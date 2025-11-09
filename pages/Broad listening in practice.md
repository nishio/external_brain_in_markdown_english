---
title: "Broad listening in practice"
---

Discussion between [[Takahiro Yasuno]] and [[Audrey Tang]] at [Funding the Commons Tokyo 2024
- [[FtCTokyo Day2]]

[https://youtu.be/k6bZ2qayBQA](https://youtu.be/k6bZ2qayBQA)

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>(Full translation from YouTube transcript)
Hello, thank you for joining our session. My name is Takahiro Yasuno. I ran for the Tokyo gubernatorial election this year. Today, Audrey Tang and I will talk about the practice of (Broad Listening, Extensive Listening). First, I will give a 5-10 minute presentation in which I will discuss this year's election and how I used technology to innovate in that election. After that, I would like to move on to a discussion with Audrey Tang. You are welcome to interrupt with a show of hands at any time during the presentation if you have any questions.

First of all, let me briefly introduce myself. My name is Takahiro Yasuno. Currently, I have three jobs: first, I am a software engineer; second, I am an entrepreneur, having founded two startups so far; and third, I am a science fiction writer. The third is a science fiction writer. I have published two books with Hayakawa Shobo. All three jobs have one thing in common: using technology to create the future.

Next, I would like to discuss this year's election. Fifty-six candidates ran in this election for Governor of Tokyo in 2024. With so many candidates, I held a press conference in early June, and the initial media reaction was very chilly. The initial media reaction was very cold, because I was not a celebrity, and although I was known in the technology industry, I was completely unknown to the general public. The media reaction was, "Who is this nerd? and "What's with the long hair?" I was not a well-known person in the technology industry. Some TV producers even told my wife directly.

But as a result, I received 150,000 votes. It was very gratifying to receive so many votes despite the fact that I am not a celebrity. The winner of this election was Ms. K. She is a well-known politician who was also the secret guest of this event. However, I achieved this result with no name, no political experience, and no organization. This score is the most votes ever received by an inexperienced and unorganized candidate and is a historic record in an election with more than 30 candidates in the Tokyo gubernatorial race.

Nagatacho, or "Washington DC" in Japan, was very surprised by this result. Here is what we did and how we achieved this result.

The main concept we worked on was "broad listening," which you can see on the slide. This slide was created by Mr. Nishio, a graphic designer. He is also a very talented software engineer, and this slide was very well received by the media community. The idea is that in the past, technology made it possible to communicate one's thoughts to a large number of people, in other words, "Broadcasting" was the mainstream. However, after the Internet and smart phones became widespread, people began to do the opposite: each person would transmit his or her thoughts to someone else.

There is a challenge in this situation. That is, it is difficult to understand and grasp all the opinions of many people. However, in the 2020s, technologies have finally emerged to summarize these large amounts of information. For example, Large Language Models (LLMs) can process natural language and can thus process large amounts of information efficiently.

In past elections, "one-way communication" in which candidates unilaterally transmitted their ideas was the norm. However, we have changed this to "two-way communication" by utilizing "broad listening" technology.

Next, I will describe the initial system architecture for this election. I showed Audrey Tang a simple version of this system before the election and asked her for some advice. The system consists of three major parts. Listening, Brush Up, and Delivery.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I think the original Japanese word was "kiku, migaku, tsutsurae," so that's what I've used below.

For the first "listening" part, we used a tool called "Talk to the City". This tool was developed in the US and has the ability to process and visualize comments written in natural language. We collected data from X (formerly Twitter) and YouTube, and through this tool we were able to get a broad picture of citizens' opinions. Using this tool, we were able to understand at a glance the vast flow of comments related to the elections.

Next, for the second "Migaku" part, we set up a web forum to discuss policy using GitHub. since GitHub is highly customizable, we implemented an AI using GitHub Actions to facilitate the discussion. The AI detected and eliminated hate speech and inappropriate images, detected and notified duplicate issues, and provided other features to facilitate discussion efficiently.

This process helped us clarify issues and create better policy proposals. Over the course of the election campaign, we discussed 206 issues and merged 74 pull requests. This rapid policy update was not seen in any previous election.

For the third "communicate" part, we utilized CI/CD (Continuous Integration/Continuous Delivery) technology as a way to deliver policies to citizens so that the latest policies are always available to the public. This allowed us to create a system in which the website is updated in real time.

In addition, AI-based video delivery technology was also introduced. Specifically, we adopted a format in which an AI avatar explains policies on YouTube Live and responds to viewers' comments in real time. In addition, in order to make it accessible to people who do not use YouTube Live, we also established a system that allows people to ask questions to the AI avatar over the phone using Twilio.

As a result, the AI avatar "AI Anno" responded to over 7,500 questions in total, 7,400 via YouTube Live and 100 via telephone. This is a scale that the physical Anno itself could never handle. This mechanism enabled interactive communication with citizens and explored a new form of democracy in election campaigns.

Finally, we decided to open source the entire system and make our findings publicly available. Through this endeavor, we aimed to make this system available to all future candidates.

The book "Plurality" was the starting point for this endeavor. I am grateful to have learned about this book through Audrey Tang and Ms. Nishio who translated it for me.

These are the contents of my presentation. From here, I would like to pose some questions to Audrey for further discussion.

---

Yasuno: First question. How would you rate this attempt?

Audrey:
I think this is an excellent proof of concept. The traditional approach required a large number of staff to achieve real-time democratic input gathering. However, in this attempt, a small team with a clear process has replaced the roles of moderator, facilitator, and summarizer by utilizing language models and AI. This greatly reduced the large manpower previously required.

Of particular importance is the creation of a system that uses AI to reflect citizens' voices quickly and accurately. If this had started years ago instead of months ago, it could have been a much more powerful political move. This is just the beginning of such an endeavor, but I believe it has tremendous potential.

Yasuno:.
Thank you. You mentioned that "this is no longer science fiction," and I would like to ask you to elaborate a little on this point regarding this attempt.

Audrey:
That's right. This is no longer the future, but something that is possible with real technology, and I think your role as a science fiction writer is to show people an adjacent possible future, a near future that can be reached with a slight change in direction. It is important to present provable concepts so that people can recognize that this is feasible. I think this attempt was an important step toward that end.

Yasuno:.
Thank you very much. Moving on to my next question. What are your thoughts on the current limitations of digital democracy, as you feel there are some limitations to this system?

Audrey:
We have talked about this a bit, but a major limitation is that many people are not yet familiar with this system. For example, if you use GitHub, you may be asking yourself, "What is GitHub? Why should I use this?" The response is often "I don't know. These technical hurdles exist.

In addition, the current system primarily focuses on one-on-one interactions, i.e., candidate-citizen dialogue. However, in the field of political mobilization, small group interactions are critical. Current technology allows for one-on-one conversations with chatbots and AI, but does not yet have sufficient mechanisms to support real-time discussions in small groups.

As an experiment in Taiwan, we invited about 10 people to a video chat session for real-time discussion. This method makes it easier to generate new ideas by hearing other people's perspectives and allows for higher quality discussions. This is the main limitation at the moment, as the current one-on-one system makes this kind of interaction difficult.

Yasuno:.
I see...you said that a group of about 10 people is good...can you tell us why?

Audrey:
In a real-life example in Taiwan, SMSs were sent to randomly selected phone numbers, 450 people were extracted and divided into 45 rooms, with 10 people in each room for discussion. The groups thus constituted serve as a "mini-public" that statistically reproduces the balance of gender, region, and occupation.

In a group of about 10 people, discussions tend to be very lively. The ability to hear the opinions of other participants and gain new perspectives makes for high quality dialogue; one-on-one discussions tend to have a lot of overlap, but within a group, opinions are naturally complementary. This is the advantage of small groups.

Yasuno:.
Very interesting. Moving on to the next question. In terms of the technological aspect, I feel that we have not yet reached a perfect solution. What technologies do you think are currently lacking to make digital democracy a reality?

Audrey:
Currently, many of the technical parts themselves already exist, but the challenge is that they are not integrated and not in a form that is easily accessible to everyone. For example, using "Talk to the City" requires customization, and there are technical burdens such as adjusting Git's Large File System (Git LFS). This difficulty in setup is a hurdle to the spread of digital democracy.

However, I believe that over the next year or two, the impact of AI on software engineering will eliminate many of the initial setup challenges and make it easier to build DIY systems. This will make it possible to experiment with such systems at the school, workplace, and individual level, and I believe we will have a truly digital democracy. Until this becomes possible, we will remain in the "adaptive government" phase, as we are now, where government and tech-savvy candidates take the lead.

Yasuno:.
I see, so the key is the diffusion of technology. Now, let me move on to my next question. How do you think this experiment can promote political participation among the younger generation and people who have not been interested in politics before?

Audrey:
This is a very important point. Today, many people are not interested in politics, especially the younger generation, which has a hard time seeing political issues as their own business. However, elections can be very effective as an opportunity to draw attention. Even people who normally have no interest in politics may temporarily turn their attention to politics through elections. I believe that leveraging this "attention" is one of the keys to advancing digital democracy.

For example, by using digital technology to realize a new form of election campaigning, as in this case, we can create an opportunity for more people to become involved in politics. And by expanding this method not only in Tokyo but also at other levels, such as local elections, even more people will become involved.

Yasuno:.
Certainly, elections are a high-profile occasion. And as a result, more people may become interested in politics, right? So, after this experiment, what improvements or expansions do you plan for the next election or project?

Audrey:
This attempt was a very good "demonstration". If the first demonstration is successful, it will be cost-effective and easy to implement next time. And more and more people will be using this method as a new mobilization tool.

For example, from an economic standpoint, this is a very efficient way to do this. Not only is it an incentive in itself to try out new technologies, but it is also a cost-effective way to get the message out to more people. We believe that this economic perspective will drive even more people to experiment with digital democracy in the coming years.

Yasuno:.
That is a very practical perspective. What do you see as the future social impact of the spread of digital democracy?

Audrey:
I believe that as digital democracy spreads, citizens, including the younger generation, will be recognized as "proponents" rather than "protesters". Protests are a reaction against the status quo, while proposals represent new possibilities. This difference is significant.

For example, when I was young in Taiwan, there was a mechanism for the younger generation to participate as "reverse mentors" in the cabinet. By showing them new possibilities, they added diverse perspectives to the traditional cabinet discussions. In this way, I believe that the greatest potential of digital democracy is for the younger generation to be recognized not as mere protesters but as "demonstrators" who show the future.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Related: [[The difference between a protest and a demonstration]].

Yasuno:.
That is a very interesting perspective. What do you think is important to further expand digital democracy efforts?

Audrey:
In order to further expand digital democracy, it is very important that the system be easy to use. Currently, the system requires a lot of technical knowledge and preparation, which makes many people hesitant to use it. However, as technology advances and setup becomes easier, it will be possible to try this system in all settings, including schools, workplaces, and communities.

What is also important is that this system not remain just a government-sponsored project, but become a tool that can be used by anyone. To achieve this, it is necessary to integrate existing tools and create an environment in which users can utilize them without feeling technologically burdened. Once this is achieved, digital democracy will become "true democracy" spread not only by governments and candidates, but by citizens themselves.

Yasuno:.
Certainly, simplification of the technology is the key to widespread use. Now, a final question. How do you think these digital democracy initiatives will affect Japanese politics and society?

Audrey:
In Japan, I believe that this initiative will play an important role in triggering the younger generation's interest in politics. In particular, it is hoped that a "proposal-based" political culture will emerge, overcoming the traditional distrust and indifference toward politics and showing new possibilities.

These digital democracy methods can also be applied to local governments and smaller communities. By incorporating them into decision-making and policy formulation at the local level, as well as in large-scale elections, more citizens will be more likely to participate. And as these efforts spread, citizens' trust and interest in politics will increase, leading to a healthier democracy.

Yasuno:.
Thank you for your excellent answers. We appreciate your time today and had a very fruitful discussion. I look forward to continuing to work with you as we move forward with digital democracy.

Audrey:
I, too, salute you for the wonderful initiative you have realized. Let us continue to learn from each other and move forward in the right direction.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>The translated text is natural as far as the text is concerned, but I haven't compared it with the video, I think there was a question from the audience or it's recognized as a question by Yasuno-san, I'll check later.
---

> [nishio](https://x.com/nishio/status/1818130802976465055) We @pluralitytokyo just published the video of the session "Broad Listening in Practice" of @audreyt and @takahiroanno in Funding the Commons Tokyo 2024 #FtCTokyo #Plurality
>  [https://youtu.be/k6bZ2qayBQA](https://youtu.be/k6bZ2qayBQA)
>  Created by @leonelkigopfert

> [nishio](https://x.com/nishio/status/1818129845148385378) Video of #TakahiroAnno @takahiroanno and Audrey Tan @audreyt in conversation at Funding the Commons.

> [yaephone](https://x.com/yaephone/status/1818834385623195988) Talk session with Audrey Tan and Takahiro Yasuno, 5th runner-up for Governor of Tokyo!
>  From around the 28 minute mark, Audrey's impressions of the recent gubernatorial election are also included.
>  It is too exciting that the digital democracy exchange between Japan and Taiwan model is about to start in earnest...!
>  [https://youtu.be/k6bZ2qayBQA](https://youtu.be/k6bZ2qayBQA)
>  ![image](https://pbs.twimg.com/media/GT3MO3FXAAAh3it?format=jpg&name=medium#.png)



from  [[Diary 2024-07-12]]
anno+audrey
> [takahiroanno](https://x.com/takahiroanno/status/1811708071023911254) I will be speaking with Audrey Tan at Funding the Commons Tokyo on July 24-25!
>  ![image](https://gyazo.com/c523cd124f392c5506d91f457bf64dbb/thumb/1000)
>  >[0xtkgshn](https://x.com/0xtkgshn/status/1811640870216913069)
It had over a million views, wow!

- [[positive externalities]]
    - [[network resources]]
    - [[Connecting creates value]]
        - If you can get [[attention]], people will try to connect because there is value in connecting, and it will get bigger and bigger.
            - [[Rolling Snowball]]
                - [[reproduction on an enlarged or expanded scale]]
                    - [[Expanded reproduction in social capital]]


2024-07-25
![image](https://gyazo.com/1aa79b0427a0199f1b8d9adbd2cb1ff4/thumb/1000)

![image](https://gyazo.com/9c1b0be11ff79791336b422cba73d2a6/thumb/1000)



[[Plurality in Practice❌]]
- [[Takahiro Yasuno]]

---
This page is auto-translated from [/nishio/Broad listening in practice](https://scrapbox.io/nishio/Broad listening in practice) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.