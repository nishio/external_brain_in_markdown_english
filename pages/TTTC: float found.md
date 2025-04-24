---
title: "TTTC: float found"
---

A troublesome bug that causes NaN to get mixed up in the argument extraction stage and die in labelling and visualization.


:

```
Running step: labelling
  0%|                                                                                    | 0/8 [00:00<?, ?it/s]
Traceback (most recent call last):
  File "/Users/nishio/election2024_broadlistening/scatter/pipeline/main.py", line 39, in <module>
    main()
  File "/Users/nishio/election2024_broadlistening/scatter/pipeline/main.py", line 35, in main
    termination(config, error=e)
  File "/Users/nishio/election2024_broadlistening/scatter/pipeline/utils.py", line 295, in termination
    raise error
  File "/Users/nishio/election2024_broadlistening/scatter/pipeline/main.py", line 27, in main
    run_step('labelling', labelling, config)
  File "/Users/nishio/election2024_broadlistening/scatter/pipeline/utils.py", line 255, in run_step
    func(config)
  File "/Users/nishio/election2024_broadlistening/scatter/pipeline/steps/labelling.py", line 44, in labelling
    label = generate_label(question, args_sample,
  File "/Users/nishio/election2024_broadlistening/scatter/pipeline/steps/labelling.py", line 55, in generate_label
    outside = '\n * ' + '\n * '.join(args_sample_outside)
TypeError: sequence item 6: expected str instance, float found
```


:

```
['I want you to reduce the burden on teachers.' ''I would like you to reduce the burden on teachers from Tokyo, which has a large budget.''
 'I would like to see a drastic improvement in the quality of public education by securing and improving the compensation of teachers on the metropolitan government's own.'
 'I think we need an environment where people who don't have assets can sit back and think about things 24/7.' Nan
```


NaN is in.


py

```
def generate_label(question, args_sample, args_sample_outside, prompt, model):
    llm = ChatOpenAI(model_name=model, temperature=0.0)
    # remove NaNs from args_sample
    args_sample_outside = [arg for arg in args_sample_outside if isinstance(arg, str)]
    args_sample = [arg for arg in args_sample if isinstance(arg, str)]
```


Even with this fix, visualization kills it.


args has nan in it.
![image](https://gyazo.com/f5fb29471b5a877807cdd8a71a554b24/thumb/1000)

![image](https://gyazo.com/c806a3ffd527d7ca2ab517f597c49338/thumb/1000)

Manually scraped.
- The script that outputs should filter

---
This page is auto-translated from [/nishio/TTTC: float found](https://scrapbox.io/nishio/TTTC: float found) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.