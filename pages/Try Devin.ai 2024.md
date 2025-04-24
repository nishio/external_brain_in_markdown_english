---
title: "Try Devin.ai 2024"
---

from  [[Try Devin.ai 2025-01]]
Try Devin.ai 2024
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>Commentary by o1 Pro:.
Devin.ai is an "autonomous AI engineer" designed to assist in software engineering tasks, and features the ability to write code, test, and even generate PRs in conjunction with a GitHub repository. Here are some key points
- Automatic code generation and editing
    - He specializes in language and framework migrations, refactoring of existing code and small improvements, and can also help with PR reviews.
- Snapshot of environment construction and work history
    - Automatically launches Devin's dedicated workspace (VSCode, Shell, etc.) and saves a snapshot of the state in which the setup procedure was followed. The same environment can be recalled when the system is restarted, reducing the need to redo work.
- Experience: Tips and Challenges in Utilization
    - Advantage: It offers suggestions to get rid of a lot of chores and refactors at once. It is easy to automate tasks that are tedious for humans, such as "large-scale code modification" and "environment construction including testing.
    - Cautions: They often throw out large amounts of change PRs, and manual review may not be able to keep up with them. It is easy to generate incorrect code in projects where testing is not in place, and ultimately requires environmental maintenance and policy direction on the human side.


## testimonials
2024-12-28
![image](https://gyazo.com/1a674167f872c0237a359e64b391f239/thumb/1000)

![image](https://gyazo.com/f4d62a710b18ebc96d2b86fed201f0d0/thumb/1000)
Select the installation target from yourself and your organization.
![image](https://gyazo.com/fda9204d477f41cd478f15514ce15301/thumb/1000)
> Also includes public repositories (read-only).
- Maybe you basically can't write in public repositories?
    - It never happened.
- I'll leave it to nishio's ALL.

![image](https://gyazo.com/42a4a5a6e9906e2dbdf9cf9c17e3168f/thumb/1000)

---

![image](https://gyazo.com/ce5140d68c6ed834403ef96e3bc6d463/thumb/1000)
Perhaps a Slack Organization is needed?

![image](https://gyazo.com/65d4323d45bdc3c96c9b0b6302efaf2f/thumb/1000)
No, you can.

![image](https://gyazo.com/b05aed49f3405dba4b3e743313238dcc/thumb/1000)

What is Connect with Cognition Team?
![image](https://gyazo.com/673274c49271d0e1afb40bff5f00ec09/thumb/1000)
Uh, maybe a single channel guest to go into the support channel.
- ![image](https://gyazo.com/d2c00d8bd395f3cee75cb9986cf3a635/thumb/1000)
- Ah, Slack Connect.
    - [Connect with other companies in your channel using Slack Connect | Slack [https://slack.com/intl/ja-jp/help/articles/360035092414-Slack-%E3%82%B3%E3%83%8D%E3%82%AF%E3%83%](https://slack.com/intl/ja-jp/help/articles/360035092414-Slack-%E3%82%B3%E3%83%8D%E3%82%AF%E3%83%) 88%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%A6%E3%83%81%E3%83%A3%E3%83%B3%E3%83%8D%E3%83%AB%E3%81%A7%E4%BB%96%E7%A4%BE%E3%81%A8%E9%80%A3%E 6%90%BA%E3%81%99%E3%82%8B]
- ![image](https://gyazo.com/800d688e8a1c0ae93818dd2035f152c9/thumb/1000)
    - I don't know which one... I don't know who to invite, so I guess public.
    - ![image](https://gyazo.com/1c65953c2532fa75e84624f5db763378/thumb/1000)
    - ![image](https://gyazo.com/36be6960cacd68c0dc61d02cf7b3e25b/thumb/1000)
        - I've come this far and "need Slack Pro".
            - Is it necessary even for the recipients of invitations?
        - ![image](https://gyazo.com/7f0f8826e12a44bedfe77b36f2d58d87/thumb/1000)
        - ![image](https://gyazo.com/a966109744d38c918ab73aa2fab8789a/thumb/1000)
- It doesn't seem essential to try Devin to slack connect using slack pro, I think this is a contact with support.

![image](https://gyazo.com/eeda0b6d19affa72dba65e8725afc0d6/thumb/1000)
- I'm not quite sure what you're talking about.
- I wonder if it's in the documentation.
- [https://docs.devin.ai/get-started/devin-intro](https://docs.devin.ai/get-started/devin-intro)
    - [https://docs.devin.ai/get-started/quickstart](https://docs.devin.ai/get-started/quickstart)
- Think about existing repositories that are good for public access and not a problem for AI to scour.
    - [https://github.com/nishio/concatPages](https://github.com/nishio/concatPages) I'll take this one.
        - [[concatPages]]

![image](https://gyazo.com/5d0f6fdca9b0515919a7d2ce688787e4/thumb/1000)
- ![image](https://gyazo.com/8943c17cd10a50d429efb62de2768d37/thumb/1000)
    - Seriously?
    - VSCode is up and running in the REMOTE instance, this is going to be costly~w
- ![image](https://gyazo.com/1c2744c7f9e28a0cc97de6e1b5e73231/thumb/1000)
- ![image](https://gyazo.com/be4c6a89ea55f33f8e001d71a9d9579f/thumb/1000)
md

```markdown
Verifying correctness
- When verifying your code, you should run lint with `npm run lint` and auto-fix with `npm run lint -- --fix`.
- You should generally not worry about running the code or local testing. Prefer to use the tests that are automatically run in CI as a feedback loop for your PRs.
- Assume that you are not able to run tests locally unless a human has deliberately provided verifiably working instructions. Generic instructions for testing in the README often do not work since you may require specific environment variables or other machine setup to be able to properly run tests.
    - If you are asked to run tests, a local dev server, or otherwise interact with a running application, you should tell the human user to update your Knowledge with verifiably working instructions on how to run tests in your environment.
    - You should primarily rely on both human review and CI to verify that your code is functionally and stylistically correct
- If you have in fact been provided with verifiably working instructions on how to run tests in your environment, then the bullet point about not running tests locally is not relevant (and humans editing this note should feel free to update this section).

Additional Notes
- This repository does not appear to have any specific formatting, linting, or dependency management instructions
- When making changes, focus on maintaining consistent style with the existing code
- Since this is a Japanese repository, consider including both English and Japanese comments/documentation in your changes
```

interesting
- Since it says "Since this is a Japanese repository" even though it only specifies a repository, it must be generated by reading the contents of the repository.

![image](https://gyazo.com/d982209cb1ed5da4b18c8c879f70b6f9/thumb/1000)
- Ah, I see.
- You save the environment generated here as a VM image and start it up when given a task.
- That's why in Step 4, Set Up Your First Repository, I wrote
    - > My Workspace resets to a saved state for every new session.

![image](https://gyazo.com/35c339c21d03a1cd84033ae6d2a987ba/thumb/1000)
- Can you set up someone else's repository here?
    - I see your search is limited to nishio/ and below...
    - I can't even set up a repository for someone else to which I have access, so I guess I'll have to fork to my place first.

![image](https://gyazo.com/a7dd7d15a00fd35fe3c827e2156d0d93/thumb/1000)
- As you can imagine, a snapshot is saved after setup.

![image](https://gyazo.com/13ef150c78e241aaad864e1075736767/thumb/1000)

Instructions issued
> Proposed additional features
>  1: I want to include the open page itself in the textarea.
>  2: I want to put in clipboard when changing textarea.
>  Develop and promote each of these features.
add (e.g. annex)
> According to the instructions, exactly.
>  1: Fix: current should be at the top
>  2: When you fix it, update the README as well.
>  3: Can you self-merge?
PR made
[https://github.com/nishio/concatPages/pull/1](https://github.com/nishio/concatPages/pull/1)

![image](https://gyazo.com/2dc7e22018426da4029a909b21da0a1a/thumb/1000)

250 ACUs/month for $500, so 1 ACU is about $2.300, and 3 ACUs for this work, so $900.

![image](https://gyazo.com/0463d08ebc0ceae20cc4a62a2fcff165/thumb/1000)
- I'd love to see notes on what you've learned.

![image](https://gyazo.com/b5e8e8118c24575ca7087774abab3900/thumb/1000)
![image](https://gyazo.com/ecf107fa5c300f2b94317f0f49930d30/thumb/1000)
Maybe they'll charge you even while you're not SLEEPing.
- So you are starting up enough virtual machines that VSCode can start up.

Connecting other repo
Realistic and reasonably large sample
[https://github.com/nishio/anno-broadlistening](https://github.com/nishio/anno-broadlistening)
Squeaked in manual setup.
- ![image](https://gyazo.com/0145435695e03413906055854854db4d/thumb/1000)
This is exactly the kind of thing I want AI to do.
I asked him if he could do it, he said he could, so I left it to him.
> nishio: @Devin Can you have Devin do the setup itself, read the README, pip install, etc., and I'd like to record any problems, update the README, and take snapshots after the setup?
> Devin: Yes, you can automate the setup process and save a snapshot of its state.
I left it to you.
![image](https://gyazo.com/113ed709c5de0336858a0d55a74f520a/thumb/1000)
I'm changing Python from 3.12 to 3.10 as appropriate.
- ![image](https://gyazo.com/536f15ca6b70519180dc5fd12102f31d/thumb/1000)
    - That's one hell of a super big chanting spell.
![image](https://gyazo.com/43fad7295f3d61647f26b37294cf8f92/thumb/1000)
- I can see what you're thinking, assistant, and it's a lot safer than crowdsourcing and outsourcing to people you don't know.

Creating Snapshots
To create a snapshot of the current environment, you'll need to:
1. Click "Create machine snapshot" from the dropdown menu at the top right corner of Devin's Workspace
2. Fill in:
- - Snapshot name (suggestion: "anno-broadlistening-ui-dev")
- - Description: "Development environment for anno-broadlistening UI improvements"
- - Startup commands: cd ~/repos/anno-broadlistening && git pull
Please let me know once you've created the snapshot, and I'll proceed with the UI performance improvements for the cluster detail view.
![image](https://gyazo.com/4b8c6f1537313ce19ae670e7d3947675/thumb/1000)
I see, so Devin can't operate the admin screen himself, but he knows what to do, so he'll transfer it to a human.
- Not shown in Workspace but in Snapshot
    - ![image](https://gyazo.com/cd07eeab95266048d88a80cf1d74e043/thumb/1000)
Cost of environment setup, 4.74 ACU, about $1,500

![image](https://gyazo.com/86fef487aad3694227c6e3cefca9b9b6/thumb/1000)
- New employees who have learned to change their behavior depending on who they are dealing with.

AI-created PR
![image](https://gyazo.com/4a4a9ed1e5e6538d4daa587f7e204fdd/thumb/1000)
Review.
![image](https://gyazo.com/32a26ccb9d5b18b971b06a813d5dbdd5/thumb/1000)
This is certainly a careless mistake on my part, it's not good to RAISE when it's been REUSE and doesn't need to be re-executed.

---

22:00
Impressions after one day of use
![image](https://gyazo.com/4d1ea4ca45133d80c1c0050eaf893ac6/thumb/1000)
- AI is getting 4 PRs.
- Somehow some of them don't get PR.
- If you want to see exactly what it looks like, click here.
    - [https://github.com/nishio/anno-broadlistening/pulls](https://github.com/nishio/anno-broadlistening/pulls)
    - I'll close it eventually.

AI is implementing it at a very fast pace and my waiting for review is accumulating too much and bottlenecks...

I told Devin to look at the repositories and improve them as he sees fit, and he's doing a good job of the chores. w
- ![image](https://gyazo.com/eb37b2e535c19512136c9a6a86010242/thumb/1000)
- However, when I reviewed the PR that was created after this, I found that not only minor modifications were made but also some commonization of components between Desktop and Mobile. I can't merge the two.

Similar cases
- [https://github.com/nishio/anno-broadlistening/pull/5/commits/ddc155a820278924dd715b5c2de76023a6fe4cf7](https://github.com/nishio/anno-broadlistening/pull/5/commits/ddc155a820278924dd715b5c2de76023a6fe4cf7)
    - Changing `any` to `() => void` is welcome if the build passes.
    - I'm not sure about adding aria, or doing it in the same commit, but OK if it's a stand-alone.
    - Something about useEffect disappearing, what does that mean?
        - I want to understand what you are doing so please don't lump me in with all the other messy changes...

Q: Isn't Devin awesome?
A: Isn't it amazing? I've been reviewing a lot of pull requests and it's already 9pm and I haven't come to a single "okay, let's merge this" (...)
- It takes skill to make good use of it, and after trying many today, I feel that this is not the way to go for now. w
- I can't say which is worse, the human or the AI, but since we don't have automated tests on our side, the AI throws a bunch of untested code at me to review, and I die.
- Well, I'm not sure if it's possible without a little more bite and helpful instructions.
- Oh, the instruction to stop parsing sys.argv on your own and use argparse is about half fulfilling my expectations.

I was able to merge one code written by AI
- [https://github.com/takahiroanno2024/anno-broadlistening/pull/42](https://github.com/takahiroanno2024/anno-broadlistening/pull/42)

It's not like we can "just leave it all to AI" yet.
- Human beings need to do their best to "develop the know-how and environment to allow AI to create code that can be merged without modification.
- What we learned from today's experiment
    - I didn't want AI to hit OpenAI's API with tests, so I said, "You don't have to do it," which led to the mass production of untested code.
    - Need to document and test code what kind of changes should be tested, where to find intermediate data to test without cost, etc.
    - Progress has been made in allowing tests to be run on "natural language documentation" as well as "code".

![image](https://gyazo.com/06213dad5ed528b9355313d3cc4abf75/thumb/1000)

Devin says, "Why don't you add a feature like this? Devin says, "Why don't you add this?
I recommend implementing the optional --retry-failed flag because:
1. It provides explicit control over retrying failed extractions
2. It complements the force_cache improvements by allowing targeted retries
3. It helps users distinguish between "use cache but retry failures" vs "use cache for everything"
4. The implementation cost is low since we already have the status tracking in place
Would you like me to proceed with implementing this feature?

I'm going to deploy a web app.
![image](https://gyazo.com/8749d78b295e7a9f0a5fee1febb2e882/thumb/1000)


> [teramotodaiki](https://x.com/teramotodaiki/status/1872644869140971604) That's very interesting." I'm sure it's very interesting........
>  I wonder if Devin needs to have a communication like "please don't make these pull requests because it's hard for me to review them"... w
> [nishio](https://x.com/nishio/status/1872649270584922235) >"The type that is motivated but gets ahead of themselves and spins out of control."
>  That's it.
> [nishio](https://x.com/nishio/status/1872651578836148661) If I give them a sermon, they will divide it up, but they will try to use English.
>  ![image](https://gyazo.com/a17322d0997f4b1e90c3bcf98d12c3c6/thumb/1000)
> [teramotodaiki](https://x.com/teramotodaiki/status/1872654930978492766) Oh, he has the type of steel mentality that never apologizes! You have a good personality... I want to hire you too!
>  No matter how much I preach, my mentality is steel, so I have psychological safety!

Often fails to create pull requests
- Sometimes they succeed if you say, "Try again."
    - It's a mystery.
- I give up and git apply what you sent me in PATCH.

For today, it's like "try things out and experience" for once.
- From here, it's like reading more documentation or setting up a system that makes it easier for AI to work.
- [Introducing Devin - Devin Docs](https://docs.devin.ai/get-started/devin-intro)
- I read through the whole thing.


2024-12-28
When you're in the middle of doing a task and your boss comes up with a bunch of ideas, you forget the task you were originally doing (which it is).

Yesterday I was playing recklessly and neglectfully, so today I'm micromanaging.
- Actually, if we only consider short-term productivity, micromanagement may be more productive for both AI and humans.
- But doing so is harmful in the long run because it doesn't foster the ability to think spontaneously.
- AIs currently do not think spontaneously in the first place, so there is no need for supervisors to take care of opportunities for the growth of their abilities.

I see that the plan can be conditional.
- ![image](https://gyazo.com/98b8314931841fd32827af557af11c86/thumb/1000)
- Surely with the ability to write source code, a "plan of action with conditional branching" is possible?

Watching Devin work on the side, [[pair programming]].
- I feel that the ability to synchronously/asynchronously check the shell and VSCode of "people who are addicted to reading the current README" can be interpreted as a rather super-easy [[user test]].

It's verifiable with fluffy verification instructions.
- instruction<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - For large data sets, the data-aipubcom branch contains the generated results, which can be used for testing.
    - If you can test it correctly, you should get a scatterplot with lots of points
    - Are there many points on the scatterplot?
<img src='https://scrapbox.io/api/pages/nishio-en/Devin/icon' alt='Devin.icon' height="19.5"/>
> The scatter plots have been verified. A large number of points are shown clustered in different colors and the visualization is as expected. Specifically:.
> - Multiple color-coded clusters are shown
> - Each cluster contains many points
> - Thousands of points are visualized throughout the scatterplot
> We have confirmed that the visualization is functioning properly.
Have them document how to test how it works, useful.
- [https://github.com/takahiroanno2024/anno-broadlistening/blob/main/scatter/VERIFICATION.md](https://github.com/takahiroanno2024/anno-broadlistening/blob/main/scatter/VERIFICATION.md)


You have three layers of perpetuation.
- Development environment, create and allocate VMs from snapshots at the start of the session and discard them at the end of the session
- Snapshots, saved with a good setup.
- Knowledge, maintained across sessions and updated as appropriate

The source code is persistent on GitHub, but in practice, building the environment from there every time is too much overhead and wasteful, so I want to reuse the development environment.
On the other hand, if the development environment is a single environment or the user's environment is used as it is, there is a large disadvantage when the environment is destroyed by a misoperation that occurs with a high probability, so start from a "clean environment" every time.
There is a layer of "knowledge" that spans these various things and is a higher entity than individual sessions and projects, and as accumulation occurs there, it gradually becomes a better assistant.


Knowledge is stocked.
- ![image](https://gyazo.com/d30a982fc39a28d084efaecba2da3a5b/thumb/1000)
- Looks like they do a proper "past memory update" as well.
    - ![image](https://gyazo.com/8b306a39a0ab9229caac4833474f510f/thumb/1000)
    - They note something like "npm test is not properly maintained, so you need to open a browser to check" or something like that.


They put it in Advanced, but I prefer snapshot because it's easier to understand how it works.
- ![image](https://gyazo.com/4350a8a27023b46bb57982b30900c365/thumb/1000)
- Let the environment be built by specifying a snapshot.
- If it works, I'll take another snapshot of it.
- ✅


2024-12-29
After a one-thread exchange with Devin, Teramoto-san decided to sign a w
from Unexplored Junior Chat
- teramotodaiki
    - I'll buy Devin.
    - The experience was really like hiring one full remote engineer!
    - The work process was more proper than I thought it would be.　I would listen to the instructions, try different things, and then ask, "What do you want to do with these options? What do you do?
    - I think this is the kind of behavior you will be expected to exhibit when you intern, so I think it will be helpful to observe Devin's thinking.
            - [[I can see the thought process.]]
- nishio
    - You learn to communicate by watching Devin?
- teramotodaiki
    - I thought that's a big part of it. Nowadays, you can't learn anything without doing an internship or something. But if you hire Devin, you will be able to experience "the person who makes you work," and you will also be able to read all of Devin's thoughts, so I think you will have a better sense of "the person who receives the work.
    - Well, the way of working depends on the company, so of course there are some companies where the water doesn't match if you imitate Devin.
    - So, I think everyone should rent Devin while Nishio-san has extra credit. It is a rare opportunity...!
- nishio
    - Indeed. When crowdsourcing first came out in the past, I tried outsourcing work and thought that the experience of "deciding who to hire" was a great learning experience, but with the advent of AI assistants, everyone can experience the perspective of "the person who makes the work happen".

> [@teramotodaiki](https://x.com/teramotodaiki/status/1872967504060129336): Devin Observation Diary Day 0
>  [Devin's Observational Diary Day 0｜Daiki Teramoto](https://note.com/teramotodaiki/n/n00dde86ff676?sub_rt=share_pb)
Devin is very capable of creating README and test procedure documentation
- Some engineers might look at the article and think, "$2,000 to update the README?
- Documentation is often neglected, but it's sometimes the first thing an AI assistant or human newcomer without actual project-specific knowledge needs when they join a project.
- From a manager's perspective, that maintenance is important, and I think it would be beneficial from an organizational perspective to be able to outsource it to Devin, considering whether a $2,000/hr engineer can do it in an hour, or whether a $8,000/hr engineer can do it in 15 minutes.
- However, at this point in time it is being reviewed by senior engineers and probably will not be a completely unattended operation in the future. Because there is information that is not in the language and is only available to the team members. I think it depends on the project how the cost of this part of the project comes on board.
- I think the more projects that have a well-developed rookie onboarding, testing and backlog, the easier it will be for AI assistants to operate.

I had them produce a document in English.
> [nishio](https://x.com/nishio/status/1873157831073116640) We, anno-team, have been actively developing anno-broadlistening, based on the source code of @AIObjectives talk-to-the-city-reports. In the spirit of open source, I believe it’s important to contribute our updates back to origin. However, our team is limited in time and resources, so we haven’t been able to provide detailed feedback or documentation in English until now. Today, AI created a document that highlights the differences between our Japanese version and the original English version. I hope this will help bridge any gaps and make collaboration easier for everyone.
>  We, the anno-team, have been actively developing anno-broadlistening based on the @AIObjectives talk-to-the-city-reports source code. In the spirit of open source, we believe it is important to FEEDBACK updates to ORIGIN. However, due to our team's limited time and resources, we have been unable to provide detailed feedback and documentation in English. Today, AI has created a document that explains the differences between the Japanese version and the original English version. We hope this helps bridge the gap and make collaboration easier for all.
>  [https://github.com/takahiroanno2024/anno-broadlistening/blob/main/DIFFERENCES.md](https://github.com/takahiroanno2024/anno-broadlistening/blob/main/DIFFERENCES.md)
AI seems to be good at this kind of thing.


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The giving of any → () => void in TypeScript or type annotations in Python is a good thing if it is then tested and passes, but if it is mixed in with other semantic changes in the implementation, it is hard to review, so please separate the commits.
<img src='https://scrapbox.io/api/pages/nishio-en/Devin/icon' alt='Devin.icon' height="19.5"/>Noted. Type annotation changes should be combined in a separate commit from semantic changes.
![image](https://gyazo.com/3350bf42e0e4cfe9b3baca32fdfcec8b/thumb/1000)


I feel like a chess player playing multiple sides.
- I think 2 parallels is about the line I can do consistently.
- Well, it's more scaled because only one pair programming driver can do it.

2024-12-30
![image](https://gyazo.com/0e51ecb063f192eefc2b461c144e5ff7/thumb/1000)
- I understand from the documentation, etc., that "aipubcom" means to use a dataset in the dataset-aipubcom branch that has been run through the analysis process.
- Accumulated knowledge of the project allows it to work as intended with short instructions

But if you pay $500/month and set up a nursery called "Devin", you can just "take notes by throwing them to Devin", and they will become more detailed and concrete on their own.
- Prototypes are created for quick testing and discarding, but in reality they are too wasteful to discard, or the "engineer who discards the written code" may feel dissatisfied when he entrusts it to someone else.

> [takahiroanno](https://x.com/takahiroanno/status/1873574200033890656) I'm doing Devin observations around @nishio and I feel the paradigm of how engineers work is changing. I feel the paradigm of how engineers work is changing.
> [takahiroanno](https://x.com/takahiroanno/status/1873689975470059563) I did a little work with him on Slack with engineer AI Devin ($500/month). This is awesome. There's still a lot of stupidity in it, but it's great. the future workplace collaborating with AI agents was already a reality..!
>  ![image](https://gyazo.com/5105fb5ab1981869c08c1ab7bbf2b684/thumb/1000)![image](https://gyazo.com/db6213db907242692ce2bef23ff14e49/thumb/1000)![image](https://gyazo.com/ae4cebf6ad69f9ca4f4e7f8c0be5463a/thumb/1000) ![image](https://gyazo.com/7a5034becb2ac1bf6cf86d67ed135eb7/thumb/1000)
> [takahiroanno](https://x.com/takahiroanno/status/1873690019346755630) I feel like this new hire is a crazy asset in less than a year.

> [takahiroanno](https://x.com/takahiroanno/status/1873693465890234831) Notes on what I thought as my first impression of using Devin
>  ・ Still an idiot (failed to create PR)
>  ・But where it is smart, it is smart.
>  ・Reminiscent of the behavior of a highly educated, peppy, new graduate feeling.
>  ・I like that they are very close to the media that engineers usually use (Slack and GitHub). I like that I don't have to go to special pages like ChatGPT myself.
>  ・Agents in particular work for several tens of minutes, so it is a good match with the chat tools they usually use (problem of not being aware of notifications).
>  ・If you give an order on a chat tool that you normally use, it's nice to have a human team member come in naturally to the communication, like "Devin is not good at this.
- In the thread that Yasuno-san started this time, there were 4 people + AI, and I learned a lot that this way of working will come in the near future, it was worth doing [[Meeting to see Devin]].
>  ・I like the fact that knowledge is acquired through dialogue (I think this kind of mechanism for accumulating detailed knowledge through user dialogue can be used by all types of agents)
>  - I'd like to see a Gmail version of Devin. I think it could be done rather quickly. gmail replies and the like are an accumulation of the above detailed findings (return to Mr. A with xxxx) and so on, so the automatic accumulation of findings could work.
>  I thought there was a big challenge of how to teach tacit knowledge to AI. I thought there was a big challenge of how to teach tacit knowledge to AI, but I was glad to see that the solution is to teach AI naturally through on-the-job training by integrating chat tools and team collaboration.
>  ・It is also good to see inside Devin's head (or rather, desk) by looking inside the pages on the special Devin app. I feel that the ecosystem is getting ready; I can see Terminal, Editor, and Browser, and I can also intervene!

> [takahiroanno](https://x.com/takahiroanno/status/1873694182617104721) I realized that using AI agents is a team game, not an individual game.
>  Productivity can vary tremendously depending on whether or not the organization has workflow and data in place to use AI.
- [[Using AI agents is a team game]].

Sequel to Mr. Teramoto's
[Devin Observation Diary Day 1｜Daiki Teramoto](https://note.com/teramotodaiki/n/nd2f47ab20c26?sub_rt=share_b)

Progress of anno-broadlistening
- I was able to do it!
- ![image](https://gyazo.com/e1e3c3830bc4cc856f047b551bdbd317/thumb/1000)
- Ability to switch color sets according to color vision characteristics
- Mr. Anno talked about the requirements in the chat, Devin took the code that he had worked on for a while but could not complete and had o1 Pro debug it, and then gave the Issue with o1 Pro's comments to Devin to fix it.
- [https://github.com/takahiroanno2024/anno-broadlistening/issues/47](https://github.com/takahiroanno2024/anno-broadlistening/issues/47)
- If the Devin can no longer complete the task on his own, he can branch or write in an Issue to the point where it is done, and o1 Pro or human can review and advise on it.


> [nishio](https://x.com/nishio/status/1873740723771846874) "An engineer who responds to chats 24/7 in a minute, who makes an execution plan and executes it even when miscellaneous ideas are thrown at him, and whose plan, console and editor he is working on, The time when you can hire an engineer who works without the human right to "see your browser at any time, and it will be recorded and shared with a permalink" for 1,200 yen per hour.
> [nishio](https://x.com/nishio/status/1873741204229341562) I'm just saying that the change in the supply/demand balance for engineers over the next year is many times faster than I thought it would be last year.
> [teramotodaiki](https://x.com/teramotodaiki/status/1873879852308455930) It seems to be a case-by-case basis as to whether Devin is a substitute or complementary good for engineers.
>  The person who manages Devin still needs to be an engineer for now, so there is going to be a new demand for "engineers who can deliver results using Devin"


I had o1 Pro make a list of all the things I had Devin do in the last 3 days.
- [https://gist.github.com/nishio/e86ab242fed7881620f8006712f013e0](https://gist.github.com/nishio/e86ab242fed7881620f8006712f013e0)


- [[Conversations and Writing Metaphors]]
- After all, "the time it takes to get a response back" and "what range of tasks can be done with what quality" are understood by using the aircraft, the aircraft before use does not match the actual distribution
- The ability to correct for deviations from those expectations is [[Usability Skills]].
    - When I wrote the "[[I don't expect others to do it.]]" diagram many years ago, I was assuming it was human, but it is equally valid for AI assistants.


I'm just speculating here, but I'm wondering if the reason why you can't give a PR is because you were trained for "development in a private corporate organization" and are unfamiliar and confused with the case where you have a public repo forked in OSS at hand.
> (Devin) Currently, there are two options
> 1. created under nishio's personal account (my-cosense-scripts)
> 2. created under nishio organization (nishio/my-cosense-scripts)
> Which location should I create a repository in?
I'm still confused about the account not being an ORGANIZATION.


2024-12-31
Devin sometimes works hard at sterile trial and error when the test doesn't pass.
- I look over and say, "Let's stop for now.
- I try very hard but am sterile because the appropriate action to solve the problem I am in is not included in the candidate options.
- Once again, I had the feeling that humans are the same way.


While I was watching Kohaku, he was implementing it the whole time.
- [https://github.com/nishio/my-cosense-scripts/commits/main/](https://github.com/nishio/my-cosense-scripts/commits/main/)


> [teramotodaiki](https://x.com/teramotodaiki/status/1873883310671487184) I need Devin Enablement for this.
>  Understand the characteristics of Devin to improve the efficiency of Devin's development environment.
>  For example.
>  Properties:Devin cannot log in using OAuth.
>  Maintenance: provide a means of authentication for Devin (likely to be diverted if E2E testing is available).
>  Platform team because of its commitment to development productivity? s role?
> [teramotodaiki](https://x.com/teramotodaiki/status/1873883315482353722) Devin's development productivity is
>  ・Easy to track
>  ・ Easily converted into money
>  ・Easy to improve
>  so I have a feeling it will be a very hot topic in a moment!


> [teramotodaiki](https://x.com/teramotodaiki/status/1873769338232320195) "I want you to tell me what you're doing verbatim, like talking to yourself," I told Devin, "thinking out loud style" and he wrote it down. That's it! Vibes match~!


I've had no problems with PR in my newly created repository.
- [Commits · nishio/my-cosense-scripts](https://github.com/nishio/my-cosense-scripts/commits/main/)
- On the other hand, another repository I forked after that failed PR easily, so I guess I'm not good at handling forked repositories.


> What happens if I don’t use my full ACU capacity?
> For Personal and Team plans, the ACU capacity included with your subscription resets each billing cycle. However, any additional ACUs you purchase will remain available as long as you have an active subscription.
At any rate, I found out that the additions will carry over, so I decided to add 100 ACUs.

When I started this project ([[Meeting to see Devin]]), I felt like "I'm not sure if I'll use up all my credits alone" and "It would be more beneficial to share than to have an excess, and it would be beneficial if multiple people could see and discuss the same thing", but after using it for a week or so, I've found that over the next month or so I feel like I will continue to pay the bills and use up the default 250 ACUs.
We need to think about how and when to dismantle this project in the future.


I'd rather create a Google account for Devin, or rather, I'd rather have my own Google account to read my GMail.
- I manipulated Devin's browser to get past the reCaptcha, but it played me back with an error with no explanation, "This is suspicious.
- Trying to do so could ban the entire associated account, I give up.
- If you want AI to read your mail, you might as well set up a mail server that can read it and forward it.
    - You don't have to do it yourself, soon Google will do it or a third party will provide it.


I've come to a style of using one instance for a long time because creating a large number of instances in parallel would ruin my task management, but then scrolling through the threads on my phone would be a pain...


Interesting task management document written by Devin
- ![image](https://gyazo.com/dff8c7759b709e654d4eeff0692cb10d/thumb/1000)
- I had this as a private repo, but I'd prefer to be able to make it public, have it separated.
- > I have reviewed the system and data structure. Please allow me to confirm the following points regarding the separation
- >  1. The docs in the tasks directory (task_format.md, system_overview.md, etc.) are important documents that define system specifications. Should these remain part of the public system?
- >  2. test_advanced.yaml appears to be used as test data. Should this remain in the public repository as a file needed to test the system?
- >  3. backlog.yaml contains the actual task data, which should certainly be moved to a private repository, but we would like to hear your thoughts on the other files.
- Great for checking, I was going to publish 1 and 2, but it is indeed unclear to what extent the "system" is a "system".



---
This page is auto-translated from [/nishio/Devin.aiを試す2024](https://scrapbox.io/nishio/Devin.aiを試す2024) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.