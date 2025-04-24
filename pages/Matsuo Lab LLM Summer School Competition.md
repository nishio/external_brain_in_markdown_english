---
title: "Matsuo Lab LLM Summer School Competition"
---

![image](https://gyazo.com/b0631db7cfa8ad1bf6d02dc707fc34c6/thumb/1000) (thanks TaroNakasendo)
![image](https://gyazo.com/8c1a991f9f156c0aef595175c7ab22b1/thumb/1000)
- Final Score

10/10 deadline
- The final exercise of [[Matsuo Lab Summer School 2023 Large-Scale Language Models]] was a competition in which participants competed against each other for the best score.
- Three types of tasks are offered in the mix
- Two of them are mechanically quantifiable tasks (five-choice quiz, long summaries) that create leaderboards
- Mutually evaluate the quality of the remaining generated tasks with their top finishers.

Participants tackle the same issues by asking questions and discussing on Slack
- This is so helpful, it's like my own trial and error times extended several times over.
- When the "[[Please provide an offload_folder]]" that other participants were getting stuck with appeared in my environment, I was able to quickly check and solve the problem by saying, "Oh, this is what was talked about in Slack.

Matsuo Lab's exercise environment, omnicampus, can use up to 8 GPUs with 24 GB.
- You get 50 credits to start with, and if you use eight of them, you'll spend eight credits in an hour.
    - The 313 people scoring above baseline as of 10/2 received an additional 75 GPU hours of GPU credit.

digest
- I switched between "TheBloke/StableBeluga2-70B-GPTQ" for the multiple choice and open-ended questions and 'lightblue/openorca_stx' for the summary questions.
- multiple-choice question
    - It has been hypothesized that knowledge is stored in all the coupling layers, and certainly the change from 'stabilityai/StableBeluga-13B' to 'TheBloke/StableBeluga2-70B-GPTQ' significantly increased the percentage of correct answers.
    - By referring directly to the probability of the occurrence of choices instead of generating sentences, the speed was bombed out and the percentage of correct answers increased.
- summary problem
    - Tasks suitable for fine tuning because it is difficult to verbally dictate the expected style of output and the cost of doing a Few shot is high due to the lengthy input.
    - Trained with 4 L4 GPUs in the exercise environment, a little over 2 hours for 1000 data.
    - We have confirmed that performance increases as more data is added. We have a little over 7,000 data available, but it looks like we won't be able to test it due to the limitations of the GPU credits we were given.
    - I decided to use 'lightblue/openorca_stx' which is fine tuned with similar data.
    - The original prompts scored better with an increased repetition penalty for the summary output, but when aligned with the fine-tuning prompts that we learned about later, the scores were higher without increasing the penalty, so we reverted to the original prompts.
- open-ended question
    - After looking at the output from each of the two, the StableBeluga2-70B looked better, so I chose that one.

thoughts during competition
- I'm looking back at the notes I wrote during the competition and writing them after the competition is over.
- Dare to write what you think is "natural".
    - I didn't know what I myself was "used to people taking for granted".
    - Example: record what you are thinking
        - So that you can look back later and see what you were thinking.

# before start
.
- The competition probably started on Monday, Sept. 25th, but I was on a trip ([[Kumano Kodo 2023]]) from the 24th, so I was late and joined the competition on Friday the 29th.
- I had a lot of meetings on Fridays, so I listened to the last lecture in between and looked at Slack and thought, "There's a lot of posts."
- Saturday the 30th, I read all the Slack logs I had accumulated and put them in a private Scrapbox.
    - This could come in handy later when searching for error messages.
- On 9/29, an announcement was made to grant additional GPU usage time to those who had submitted by 10/1.

# 9/31
- In the meantime, I'll run the starter and work up to submittal.
    - Check first before tinkering, because if you tinker first, it will be difficult to isolate the problem when it occurs.
    - And I'd like to get additional GPU use time.
- Beep at the end (thanks chocopan)
python

```
!pip install Jupyter-Beeper
import jupyter_beeper
b = jupyter_beeper.Beeper()
...
b.beep(frequency=392, secs=3, blocking=True)
```

    - I thought it would be nice to have a different sound on errors as well, but that was never implemented after all.
- Falling into the [1GPU + device_map='auto' trap
    - The [[device_map='auto']] setting automatically puts the model and the tensor in progress in RAM or disk if the model cannot be fully loaded on the GPU, which slows down the inference (thanks shitsutyo).
    - You can check which GPU each layer of the model is assigned to by [[hf_device_map]] (thanks chocopan)
    - I noticed later that with Google Colab, the resource consumption is displayed in a graph, so it's easy to understand the situation.
    - I had read about this area earlier in Slack, so I was able to recognize the cause of the problem.
        - I wrote: [[Please provide an offload_folder]].
- Starter worked fine: score: 2.0.
    - I named the output file baseline.json and saved it.
    - This has since been utilized dozens of times.
- I implemented it because I thought it needed a progress indicator.
    - Showing how many tasks are in a task
    - The start time of the task and the time required for each task are displayed after
    - To understand "how much progress we are making and how much more time it will take."
- I noticed that the summary questions start at the 100th question around here.
    - The input on this is very long.
    - I thought this was the reason for the flurry of reports on Slack that it ran halfway through and then died due to lack of memory.
    - Flags for thinning out the test to 1/10, for solving only one summary question, for skipping the multiple choice questions (the first 100 questions), and so on.
    - I made sure these methods didn't kill me before I let them run full time.
    - Number of seconds taken to infer with 1/10 data `{'generation': 8.499536145999855, 'summarization': 41.61696943300012, 'multiple_choice': 36.508038440000064}`
        - A summary task with only 20 questions uses more time than a selection task with 100 questions.
- I saw on Slack that people wanted to increase max_length because the summary was broken, and that increasing it made it worse.
- I checked the input size of the summary task and noticed that some of them exceeded 2048
    - If max_length is set to 2048 tokens, even 2 GPUs will overflow
    - 4GPU, 1/10 the number of seconds it took to infer with data `{'generation': 2.6214422240000204, 'summarization': 58.79387292899992, 'multiple_choice': 0}`
    - 4096 tokens would cost even more.
        - I figured I'd either throw it away without seeing the entire input or read it in segments.
- Experiments running on Google Colab

# 10/1
- Experiment with Colab
- (A) Prompt change for now: went down
    - I thought the format I was used to with ChatGPT would be better, but it wasn't.
    - I guess it's important for the unwise LLM to give information in a format that is easy for that unwise LLM to understand.
- (B) made stabilityai/StableBeluga-13B: 2.67003
- Beluga-13B + max_token for summarization and generation set to 1024: 2.79775.
- (A) and went down, so the prompt is returned to the original from (B).
    - 2.72885
        - (B) is an improvement since it is a comparison from 2.67003
- Experiments in this area are being conducted in parallel at Colab.
    - I think it's good that students can experiment without having to charge, but that doesn't mean I shouldn't charge.
    - My disposable time is the bottleneck because I can't just compete all the time, and GPU time is relatively priceless because it can be bought with money.
    - Colab Pro+ was contracted to run the experiment and then implement and run new experiments while waiting for results.
    - ![image](https://gyazo.com/23dd95763cb4e2168c476b7dddcc13a9/thumb/1000)
    - It is kind enough to display how much is left.
- I wrote code to split it up, summarize each one, and combine them, but stopped when I looked at the correct data and decided that the required summary sentences were shorter than I had imagined and would not score well.
- Talk about [[lightblue/openorca]] being strong in summary tasks (thanks y_morinaga)
    - 4 points just for the ingenuity of the prompt.
    - Fine tuning at XLSUM.
- Talk about strong compared to [[TheBloke/StableBeluga2-70B-GPTQ]] (thanks mizoguchicoji)
    - multiple_choice:
        - baseline: 35 correct answers
        - TheBloke/StableBeluga2-70B-GPTQ: 90 questions correct
        - lightblue/openorca_stx : 80 correct answers
    - summarization:
        - baseline: 4.044292964896873
        - TheBloke/StableBeluga2-70B-GPTQ: 4.705614584018149
        - lightblue/openorca_stx : 6.788956451595625
- thinking
    - The summary in [[lightblue/openorca]] is strong because it is trained in [[XLSUM]], so perhaps the test data is also XLSUM-derived.
        - This would easily improve performance.
        - but for me, "increasing my experience" is a more important strategic goal than "increasing my competition score".
        - So Next Action is Fine Tuning at XLSUM
    - If the compatibility of each task with the model is so different, we should be able to experiment with each task and get results.
        - I expect that the final output will switch between models for each task.
    - You should try to solve the choice questions with TheBloke/StableBeluga2-70B-GPTQ

# 10/4
- model00: Fine tuning with starter
    - Notice: long summary inputs are skipped from the training data in the starter to begin with (shared on Slack).
- I was looking at xlsum and noticed: I thought this task called "summary task" is not really a summary (I shared it on Slack).

>   {
>      "id": 19,
>      "task_type": "summarization",
> "text": "Moosa Ucavir Suspect Moosa Ucavir, a suspect suspected of involvement in the Barcelona incident, was one of those shot dead by police in Cambrils about eight hours after the Barcelona attack, according to Catalan police in Spain. The suspect was a Spanish national from Girona in northern Catalonia and was believed to have been 17 years old. Police later announced that the driver was at large in the Barcelona attack. Local media reported that this was the suspect Younes Abouyakoub, 22, who is already wanted. The suspects are suspected of also hitting pedestrians with a van in Cambliss, killing one woman and injuring six others. According to the investigation, one officer shot and killed the suspects as they exited the overturned vehicle after hitting the pedestrians. One of the suspects allegedly had a knife in his hand. He was wearing what appeared to be a suicide belt, which was later determined to be a fake. Said Ahraa, 18, and Mohamed Heichami, 24, who were wanted by police along with Ukabir, were also among the four suspects who died in Cambliss. Of the wanted suspects, only Younes Abouyakoub, 22, has not been located. All but one of the suspects, except Uqabil, are said to be from Morocco. From left to right: the suspects Ukabir, Ahraa, Haichami, and Abouyakoub. The three left are dead. The suspect Abouyaqoub is missing. Ukabir suspect is believed to have rented several vehicles using his brother's ID. His brother's ID was left in the van used in the Barcelona attack. Another van, believed to have been prepared for the escape, was found in the city of Vic, about 80 km north of Barcelona. Investigators have linked the Barcelona and Cambrils attacks to a house explosion that occurred in Alcanar, about 90 km southwest of Cambrils, on the night of August 16. One person was killed in the house explosion. Authorities suspect that the suspects were attempting to build an explosive device and are investigating the possibility that they were planning a more sophisticated attack. People at the scene of the Barcelona van attack Four other people have been arrested in connection with the series of incidents. One person was arrested after the explosion at a house in Alcanal, and three others were arrested after the Barcelona attack in the city of Lipoy, about 100 km north of Barcelona. Doris, the brother of the Ukabir suspect, was one of the suspects and was arrested after he turned himself in. He stated that his brother stole his identity and procured a car for the raid. One Spanish man and two Italian men were confirmed dead in the Barcelona attack, as well as a Belgian, a Canadian, and an American. According to Australian news reports, a 7-year-old boy with dual British-Australian citizenship is missing after being separated from his seriously injured mother at the scene. (English article Barcelona attack key suspect Moussa Oukabir confirmed dead)",.
> "answer": "One of the suspects in the incident in which a van hit a string of pedestrians on the busy Las Ramblas street in Barcelona, the main city in northeastern Spain, on the evening of the 17th, killing at least 13 people and injuring more than 100, was confirmed to be one of five people shot dead by police in Cambrils, about 120 km west of the city earlier the next day. It was confirmed that he was one of the five people shot dead by police in Cambliss, about 120 kilometers west of the city early the next day. The attackers who were shot dead also hit a string of pedestrians in a van in Cambliss, killing and injuring seven people."
>    },
- The "Las Ramblas" in answer is not included in the input.
- I thought this was not a "summary task" but a "task to input the second and subsequent paragraphs of a news article and generate the first paragraph
    - I don't know if I can use that kind of data! I thought.
- I explicitly prompted this.
    - "You are a newspaper reporter. Below is a fragment of a news article, with the title of the English article at the end. Create a plausible first paragraph."
    - It took a long time and the connection to the instance went wrong in the middle of the process.
        - Score measurement by having partial data exported, not good.
    - Observed output. It was determined that the longer output led to a worse score.
    - The crux of the summary task seems to be to make the output of moderate length.
- Implementation of measuring scores by task type
    - Since it is known that the baseline is the basis for calculating the score and that the score is 2.0, you can get the score for each individual task by submitting the baseline results with only the results for the specific task overwritten, where mc is the choice question and sum is the summary question.
    - coji made [https://github.com/coji/llm-competition-evaluation](https://github.com/coji/llm-competition-evaluation), a system that allows score calculation at hand, but I did it this way because preparing the correct answer data was too much trouble for me.
    - Past SUBMITS were also broken down to check individual scores.
    - Best so far
    - mc: Beluga-13B + Original Prompt: 3.0
    - sam: Beluga-13B + 1024tokens: 1.85658 (losing to baseline: 2.0)
- TheBloke/StableBeluga2-70B-GPTQ
    - mc: 3.29412 (best!)
    - sam: 1.94878 (losing to baseline: 2.0)
        - This one has a prompt fix in it too.
        - I've also compared it to the one with the prompt undone, but not with good results.
        - Visual observation of the results made me feel "pretty long".
        - I'm still going to have to use fine tuning to control the length.

# 10/8
- 'lightblue/openorca_stx'
    - mc: 1.76471
    - sum: 2.45053 (best!)
        - It is still strong!
- Experiment to control length with fine tuning
    - Experiments with N=100 and N=1000
    - model01: sum: 1.42116
    - model02: sum: 1.45841
    - It seems to get better with more data...
    - I have about N=7000 of data prepared using xlsum, but I don't think the performance will improve for the cost...
- openorca + repetition penalty:1.2
    - Thought: I observed the results and found a case of word repetition, let's increase the penalty.
    - sum: 2.46645 (best!)
- Training Details story on lightblue/openorca_stx (thanks mizoguchicoji)
    - The prompts used during the study are written
    - Thought: if fine tuning in XLSUM increased the performance of the summary, wouldn't it be better to align to the prompt at the time of that fine tuning to increase performance?
    - sum: 2.63799 (best!)
    - It still has a repetition penalty:1.2, but that should be aligned with the one at the time of the study.
    - sum: 2.93555 best! (10/9)
- Referring to probability without replaying the text in a choice question
    - ![image](https://gyazo.com/11f25a73f8d219ac189cc71a0957ef5e/thumb/1000)
        - [What's going on with the Open LLM Leaderboard?](https://huggingface.co/blog/evaluating-mmlu-leaderboard)
    - Someone implemented and shared what was presented as an example of improvement in the starter but which I had not gone through because I thought it looked like a pain to implement (thanks piyoketa).
    - mc: 3.29→3.52941 (best!)

# 10/9
- mc: 3.52941 sum: 2.93555 so I submitted it and was done with it because it was over 4.0 and I felt like this was good enough.

# 10/13
- I did not understand that to participate in the final test with the additional data, I needed to participate in the creation of the test data!

Comments
- A free exercise environment would be a good thing for many.
    - 50 GPU hours will be given out to everyone free of charge, fat chance!
    - [[NVIDIA L4]](24GB) for up to 8 cards
    - An additional 75 GPU hours were handed out, fat.
        - Maybe it's Mr. Google who's the fat one.
- First time using [[Google Colab]] pay-as-you-go.
    - A100 with 40GB VRAM available for $150 per hour.
    - Good for "parallel use" compared to own hardware or exercise environment.
        - I'm doing one experiment and something comes to mind that makes me want to do another.
        - In an environment where only one experiment can be done at a time, one must wait until the first experiment is completed
        - Google Colab can probably experiment with up to 4 in parallel.
        - I have a limited amount of time to concentrate on my experiments, so being able to run the experiments I have in mind in parallel has increased the efficiency of my time usage.
    - The good thing is that you can add 1,000 yen at a time, so you only lose 1,000 yen if you accidentally fall asleep.
- Google Colab UI is great!
    - I especially like the ability to graph memory and VRAM usage on the side panel.
    - I'm like, "Huh? The model isn't on the GPU?" You'll notice that
    - A model that was supposed to be in VRAM was in VRAM earlier, but now it is not. You can notice such happenings.
        - If you don't notice this, you'll find yourself in a situation where you're like, "Hey, I finished in an hour earlier, but I'm not done yet this time.
        - It's important to be able to "quickly recognize when behavior is different than expected."
- It was a good experience when a service was provided to judge "how much better" and it was possible for hundreds of people to compare "goodness" by the same standard.
- The Slack forum to help each other was very beneficial.
    - Typical mistakes and their resolution by someone other than myself, so I didn't waste time getting into the boring stuff.
    - I kept a good log.
- I used ipynb so much this time because it was required as a final submission, and I thought it was a good one!
    - I was tempted to do what I was used to, which was to put the files locally and manage them in git because I was worried about working in Jupyter Notebook and it was confusing, but in retrospect, I could have moved more toward Notebook.
    - Good point, #1, acting as a tax cue.
        - When you run a large process, the mental model of local development tends to make it a process, and in that case, the way to do it afterwards is not so easy to understand: "Do this process when that process is done.
        - If it's Notebook, just "add a cell and keep it running".
        - It is also good to have access to namespaces unlike in the case of separate processes
        - I should have saved the value of this variable in the code. can be saved after the fact.
        - It's also nice to be able to interrupt a running script to look at the value of a variable.
    - Output is saved by default
        - If you're developing with local scripts and you print something, it tends to get lost if you want to look back on it later, unless you save it to a file with tee or something.
        - Of course, I could just write the logs to a file with logging or something and read them with a tail or something.
        - I'd like to see the print and the stack trace on error all together and managed as a set of "code executed at that time" without having to think about that.
        - This feature requires that it not be rewritten during execution
            - If you want to tinker with it, just save it as a different name and connect it to another kernel.
            - Save As" is the equivalent of creating a branch in git
    - file system
        - Running it on a browser is where I'd be concerned about persistence and such.
        - In the exercise environment, there was a directory that was persistent.
        - In Colab, just mount Google Drive.
        - I was recommended [[runpod]] and will consider it in the future (thanks satoru_hataya)
    - You can do something like Github Copilot on Google Colab.
        - Because it's Pro+?
- I'm starting to think that having a deadline and a sense of "everyone is doing it" was a good thing.
    - Like studying for an exam in the library.
    - Actually, there are 2000 people in Slack and only 500 people have submitted, so it's not "everyone.

---
This page is auto-translated from [/nishio/松尾研LLMサマースクールのコンペ](https://scrapbox.io/nishio/松尾研LLMサマースクールのコンペ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.