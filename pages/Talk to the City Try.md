---
title: "Talk to the City Try"
---

> [nishio](https://x.com/nishio/status/1796156174250734034) [[Public Comment on AI and Copyright]] collected by Agency for Cultural Affairs was analyzed and visualized by AI(Talk to the City)
>  ![image](https://gyazo.com/513b9a5424f8f2b112bd9305ed5677dd/thumb/1000)
> [nishio](https://x.com/nishio/status/1796156300189208780) You can switch to Japanese by using the flag icon in the upper right corner
>  [https://nishio.github.io/tttc_aipubcom_japan/](https://nishio.github.io/tttc_aipubcom_japan/)



experimental process
---

[[Talk to the City]]
[/tkgshn/report on Taiwan's same-sex marriage debate at Talk to the City](https://scrapbox.io/tkgshn/report on Taiwan's same-sex marriage debate at Talk to the City).

2024-05-27
- I was curious about the algorithm for [[Talk to the City clustering]] on 2024-05-26, so I looked it up #Governor's race x digital democracy
- [https://github.com/AIObjectives/talk-to-the-city-reports.git](https://github.com/AIObjectives/talk-to-the-city-reports.git)
- tkgshn had a hard time using the visual tool "[[Talk to the City Turbo]]", but there is also a CLI tool "[[Talk to the City Reports]]", so let's take a look at that.
- Pipeline is a single track

Consider the data to be tested
    - [[Public Comment on AI and Copyright]]
    - It's rather trashy...

I will do a Polis-like analysis of [[Joint research by Taniguchi Laboratory, University of Tokyo and Asahi Shimbun]] (UTAS) on another matter first.
- Polis-like data and natural text are both available.
    - Fewer natural sentences
    - First, I did a Polis-like analysis ✅[[pPolis2024-05-27]].

2024-05-30
Extracting natural sentences from UTAS data
- [https://gist.github.com/nishio/de629941b5ac4a080fae88348df1499c](https://gist.github.com/nishio/de629941b5ac4a080fae88348df1499c)
    - 126 Politicians Comment on Constitutional Amendments
        - Lots of overlap.
        - 85 excluding duplicates
    - There are more comments about the House of Councillors.

Let's try something small for now. [[Small Start]]
Create and run CSV and config with comment-id and comment-body according to README

# extraction
extraction

```
Running step: extraction
 50%|██████████████████████████████████████████████████████                                                      | 2/4 [00:05<00:05,  2.92s/it]JSON error: Expecting value: line 1 column 1 (char 0)
Input was: Severe punishment for foreign powers proceeding
Response was: I'm sorry, but I can only assist in English. If you provide the text in English, I'll be happy to help you refine it.
Retrying...
 75%|█████████████████████████████████████████████████████████████████████████████████                           | 3/4 [00:07<00:02,  2.51s/it]JSON error: Expecting value: line 1 column 1 (char 0)
Input was: Governing structure reform
Response was: I'm sorry, but it seems like the text "governance reform" is in a language that I am not able to understand. I'm sorry, but it seems like the text "governance reform" is in a language that I am not able to understand.
Retrying...
JSON error: Expecting value: line 1 column 1 (char 0)
Input was: Governing structure reform
Response was: I'm sorry, but it seems like the text "governance reform" is in a language other than English, and I am unable to provide a concise and clear argument based If you could provide a translation or more context, I would be happy to assist further.
Retrying...
JSON error: Expecting value: line 1 column 1 (char 0)
Input was: Governing structure reform
Response was: I'm sorry, but it seems like the text you provided is not related to the topic of artificial intelligence. Could you please provide an argument related to AI for me to help you refine?
Retrying...
JSON error: Expecting value: line 1 column 1 (char 0)
Input was: Governing structure reform
Response was: I'm sorry, but it seems like the text "governance reform" is in a language other than English. Could you please provide a translation or more context so I can assist you better? can assist you better?
Silently giving up on trying to generate valid list.
100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████| 4/4 [00:12<00:00,  3.23s/it]
```


I'm at a loss to interpret this from Japanese.
If it doesn't work after a few retries, you give up. "Silently giving up on trying to generate a valid list."
However, the other comments are also in Japanese but easily interpreted, so I guess that means they are too short or ambiguous and fail to extract the meaning.
- 🤖"I'm not sure what you mean by 'governance reform'..."

# embedding
embedding

```
Running step: embedding
100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████| 1/1 [00:10<00:00, 10.26s/it]
```


# clustering
:

```
Running step: clustering
Traceback (most recent call last):
  File "/Users/nishio/talk-to-the-city-reports/scatter/venv/lib/python3.12/site-packages/nltk/corpus/util.py", line 84, in __load
    root = nltk.data.find(f"{self.subdir}/{zip_name}")
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Users/nishio/talk-to-the-city-reports/scatter/venv/lib/python3.12/site-packages/nltk/data.py", line 583, in find
    raise LookupError(resource_not_found)
LookupError: 
**********************************************************************
  Resource stopwords not found.
  Please use the NLTK Downloader to obtain the resource:

  >>> import nltk
  >>> nltk.download('stopwords')
```


No, no, no, no, no, no, no, no, no, no, no, no, no, no, no.
clustering.py

```
   stop = stopwords.words("english")
   vectorizer_model = CountVectorizer(stop_words=stop)
```


You're hard-coded to assume that the language is English.
Well, okay, let's just go all the way to the end and get the big picture first.

:

```
Running step: clustering
OMP: Info #276: omp_set_nested routine deprecated, please use omp_set_max_active_levels instead.
2024-05-30 14:43:23,417 - BERTopic - Reduced dimensionality
2024-05-30 14:43:23,423 - BERTopic - Clustered reduced embeddings
```


# labelling, takeaways, overview
:

```
Running step: labelling
100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████| 3/3 [00:02<00:00,  1.20it/s]
Running step: takeaways
100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████| 3/3 [00:04<00:00,  1.67s/it]
Running step: overview
```


# translation
:

```
Running step: translation
Translating to Mandarin...
100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████| 7/7 [00:16<00:00,  2.38s/it]
Translating to English...
  0%|                                                                                                                    | 0/7 [00:00<?, ?it/s]JSON error: Expecting ',' delimiter: line 1 column 216 (char 215)
Response was: ["Through public debate, considering Japan's history and education, it is necessary to create a democratic law by taking time into account.", "It is important to reflect the public opinion by creating a process of "constitutional amendment" through consensus.", "It is necessary to stop the annual budget system.", "For the protection of human rights, it is essential to have discussions and collaborations on the internet.", "Through public debate, considering Japan's history and education, it is necessary to create a democratic law by taking time into account.", "By passing the process of "constitutional amendment", reflecting the public opinion is important.", "For Japan to consider Japan's future, it is necessary to establish a law that will become the basis.", "By revising the 41st article of the constitution, implementing the national referendum, and reflecting its contents in politics is important.", "Keep an eye on the "constitutional amendment".", "Revise the 41st law, implement the national referendum, and reflect its contents in politics."]
Retrying batch...
Warning: batch size mismatch!
Batch len: 10
Response len: 9
Batch item 0: Through public debate, an independent constitution that takes into account Japanese traditions and customs should be created over time.
Response: By engaging in public debate, considering Japan's history and education, creating necessary self-defense laws over time is essential
Batch item 1: Public input should be reflected through the "constitution-making" process
Response: By promoting the principles of 'innovation', reflecting the opinions of the people to be considered
Batch item 2: Single-year budget system to be eliminated
Response: It is necessary to stop the annual budget system
Batch item 3: Internet Initiatives Needed to Protect Human Rights
Response: For the protection of human rights, it is essential to have an internet platform for gathering information
Batch item 4: Take time to create an independent constitution that takes into account Japanese traditions and customs through public debate.
Response: By engaging in public debate, considering Japan's history and education, creating necessary self-defense laws over time is essential
Batch item 5: Public opinion should be reflected through the "constitution-making" process.
Response: Establishing laws to become a better future for Japan that the Japanese people consider
Batch item 6: A constitution should be created that the Japanese people believe will benefit Japan's future.
Response: By revisiting discussions and debates, developing Japan's unique education and history, creating necessary self-defense laws over time
Batch item 7: Take time to create an independent constitution that takes into account Japan's unique customs and traditions through discussions with the public.
Response: Keep the focus on 'innovation'
Batch item 8: "Constitutional Creation".
Response: Amend the 41st law, implement national referendums on important legislation, and reflect its contents in politics
Batch item 9: Article 41 of the Constitution should be amended to allow for referendums on important bills and their content should be reflected in the political process.
Retrying with smaller batches...
```

I'm trying to translate it all together and failing.
- I had to start over a few times.
- As a result, it looks like the translation was done.

# visualization
:

```
Running step: aggregation
Running step: visualization
> next-app@0.1.0 build
> next build
```


Static HTML is output

![image](https://gyazo.com/cd28455301f8f4eb3c034e1b7bf4cf36/thumb/1000)
The title should have been set up in config or somewhere else.

> Overview:
>  The public consultation on constitutional development in Japan revealed three main clusters of opinions. Cluster 0 emphasized the importance of crafting a unique constitution reflecting Japanese traditions, while Cluster 1 focused on constitutional reform through public engagement and utilizing the internet for human rights protection. Cluster 2 highlighted the need for a new constitution with amendments to include national referendums and strengthen the role of the National Diet, along with calls for strict penalties against foreign interventions.
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Overview: (in Japanese only)
The public consultation on constitutional reform in Japan revealed three main groups of opinion. Cluster 0 emphasized the importance of creating a unique constitution that reflects Japan's traditions, while Cluster 1 focused on constitutional reform through public participation and the use of the Internet to protect human rights. Cluster 2 emphasized the need for a new constitution that includes a referendum on amendments and strengthens the role of the Diet, and called for severe penalties for foreign interference.

![image](https://gyazo.com/44f207f7dba5759da45359d4026c1481/thumb/1000)

This is what happens when you hover.
![image](https://gyazo.com/b4edf6bd8b0ac7ad8c90b4dc959f0bb3/thumb/1000)
This is what happens when you click on it
![image](https://gyazo.com/daa59e7c46e449879ef4b650b030aeb0/thumb/1000)

Can we put this in this cluster?
![image](https://gyazo.com/b4c0ca19fdd29845366f5e3a00908ed6/thumb/1000)

![image](https://gyazo.com/2d99689ba283be2603326428a2922153/thumb/1000)
Translation failure.

> Representative comments:
>  Through public debate, we should take the time to create an independent constitution that takes into account Japanese traditions and customs.
>  We should take time to create an independent constitution that takes into account Japanese traditions and customs through public debate.
>  Take time to create an independent constitution that takes into account Japan's unique customs and traditions through discussions with the people.
>  Through public debate, it is important to take the time to create an independent constitution that takes into account Japanese traditions and customs.
>  Single-year budget system to be eliminated.
- Can we put this in this cluster?

![image](https://gyazo.com/39cbb634818132cf5507627f6b9c0f5e/thumb/1000)

# Appendix
![image](https://gyazo.com/9d91ba4647492bdea0946b1d67a586bb/thumb/1000)
This is useful.
- I wish there was some progress data along the way.

AI Cost
![image](https://gyazo.com/c0e35ea852610126fe5e9d8a1bfbb20e/thumb/1000)

amount of data
- Japanese 2450 characters

Let's try a few more things before we try larger data sets.
Revisit config.
json

```json
{
  "name": "Recursive Public, Agenda Setting",
  "question": "What should be top of the agenda as humanity develops and deploys artificial intelligence?",
  "input": "UTAS_2022__SQ6_16_FA",
  "model": "gpt-3.5-turbo",
  "extraction": {
    "workers": 3,
    "limit": 12
  },
  "clustering": {
    "clusters": 3
  },
  "translation": {
    "model": "gpt-4",
    "languages": ["Mandarin", "English"],
    "flags": ["TW", "EN"]
  },
  "intro": "This AI-generated report relies on data from the UTAS 2022 (joint research by the University of Tokyo Taniguchi Laboratory and Asahi Shimbun)."
}
```


- > Titles should have been set up in config or somewhere else.
    - NAME and QUESTION are it.
- You've fixed it to three clusters.
- The translation part, I set it up like this with the intention of processing it in Japanese and then translating it into English.
    - But since the clustering was code that assumed English, I'd rather process it in English and translate it into Japanese.
    - If you want to process Japanese as it is, you need to set morphological analysis and Japanese stop-words for the part of the clustering step that uses CountVectorizer, assuming Japanese.
    - Add "All texts should be in English." to the extraction prompt and proceed with the policy of extracting in English.

re-execute
"Severe punishment for the progress of foreign powers" and "reform of the governing structure" were also said "I don't know."
Oh, I forgot to translate it into Japanese.
:

```
So, here is what I am planning to run:
{'step': 'extraction', 'run': False, 'reason': 'nothing changed'}
{'step': 'embedding', 'run': False, 'reason': 'nothing changed'}
{'step': 'clustering', 'run': False, 'reason': 'nothing changed'}
{'step': 'labelling', 'run': False, 'reason': 'nothing changed'}
{'step': 'takeaways', 'run': False, 'reason': 'nothing changed'}
{'step': 'overview', 'run': False, 'reason': 'nothing changed'}
{'step': 'translation', 'run': True, 'reason': 'some parameters changed: languages'}
{'step': 'aggregation', 'run': True, 'reason': 'some dependent steps will re-run: translation'}
{'step': 'visualization', 'run': True, 'reason': 'some dependent steps will re-run: aggregation'}
Looks good? Press enter to continue or Ctrl+C to abort.
```

They'll just redo the second half.

Translation from English to Japanese was batch-processed without any problems.
![image](https://gyazo.com/df09fdbd0383a3f2ba268babcf4f9a92/thumb/1000)
Hmmm, I don't know the term "constitutional", so it's a misinterpretation.

prompt: `All texts should be in English. Translate Japanese words based on their meaning, not just their sound.`
Error in embedding
- `TypeError: expected string or buffer`
- ![image](https://gyazo.com/e14a78aa645250327a5444578f53eb8e/thumb/1000)
That's the one.
- [FIX: LLM sometimes returns string and the code handle it as list by nishio · Pull Request #186 · AIObjectives/talk-to-the-city-reports · GitHub](https://github.com/AIObjectives/talk-to-the-city-reports/pull/186)

![image](https://gyazo.com/42ad2adc162133c7db85bbcf2040a56f/thumb/1000)
Should have named the project.



# [[Public Comment on AI and Copyright]]
534365 characters
I think it's a few hundred yen even if you do it normally, but let's try it with 1/10th of the data.

## extraction
> Input was: "A Proposed Guidelines for Business Operators", Attachment 1, Part 1, related/P13, line 20, "Risks due to Al
> Response was: I'm sorry, but it seems like the text you provided is in Japanese and it's not clear how it relates to the task of refining arguments in English. Could you please provide an argument or statement in English that you would like me to work on?
- I wonder if this is a misdirect.

![image](https://gyazo.com/96d04b3dacc97adfd0532ea689148816/thumb/1000)
Surprisingly cheap

`openai.error.InvalidRequestError: This model's maximum context length is 16385 tokens. However, your messages resulted in 17461 tokens. Please reduce the length of the messages.`
This is a problem.

Results of various experiments
![image](https://gyazo.com/93fac38b5ca66a3704982db49350eb71/thumb/1000)
It's time to make the final version.

including everything
![image](https://gyazo.com/aba0d2524512bed37a47b1f360c3f2a3/thumb/1000)
Hmmm, that's all I get when I include corporate comments.
- Is the public's comment too thin?
- Thought it would be more interesting to mix it up...

Let's limit ourselves to 2013 data from individuals.
`"clusters": 7`.

![image](https://gyazo.com/03cfc231950f8299513156ac1c034afb/thumb/1000)
Hmmm, not much has changed.

Ah, `"extraction" "limit": 12` this.
- Let's change it to 24.

![image](https://gyazo.com/752caf0a8cdf21c1254f4e09eaca97be/thumb/1000)
Increase.
But `Warning: data for page "/" is 170 kB which exceeds the threshold of 128 kB, this amount of data can reduce performance.`

I'll change it further to 48.

:

```
File "/Users/nishio/talk-to-the-city-reports/scatter/pipeline/steps/translation.py", line 102, in translate_batch
    parsed = [a.strip() for a in json.loads(response)]
```

`json.decoder.JSONDecodeError: Invalid \uXXXX escape: line 1 column 1098 (char 1097)`
Hmmm, this is tricky.

I redid it and it worked.
- I guess it means that retries are not well implemented, unconfirmed.

![image](https://gyazo.com/4532c61d6dc74dbbf653aa1481fee36a/thumb/1000)
It's nice, after all, if it doesn't have this many dots, it doesn't feel like "it's a visualization of a distribution".
- Like the feeling that the cluster in the lower right corner is a little too far away.

If the points increase as the limit of EXTRECTION is increased, it may mean that the reason why "only opinions from the organization are picked when data from the organization is mixed in" in the beginning is simply because the limit was reached only by opinions from the organization.

I'm not sure why it only cost a few cents for both the 2450 Japanese characters UTAS data and the 534365 AI pubic data, because they both hit the LIMIT.
As an experiment, we should try to make the limit bigger.
Increase LIMIT from 48 to 10000. The cost would be about $7.

I let it run, then I read the code.
extraction.py

```
   comments = pd.read_csv(f"inputs/{config['input']}.csv")
   limit = config['extraction']['limit']
   comment_ids = (comments['comment-id'].values)[:limit]
```

Ah, I see. That's how it works.
Then you put in the data for 2013, but suddenly it's down to 48!

![image](https://gyazo.com/e0e1c18e00f5b575f2fa37ab845b0fd2/thumb/1000)
We've come this far and now we're dead.
:

```
 99%|███████████████████████████████████████████████████████████████████████████████████████████████████████▏| 666/671 [29:36<00:13,  2.67s/it]
Traceback (most recent call last):
```

`openai.error.InvalidRequestError: This model's maximum context length is 16385 tokens. However, your messages resulted in 19680 tokens. Please reduce the length of the messages.`

I'm wondering if the format has changed for the data after 185001345000002001, or if it's being combined at the time of CSV extraction.
I'd have to hand scrape that and make it a 1997 case to get it to work.
But, well, technically, you can check for such oversize errors before actually hitting the API, and the oversize error messages should be a little easier to debug.

- [[Polis is opinion clustering, TTTC is topic clustering]]

We're making progress.
:

```
100%|██████████████████████████████████████| 666/666 [30:12<00:00,  2.72s/it]
Running step: embedding
100%|██████████████████████████████████████| 6/6 [00:15<00:00,  2.65s/it]
Running step: clustering
OMP: Info #276: omp_set_nested routine deprecated, please use omp_set_max_active_levels instead.
2024-05-31 04:37:45,187 - BERTopic - Reduced dimensionality
2024-05-31 04:37:45,284 - BERTopic - Clustered reduced embeddings
Running step: labelling
100%|██████████████████████████████████████| 7/7 [00:04<00:00,  1.74it/s]
Running step: takeaways
100%|██████████████████████████████████████| 7/7 [00:16<00:00,  2.35s/it]
Running step: overview
```


> I'm wondering if the format has changed for the data after 185001345000002001, or if it's being combined at the time of CSV extraction.
Conclusion, from the third PDF, the `● receipt number` is preceded by a space or not.
- That some of them have been combined because the delimiting condition was that they begin with `●receipt number`.
- Fixed, there are 2985 cases.

:

```
 93%|██████████████████████████████████████       | 556/601 [1:33:50<07:35, 10.13s/it]
Traceback (most recent call last):
  File "/Users/nishio/talk-to-the-city-reports/scatter/pipeline/steps/translation.py", line 102, in translate_batch
    parsed = [a.strip() for a in json.loads(response)]
                                ^^^^^^^^^^^^^^^^^^^^
...
json.decoder.JSONDecodeError: Unterminated string starting at: line 1 column 382 (char 381)
```

No, no, no, seriously?

Same cause as this.
- > `json.decoder.JSONDecodeError: Invalid \uXXXX escape: line 1 column 1098 (char 1097)`
- > Hmmm, this is tricky.
- > I redid it and it worked.
- > I guess it means retries are not implemented well enough, unconfirmed.
I'm not going to run it for an hour and a half and start over because it rubbed me the wrong way...

Let's turn off the translation once and try to finish it.
![image](https://gyazo.com/3812304949fb72e6d10c8414abb84422/thumb/1000)
![image](https://gyazo.com/cad9b3292c1e806ab450e1e9f2682291/thumb/1000)

For example, if we do this and say, "Let's try a larger number of clusters," will the translation be redone?
- I'm assuming that the cluster summary text, for example, is regenerated and needs to be retranslated, but the EXTRACTION results don't, do they?
- I think it should be cached and reused, but I wonder if there is a mechanism for that.

I was thinking, "The translation will be finished in 5 minutes, so I'll deploy and go to bed when it's done," when the Chinese translation phase started (a little over an hour to go).

2024-05-31
![image](https://gyazo.com/29a6818e0bb23986f1992c5ab5766713/thumb/1000)
It's done.

You've had a lot of trouble and redoing things, but you're still within the expected amount.
![image](https://gyazo.com/a1b1c1f9c32359eef0543505a5e202b5/thumb/1000)

> If we do something like "let's try more clusters," will the translation be redone?
:

```
% python main.py configs/aipubcom.json                       
(!) {'step': 'clustering', 'filename': 'clusters.csv', 'dependencies': {'params': ['clusters'], 'steps': ['embedding']}, 'options': {'clusters': 8}} step parameter 'clusters' changed from '7' to '50'
diff_params ['clusters']
So, here is what I am planning to run:
{'step': 'extraction', 'run': False, 'reason': 'nothing changed'}
{'step': 'embedding', 'run': False, 'reason': 'nothing changed'}
{'step': 'clustering', 'run': True, 'reason': 'some parameters changed: clusters'}
{'step': 'labelling', 'run': True, 'reason': 'some dependent steps will re-run: clustering'}
{'step': 'takeaways', 'run': True, 'reason': 'some dependent steps will re-run: clustering'}
{'step': 'overview', 'run': True, 'reason': 'some dependent steps will re-run: labelling, takeaways'}
{'step': 'translation', 'run': True, 'reason': 'some dependent steps will re-run: labelling, takeaways, overview'}
{'step': 'aggregation', 'run': True, 'reason': 'some dependent steps will re-run: clustering, labelling, takeaways, overview, translation'}
{'step': 'visualization', 'run': True, 'reason': 'some dependent steps will re-run: aggregation'}
Looks good? Press enter to continue or Ctrl+C to abort.
```

It looks like the translation only needs to be the part that changes.

:

```
100%|████████████████████████████████████████████| 606/606 [2:31:52<00:00, 15.04s/it]
Translating to Taiwan...
  9%|█████████                                                                                              | 53/606 [08:00<1:13:18,  7.95s/it]
```

What, it looks like you spent 2.5 hours re-translating it?

:

```
100%|███████████████████████████████████████████████████▊| 605/606 [1:38:47<00:09,  9.80s/it]
Traceback (most recent call last):
  File "/Users/nishio/talk-to-the-city-reports/scatter/pipeline/steps/translation.py", line 119, in translate_batch
    return translate_batch(batch, lang_prompt, model, retries - 1)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
...        
RecursionError: maximum recursion depth exceeded
python main.py configs/aipubcom.json  56.16s user 33.46s system 0% cpu 4:13:37.44 total
```

What the hell [full stacktrace](https://gist.github.com/nishio/b5e54d84a080fa7397559f32ee48dc84)
You've taken four hours and failed with an error that is only probabilistic.
![image](https://gyazo.com/08143c5154dee81bf134625d3c8f31f4/thumb/1000)
The cost isn't that high.
And there's something wrong with the translation running for four hours in a situation that only changed the number of clusters this time in the first place.
The probability of having to start over increases the larger the data size because there is a lack of care for probable problems.

![image](https://gyazo.com/c9a671b43b4488ac2c82390ac847e3d3/thumb/1000)
The Japanese version has already been translated, but the Taiwanese version was a flop, so there is no data for the Japanese translation.
The 50 clusters divided into 50 clusters are all sorts of unique and interesting.
It might be interesting to create a question from each of these clusters that can be divided into pros and cons and polis it.

Future Direction
- The report for Japanese users with Japanese input will be able to be executed in Japanese instead of English, which is currently done internally.
- Improve the translation script a bit more, to the point where you can check the cluster in English without translation first, and then add more languages later, Japanese, ... and so on.
- It's difficult to process data from 20,000 people in the current situation, where 5,000 data points or so are created from 2,000 human pubic comments, all of which are plotted, and clustering is applied in the previous step to combine similar opinions into one.


2024-06-03
- [[Visualize the contents of the Plurality book with Talk to the City]]
![image](https://gyazo.com/516d87e486692d3102793a8b5b27461e/thumb/1000)
Well, to filter when this kind of garbage is generated...
- There doesn't seem to be an official, easy way to do this.

Add a filter to `embedding.py`` and force re-run

util.py

```
    for (i, option) in enumerate(sysargv):
        if option == '-f':
            config['force'] = True
        if option == '-o':
            config['only'] = sysargv[i + 1]
        if option == '-skip-interaction':
            config['skip-interaction'] = True
```


Oh, no, they'll check here.
`ValueError: Make sure that the embeddings are a numpy array with shape: (len(docs), vector_dim) where vector_dim is the dimensionality of the vector embeddings. `

I'll have to rewrite the args.csv in front of me.
filter_argument.py

```
import pandas as pd

# Load the arguments from the CSV file
arguments = pd.read_csv("outputs/plurality/args.csv")

# List of arguments to ignore
ignores = ["error", "argument", "reference", "references", "source", "sources", "message", "contributions"]

# show size
print(len(arguments))

# Filter out the ignored arguments
filtered_arguments = arguments[~arguments['argument'].isin(ignores)]

# show size
print(len(filtered_arguments))

# write filtered_arguments to output/plurality/args.csv
filtered_arguments.to_csv("outputs/plurality/args.csv", index=False)
```


`arguments_array.shape=(3497,), embeddings_array.shape=(3353, 1536)`
I updated the args, but for some reason it's not re-running. force with -o again.
`arguments_array.shape=(3497,), embeddings_array.shape=(3497, 1536)`
It's done.

Oh, better.
![image](https://gyazo.com/fe17a549997d15573ac078150958add6/thumb/1000)
Released.
[https://nishio.github.io/tttc_plurality/](https://nishio.github.io/tttc_plurality/)

2024-06-17
> Encountered 15 files that should have been pointers, but weren't:



---
This page is auto-translated from [/nishio/Talk to the City試す](https://scrapbox.io/nishio/Talk to the City試す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.