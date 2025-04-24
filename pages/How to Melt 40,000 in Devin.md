---
title: "How to Melt 40,000 in Devin"
---

- [I was too busy on a business trip to take a closer look, but when I looked at it later, I saw that he had melted 45,000 yen in a single thread terrible.
- I don't mean to blame you for this, as the financial burden has already been recovered by you, the volunteers, and the money thrown in by [[Scott Wu]], the CEO of the company.
- I feel that if we introduce it in a company in a messy way, there might be one similar case in each company, and everyone should know about it in advance.

# task in question
.
![image](https://gyazo.com/efcb5d9956a28e98e31f05a62e4490c6/thumb/1000)
This is the Dantotsu task that is the most dangerous.
- 1ACU = 2USD = a little over 300 yen, or 45,000 yen for one of these.
- You can do something fairly useful with about 10 ACUs, so what are you doing with 10 times more than that?
- The one above, which uses 75 ACUs, is generated entirely by [contrast-game](https://github.com/nishio/contrast-game), so it's not half as much as it costs twice as much.

# What was going on?"
I had o1 Pro read the log and explain it to me.

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
The following is a brief description of the interaction between a human (user) and an AI (Devin), with the individual names withheld.

# exchange summary
.

1.### Run Jekyll and check logs
.
- A human asks Devin to run the designated GitHub repository with Jekyll and check the logs, and Devin starts Jekyll and presents the logs, although he has trouble with the Ruby version settings and plugin errors.

2.### Sass Deprecation Warning fix
.
- Humans are assigned the task of fixing Sass warnings (Deprecation Warnings); Devin creates several patch files, but there are a number of problems that fail to apply, or include irrelevant differences such as Gemfile.lock or .rb files.

3.### patching trouble
.
- Humans point out the errors with `git apply --check` and Devin fixes the patch file, but it often happens that the warnings are not resolved completely and the patch is not properly applied.

4.### Work in progress
.
- Devin has a restriction that he goes to sleep when his session usage (ACUs) exceeds a certain level. Each time this happens, a human being urges him to "report his progress and then go to sleep," and although Devin reports that he is "fixing xx remaining warnings," he repeatedly falls asleep without completing the work.

5.### Partial resolution on the human side
.
- The human commits to fix some of the warnings using Sass Migrator on his own, and again asks Devin to "fix the rest of the warnings." Devin resumes the task, but falls asleep again in the process, etc., and eventually presents a patch file, but it remains unclear whether the problem has been completely resolved Termination.

# oddities/notes
(There are many things, but the important one is this <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>)
- Interruption due to session limitation.
- Devin frequently "sleeps" due to session usage limitations, causing work to be interrupted. When a human asked for a progress check, the corrections did not come together properly until the end, leaving it ambiguous whether all warnings were finally resolved.

Overall, the dialogue is characterized by a series of exchanges trying to fix a Deprecation Warning in Sass, but not completing smoothly, as Devin is unable to finish the patch properly or is interrupted by session limitations.

---
# 問題点1: Usage LimitによるSleepの挙動が理解されていない
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
Sleep by Usage Limit occurs as an emergency stop when more than 10 ACUs are used without any interaction since the last instruction.
- 10ACU=20USD=a little over 3000 yen
- I want people to understand that this is a very unusual situation, as I have rarely had this happen in all the years I've been using it.

Note that after this event [release notes for 1/16/16 at](https://docs.devin.ai/release-notes#devin-usage-best-practices)
- The comment, "Basically, keep it within 10 ACUs, the longer it goes, the worse the performance will be." and
    - > Keeping sessions under 10 ACUs (Devin’s performance degrades in long sessions)
- Long session warning display added to the Web UI side.
    - ![image](https://gyazo.com/bdfff1acbe58851295b7fd3cdc6fbd23/thumb/1000)
- I don't know, but if you're using it from Slack instead of the web UI, you won't notice it, and most people will use it without even reading the documentation, let alone the release notes, so the safety guards are too weak.
- And this sleep state is easily released when you talk to them on Slack.
    - You're definitely going to disarm it without realizing it.

---
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>How many times have you actually fallen asleep?
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>The following logs show that Devin went to sleep a total of ### 8 times
 (the timing of "Devin went to sleep due to session usage settings" and "Devin went to sleep due to user inactivity" is (count).
Progress at each of these timings has all been reported, such as "partially fixed Sass Deprecation Warning," but the final solution has not yet been fully resolved. Below is a summary of the main progress made just before going to sleep.

1.### 1st (5:07 PM)
    - Prior to that, the company indicates a policy such as "create a patch to fix Sass", but the actual deliverable (patch) is still in the error-prone stage. No clear completion report.

2.### 2nd (9:33 PM)
.
    - He reported that "364 warnings have been fixed." However, many warnings still remain, and patching continues to fail.

3.### 3rd (7:14 PM)
.
    - Continuing to fix Sass warnings. Just before the end of the day, it tells you that it is "in the process of fixing mixed declarations" etc., but goes to sleep before it is completed.

4.### 4th (2:42 AM)
    - Similarly, while stating progress that "364 _type.scss and _rfs.scss have been fixed," the correction of _reboot.scss and others is not yet complete.

5.### 5th (8:36 PM)
    - We are attempting to create a patch and check the build of Jekyll, but have not yet been able to provide an appropriate patch.

6.### 6th (7:34 PM)
    - It wasn't reported until "finally, Warnings were reduced to zero," and then it went to sleep with only a partial fix.
        - Even in this area, there are still reports of patching problems and fixes in progress.

7.### 7th (2:03 PM)
.
    - Only reported "continuing to fix Sass." No specific details on the number of warnings remaining were given.

8. ### 8th time (8:22 PM, user inactivity)
.
    - Finally, a patch called "css-fixes.patch" is presented, but it is not clear if it completely eliminates all warnings.
        - Just prior to this, he also told them that the warning disappeared at build time, but ended up not verifying what actually happens when it is applied.

- Summary
- Devin has fallen asleep a total of 8 times.
- Although there are reports of "fixing some warnings" and "creating patches" just before each sleep, none of the work has been completed, and it remains unclear whether the remaining warnings have finally been completely resolved.
- Although there is a "progress report" before each sleep, there are repeated errors in applying patches and re-fixes to remaining warnings, and no reliable completion report is seen.

-----
So, since they are sleeping 7 times at the Usage Limit, they have melted at least 21,000 yen there alone.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

# Specific example of Sleep with Usage Limit
.
![image](https://gyazo.com/93da0b5bdc8ed46a4ae5c61b39cb4014/thumb/1000)

Devin goes to sleep without any output after this, maybe it would have been shown in Slack as follows
- ![image](https://gyazo.com/c3504cf9f0ae6eb605adf939b6d9e1ba/thumb/1000)
    - If you read it carefully, it says, "You can continue if you talk to them, but it's not a good idea to go over 10 ACUs because it will slow down Devin's performance, we generally don't use 10 ACUs, read the documentation to learn how to use the recommendations..." ...
- This remains in the Web UI, but the Slack side disappears the moment you speak to it.
    - I don't think it should be turned off, I'd rather have it displayed in a toxic color (...)
- And the next day, Devin is casually tapped awake.
    - ![image](https://gyazo.com/76ef77f77dd58bad00f091427159cf29/thumb/1000)
    - Maybe you're unaware of this situation.
- AI does not recover from sleep.
    - Instead, the longer the context, the lower the performance.
    - So, to use an analogy, this is like waking up an engineer who has been up all night for three days and is so exhausted that he is falling asleep in his office and saying, "Good morning, I've got a lot of work to do! Let's get on with our work! It's a terrible act!
    - Instead of letting it continue, it would have been better to hand it over to someone else (Devin) or to see why it's so complicated.

# Differences in mental models from conventional programming
.
Something similar to this is happening with several people, not just this one seemingly.
I have used more than 10 different paradigms of programming languages, and have published a book on comparing and learning languages, "[[Technology Supporting Coding]]", and from my point of view, this is almost like a paradigm shift in programming. I think this is similar to a paradigm shift in programming.

Perhaps a conventional mental model would make the following code look "efficient"
python

```
for task in tasks:
	process(task)
```

They would feel more efficient because humans write less and computers work a lot more.

In fact, in this case, people were giving these instructions.
> Okay then, can you try your best to fix all of warnings you see in the logs?

In other words, if you put it in code, it would look like this
python

```
for warning in logs:
	fix(warning)
```


The plan generated internally by Devin reflecting that instruction is also in the loop.
![image](https://gyazo.com/17b365aa705d5e69504a8e817e72163a/thumb/1000)

Is this really efficient?
In the current LLM mechanism, which maintains contextual memory by first adding to the context, repeating the loop gradually extends the input to the LLM, increasing the time it takes and the amount charged.
![image](https://gyazo.com/3fb11d784a9c98d534e6385e33c0e871/thumb/1000)
To look at it the other way around, if you run similar tasks in a loop, AI-kun will get dumber and slower as the loop turns.

# Scale of contents of loop
.
The next problem is the scale of the loop's contents relative to the task
For those accustomed to recent programming environments, the cost of the loop's contents is too often small and unconsciously assumed to be zero.

In reality, however, as long as you hit the LLM API that you are charged for, it costs money per processing. Moreover, due to the "efficiency decreases as the loop turns" effect described above, for example, in the case of a squared order, it costs 900 times as much to process 30 cases at once. If there is a [[Prompt Caching]] or something like that, it can be mitigated, and other efforts will lower the order, so the 900-fold increase will only occur in a very naive configuration, but basically, the cost is greater than linear.

How much does that one task cost to perform? It is dangerous to throw a large number of tasks in a loop when you do not have a good feel for this.

Also, we don't know if the processing by LLM will return the expected results. The AI is not responsible for producing "results you are satisfied with," so it is more like outsourcing under a sequential delegation contract than a contract agreement. The AI is not responsible for producing "results to your satisfaction," so it is more like subcontracting under an orderly delegation contract than a contract agreement.

How to manage AI in such a situation is to first try a small unit to see if it can be done and how much it will cost before placing a large order. This is an idea well known as [[Minimum Viable Product]] proposed by [[Lean Startup]].

# Finally
.
Recently, an INVITE link has been set up where the referrer and the person referred will receive 100 ACUs, or a little over 30,000 yen as a referral fee.
I'm taking the initiative and hurting my own wallet to gain knowledge, so please don't hesitate to throw money at me!
[https://app.devin.ai/invite/iDYvHCNSdfhnClCf](https://app.devin.ai/invite/iDYvHCNSdfhnClCf)





Material notes

![image](https://gyazo.com/81fa61350c0a4bbc6d15bab47bed5241/thumb/1000)

![image](https://gyazo.com/58aaa53f0b2f805d978392a4e8838944/thumb/1000)
![image](https://gyazo.com/2fec0c5d4432194e55b2b431d57dcf87/thumb/1000)
![image](https://gyazo.com/fb7080ddd68dc08d11793a01a950b1db/thumb/1000)
![image](https://gyazo.com/aa7de062b39a50e8ff5423599b12aec2/thumb/1000)


---
This page is auto-translated from [/nishio/Devinで4万溶かす方法](https://scrapbox.io/nishio/Devinで4万溶かす方法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.