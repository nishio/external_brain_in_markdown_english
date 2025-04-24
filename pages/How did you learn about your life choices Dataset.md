---
title: "How did you learn about your life choices Dataset"
---

![image](https://gyazo.com/3d5569ccbfe7db10bf2a2ea9cdfa9bea/thumb/1000)

Some people have asked for sample data in Japanese to try Talk to the City.
- On the other hand, the handling of data acquired through the X API has recently been restricted by the terms of the API contract, making it difficult to convert the data into open data.
- This "How I learned about life choices dataset" was solicited by Nishio on Twitter on 2021-05-07 and 247 submissions were collected. It was collected manually without using the Twitter API at the time, so it is not bound by the X API agreement.
- The original data collected manually can be found here: [[How do you know what your life choices are?]]

## Dataset
.
[https://gist.github.com/nishio/116708c1f65d21d224f2a5fe40bc962d](https://gist.github.com/nishio/116708c1f65d21d224f2a5fe40bc962d)
- 250 cases

## The process of creating a dataset
.
It would be helpful for future Talk to the City users with their own data to note this.

Original data is blank line delimited
- [https://gist.github.com/nishio/e134a1aa0627512da8e1a765ea7ec7b5](https://gist.github.com/nishio/e134a1aa0627512da8e1a765ea7ec7b5)

So I wrote code to make it a CSV, separated by blank lines.
- [https://gist.github.com/nishio/d2db6c529e2ada71e795e448b0469d94](https://gist.github.com/nishio/d2db6c529e2ada71e795e448b0469d94)

I'll try to put in the first 25 cases first and just run the EXTRACTION step.
- `$ python main.py configs/choice.json -o extraction`
- Now look at the results and modify the prompts or add examples of FEW SHOTS (referring to the input and output examples at the end)
- TTTC ignores the original data if it cannot be successfully extracted after several attempts (Silently giving up on trying to generate a valid list.)
- Example
:

```
JSON error: Expecting value: line 1 column 1 (char 0)
Input was: [https://gyazo.com/eb0af52aab8f22c0e91035bb2c106165]
Response was: Sorry, we are unable to directly verify the content of the image or link. If you could provide a text description of the content of the image, we may be able to help you with that information.
Silently giving up on trying to generate valid list.
```

- This example is due to the fact that there was a paragraph with only image links in the text that was included.
    - ![image](https://gyazo.com/e7ad3334c76f1526fcd6a7ac338363be/thumb/1000)
    - It is easy to remove these things from the original data if there are not many of them.
    - In many cases
        - If you can easily write a rule-based filter in Python, play with it.
        - If it's not easy, play it at the prompt.
        - Or add "filtering steps to be played at the prompt" before

If it seems to work, I'll add more data.
- At this time, `nothing changed` is displayed even though the data is changed (this may be a bug).
- If you change the prompt, it recognizes that it needs to be re-run.
- Can be forced to rerun.
    - `$ python main.py configs/choice.json -f`
- Force reexecution even if "only" is specified
    - `$ python main.py configs/choice.json -o extraction`
    - If it's an experiment with growing data, this is the way to go.
    - After confirming that there are no problems, run normally and the extracted data will be reused and run from next time.
        - `$ python main.py configs/choice.json`

- I tend to forget to increase the limit of extraction in config.
    - This is a parameter for trial-and-error prompting with a small amount of data in cases where the data CSV itself is already available.

- I'll try to visualize it with 100 cases for now.
    - ![image](https://gyazo.com/beb0708b8dfd568533bf5704ca98abd7/thumb/1000)
    - Directions seem fine.

Modify "name", "question", and "intro" in config.
- Since this is an update of the visualization description, I thought it would be sufficient to update only the visualization, but it is the aggregation that takes the data for display from the config and creates a chunk of data for visualization.
- `$ python main.py configs/choice.json -o aggregation`
- `$ python main.py configs/choice.json -o visualization`
- (I feel like there should be a way to re-run this after aggregation.)
- ![image](https://gyazo.com/fb50af81b5da9e460a94224df167d409/thumb/1000)
- The "number of data analyzed" is described in aggregation.py, the amount of data is automatically described
- ![image](https://gyazo.com/578c7020b1bd1c30175f3bc2aaf38b95/thumb/1000)

Final config and prompt
- [https://gist.github.com/nishio/74e8c1d8c52847080dbdcdd15c3681db](https://gist.github.com/nishio/74e8c1d8c52847080dbdcdd15c3681db)
- [https://gist.github.com/nishio/090f5ca74a7d5d7f36769b00def773c2](https://gist.github.com/nishio/090f5ca74a7d5d7f36769b00def773c2)

---
This page is auto-translated from [/nishio/人生の選択肢を知ったきっかけデータセット](https://scrapbox.io/nishio/人生の選択肢を知ったきっかけデータセット) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.