---
title: "Preparation for Omoikane Study Group"
---

I put together materials for a one-hour internal study session while conversing with ChatGPT.


I did it in [[Omoikane Project]] because I thought it would be nice to have interactions with other members, but no interactions occurred, so I copied it here as well.

from [/omoikane/preparation for Omoikane study group](https://scrapbox.io/omoikane/preparation for Omoikane study group).
Preparation for Omoikane Study Group
- Next Friday at noon, it's my turn to speak at an in-house study session, so I'll talk about the Omoikane Project.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - This can be interpreted as a task with a deadline to "tell people about the project" and "create materials for it".
    - I thought it would be an interesting topic to see how GPT could assist with this task, so I'll give it a try.
    - Comments and impressions are welcome for all locations. The chat logs will guarantee the timeline of the experimental logs, so we'll write here in a Scrapbox-like mess.

# initial chat
[chatlog1](https://chat.openai.com/share/68fa90a6-5d7a-4325-aeb2-d181338bcfeb)
- > I'm planning to explain at a Cybozu internal study session about software implementations such as the Omoikane project and Komorebikagami that I've been working on recently. You, as the assumed audience, are welcome to share your thoughts with me and ask questions about what you don't understand.
- Included the contents of the slide explaining [[Generation AI as a research and writing support tool]] as an explanation of Omoikane itself.
    - [[Project to build a platform for collecting feedback on "Komorebikagami]]
    - I thought I should put it in and explain what it would lead to in the future, because I'm not sure about this at this stage at that time.
    - > "If we can collect a lot of information for and against by "komorebikagami" [[community AI]], it will help improve [[community AI]].
            - [[Building Community-Centered AI" Project]]
            - Breakdown [[Scrapbox-based AI chat creation project]].
                - The reason why I brought this up is because the most recent project I did, "AI writing to Scrapbox," is classified in this category.
                - Ah, yes, notice: not only abstract or future talk, but I want to see a good connection between that and what has already been achieved or is being implemented.
- They asked me three questions at the stage where I told them about Omoikane.
    - I expected an immediate answer to this to get lost before we got to the Komorebikagami story.
    - So, instead of answering the question directly, we first shared the entire current
        - This allowed us to expand from "Omoikane project and software implementations such as Komorebikagami" to "Scrapbox-based AI chat creation project" without getting lost.
    - I recognize this shift in thinking as "switching from [[depth first search (search algorithm in AI)]] to [[breadth first search]]" in the metaphor of information science.
        - Maybe a good explanation as to how to use it would be nice.
- I had them create a summary for the recap and made the chat loosely coupled.

## answer the generated questions
.
- What are the specific ways in which AI will assist in the Omoikane project? For example, in what areas will AI assist with plot generation, character development, dialogue creation, etc.?
    - General Purpose, so I'm trying different things.[[人々による探索的研究が現場で起こっている]]<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - Personally, I like the use of having a near-future science fiction plot created, cost-effective.
            - This is because I consider "effectiveness" to be "prototyping".
        - Another usage is "[[Explanation for those unfamiliar with Japanese culture]]."

- What are some specific insights or lessons learned from the science fiction stories you have written? Can you give specific examples of how these stories make you think about the future of AI?
    - [[story of protagonists with different ideas acting from the same situation]].
    - In a setting where local government has gone digital due to a lack of manpower, we created a story of those in favor of it and those against it.
    - [[ChatGPT wants to make it a good story]] has had a positive effect.
        - At first I subconsciously thought that older people who resist change are unhappy by their choice.
        - When I saw that ChatGPT generated a happy ending with that constraint, I realized I had an [[unconscious bias]].

- What are the main benefits of using AI to create narratives? And what are the biggest challenges in this project?
    - To create a near-future science fiction story is to start from the current situation and create a prediction of the future by connecting small steps that "such a thing is likely to happen.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - (I'm not talking about [[its value as an entertaining novel]] here.)
        - Some people are not good at making these future predictions in the first place, and even if they could make them, they would make narrow predictions due to implicit bias.
            - Like a forecast circle in a typhoon forecast
        - Mechanical assistance here can reduce costs.

- What are the specific goals of the "Comorebikagami" project? What new experiences do you aim to offer users?
    - Collecting subjective data from a large number of people.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- What parts of Polis do you feel need improvement? What specific improvements do you plan to make?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - First, there is little affinity for social networking.
            - There is no ability to share the questions themselves, and the questions are randomly shuffled, so even if someone has some strong opinions, they can't spread the word.
        - Second, reward feedback is weak.
            - After you have voted on a few cases with the visualization displayed, you will get feedback that your icon is moving.
            - Visualization experience is difficult to control.
            - The voting feature on Twitter allows you to see the results with one click, which is better as a reward.
- What are the main technical challenges in implementing the platform?
    - No particular technical challenge at the moment, rather Polis is facing a technical challenge with real-time updating of the cluster display.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - Need to secure a server to keep computing
        - The fact that its server is a Clojure implementation is also troublesome.
- How will the information for and against collected by the "Komorebikagami" platform be used to train the "Community AI"?
    - AI-generated answers are easily voted good or bad by community members<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - Disagreements create opportunities for discussion.
        - If there are more "bad" responses, that information can be included in the training data to train the AI to behave more favorably.
- How will the Scrapbox-based AI Chat Creation Project use Scrapbox data to train AI chatbots?
    - Make it a vector index and hang it on the prompt when generating responses.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- You mentioned that "Community AI" understands and expresses the issues of individual communities.
    - The "atmosphere" or "consensus" of the community has been vague and elusive<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - It becomes something that we can actually ask questions about.
        - Community members can challenge the "community atmosphere" without taking social risks
            - "I don't understand what you mean when you think SF prototyping is useful?" And so on.
            - The AI's response to this will generate a lot of discussion about "yes," "no, not enough words," or "no, it's not."
            - Discussions start with conflicts of opinion, but Japanese culture represses the creation of conflicts, and it is useful to reduce the psychological cost of this step by supporting AI.

# chat2
## generate more questions in response to previous question answers
.
- What specific AI techniques does the Omoikane Project use to generate science fiction? Also, do you have any criteria for evaluating the quality of the stories generated by AI?
    - Specifically, throw a prompt to ChatGPT<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - I better actually show them.
    - Quality of AI-generated stories.
        - <img src='https://scrapbox.io/api/pages/nishio-en/niryuu/icon' alt='niryuu.icon' height="19.5"/>I personally don't care about quality.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
            - The "[[Prototypes]] should not try to improve quality."
                - [[Bad Perfectionism]] keeps things in the hands of individuals without being shared.
                - [/nishio/bad perfectionism](https://scrapbox.io/nishio/bad perfectionism)
                    - >  To stop producing anything because you think you have to produce things in a perfect state from the beginning.
                    - >  It would be better to first produce something of low quality and then improve it, but I raise the hurdle in my own mind and think, "This is not good enough.
                - [/nishio/myopic perfectionism](https://scrapbox.io/nishio/myopic perfectionism).
                    - > Most people who think they are perfectionists[[myopic]] な [[perfectionism (psychology)]] だと思う<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
                        - > Perfection is not achieved by "myself alone" but by "[[Massive feedback]]".
                        - > But you are delaying the release of the work by insisting on "short-sighted perfection" by "yourself alone," and you are forcing the work into a state where you cannot get "feedback from many people.
                        - > "I'm trying to be perfect," he says, "but I'm getting away from perfection.
                            - [[authorship]] and [[the desire to possess]] get in the way.
                - [/nishio/good-ideas-inspire-people-around-you-and-start-growing-yourself](https://scrapbox.io/nishio/good-ideas-inspire-people-around-you-and-start-growing-yourself)
                        - Metaphor for [vegetative growth
                        - Pulling does not grow, create an environment and wait.
- How will the Polis voting function be improved and what new features will be added in the "Komorebikagami" project? Also, what specific techniques do you have in mind to improve the affinity with Polis?
    - We'll make sure feedback happens quickly after you vote.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - We will do the visualization so that users can feel the value even if there are few users.
        - Hopefully in the future we can have a conversation with a chatbot on that subject.
    - I don't think affinity with Polis is necessary, trying to make updates to Polis will reduce freedom.
        - Now is the phase where exploratory trial and error should take place
        - I think any system designed before GPT4 should be reviewed.
            - Not that the previous system would instantly lose value...
            - When a new component is created, the existing system is already structured to provide user value without that component, so trying to add a new component to it will only result in a non-essential add-on
            - Assuming that new components are available, we must consider what we need to do to create customer value
- Can you tell us exactly what will be learned from the Scrapbox data?
    - To be precise, it is not "learning." [[Retrieval-Augmented Text Generation]], text generation enhanced by retrieval.
- In building a "community AI," how do you learn about the culture and opinions of a particular community? And how will the learned information be used to express the specifics?
    - It would be good if the text data of the exchange could be automatically extracted from the communication platform (groupware) primarily used by the community.
        - To use a figurative expression, "the AI is watching every conversation in the community."
    - I'm doing it in Scrapbox now because it's convenient for automatic export in JSON format.
        - The good news is that there are a number of public and private communities
    - As a start, anything with text data is good.
        - For example, Taiwan[[g0v]] minutes are available on HackMD, which you can crawl
            - [[Cybozu style]] articles can be targeted
        - But even if you build a chatbot that learns these things as a start, it's not very interesting if you can't build a feedback loop for it.


> Awareness: I would like to see not only abstract and future talk, but also a good connection between that and what has already been achieved and what is being implemented.

Notice: Several sub-projects of the Omoikane project are connected by [[familial resemblance]].
- So you can't verbally say, "This is what the Omoikane project is.

## summarized
.
- The Omoikane Project specifically uses ChatGPT to generate science fiction. However, in terms of narrative quality, we advocate avoiding high self-standards due to bad perfectionism, and instead producing low quality first, and then improving upon it. We believe that perfectionism should be achieved through sharing and feedback, and that the desire for authorship and ownership inhibits this.

- Improvements to the Polis voting functionality in the "Komorebikagami" project will be implemented by providing immediate feedback to users when they vote, and by creating a visualization that even a small number of users will find valuable. In the future, it is anticipated that the ability for users to converse with chatbots about themes will be added. However, we do not aim to strengthen our affinity with Polis, and we take the position that older systems should be revised to be compatible with newer components (e.g., GPT-4).

- In the "Scrapbox-based AI Chat Creation Project," Scrapbox data is used not to "train" AI chatbots, but for Retrieval-Augmented Text Generation, or text generation enhanced by search.

- To build a "community AI," text data will be extracted from communication platforms that are primarily used by the community, and used as material for training by the AI. However, we recognize the importance of not only data extraction and learning, but also a feedback loop.

- In general, he believes that these projects should be connected not only to abstract stories of the future, but also to concrete actions that have already been realized or are being implemented, and that the sub-projects of the Omoikane project are connected by "family resemblances.

## made him ask more questions
- First, I found your explanation of "bad perfectionism" and "good perfectionism" very interesting. If you could explain how this is reflected in the Omoikane project with specific examples, I would understand it better. For example, could you give us a specific SF story generation process and steps for improvement through feedback?
    - Specific SF story generation process will be shown at the beginning of the study session<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - [https://chat.openai.com/share/7f7ca59b-1fe8-40af-889e-2652375875b1](https://chat.openai.com/share/7f7ca59b-1fe8-40af-889e-2652375875b1)

- Next, we heard about the "Komorebikagami" project to improve the Polis voting feature. The idea of making feedback immediately available is very interesting, as it seems to improve the user experience. However, I would like to know more details on how exactly that will be implemented. Also, I would like to hear more about the part "we are not aiming to strengthen the affinity with Polis" and why.
    - As soon as the vote button is pressed, the percentage of approval or disapproval is displayed.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - If you want the same experience as Polis, you can use Polis. Polis does not have an API, so if you want to integrate with Polis, you have to start by modifying the source and adding an API, but it is more flexible to use your own.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

- Regarding the "Scrapbox-based AI chat creation project," it was explained that Scrapbox data will not be used for "learning" but for "text generation enhanced by search." I would like to know a bit more about the specific process by which this is done, e.g., how Scrapbox data is incorporated into the AI chatbot and how it helps with text generation.
    - Scrapbox data is divided into chunks and entered into a vector index, from which it is searched for vectors and loaded into prompts during text generation<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - I'll explain in more detail at the workshop or...

- Finally, regarding "community AI," I understand the importance of text data extraction and its feedback loop. However, I would like to hear more about its specific implementation. For example, how is the process of extracting text data from a particular community and then having the AI learn it? Also, I would be interested to hear specific examples of how the feedback loop is constructed and how it contributes to the AI's learning and representation.
    - The "text data is extracted from a specific community and the AI learns from it" is the same as the above mechanism.
    - The feedback loop begins with chatbot and user chat logs that are shared with the entire community
        - You can vote yes or no on each of these exchanges, and discuss better answers, etc.

- These are my impressions and questions based on the understanding I gained from this briefing. It was very interesting to hear how each project is progressing and how they are working together. A more detailed explanation would be helpful to further deepen our understanding.

memo
- If I had to sum up the Omoikane Project in a few words, I would say "combining sci-fi prototyping and AI technology to create a better discussion mechanism.
- Now Explanation
    - > The Omoikane project aims to [[improve]] discussion through [[SF Prototyping]].
    - Update based on the above or
    - The ✅ below.

memo
- Previously we talked about Plurality and Polis in the study group.
- Discussed in the context of digital democracy, deliberative support systems, and
    - To apply for an OpenAI grant
- The concept of "combining sci-fi prototyping and AI" was born from this.
- Polis is a useful component, but it is not complete on its own, requires pre and post steps
- ![image](https://gyazo.com/aef9e1e0f7e3b68658191af8d97ed0ae/thumb/1000)

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
Thank you very much for your very detailed response. This has given me a better understanding of the specific implementation of the project and the direction we are aiming for.

Regarding the "Komorebikagami" project, I was convinced by the fact that the percentage of approval or disapproval is displayed as soon as the vote button is pressed, and by the policy of building our own system to provide a different experience from Polis. We felt that building our own system would give us the freedom to customize the functionality we needed and achieve results more consistent with the goals of the project.

Regarding the "Scrapbox-based AI Chat Creation Project," the explanation that Scrapbox data will be put into a vector index and searched for vectors during text generation was helpful in understanding how the AI chatbot will utilize Scrapbox data. This was helpful to understand how AI chatbots utilize Scrapbox data.

The description of the feedback loop for "community AI" was also useful to understand specifically how direct feedback from the community is used to learn AI. The ability to share and vote on chat logs across the community will not only help accelerate improvements in AI, but also encourage active user participation.

With these explanations, the overall picture of the Omoikane project came into focus. I feel that the concept of "combining SF prototyping and AI technology to create a better discussion mechanism" is very useful for improving the quality of discussions and guiding better decisions in today's society. We will continue to keep an eye on how these projects progress.

## 次回リキャップすべき要約
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
- The "Komorebikagami" project aims to improve upon the voting functionality of Polis, with a system that displays the percentage of approval or disapproval as soon as the user presses the "Vote" button. The project has also adopted a policy of developing its own system to provide a different experience from Polis.
- In the "Scrapbox-based AI Chat Creation Project," Scrapbox data will be put into a vector index and utilized in a vector-searchable manner during text generation. This allows for "text generation enhanced by search" rather than "learning.
- With "community AI," chat logs are shared with the entire community and feedback is provided through voting. This allows the AI to learn and improve its expression.

These three projects are ongoing as part of the Omoikane Project, which aims to "combine SF prototyping and AI technology to create a better discussion mechanism.

In the next issue, we hope to discuss in more depth the specific progress of these projects and how they are working together.

[chatlog2](https://chat.openai.com/share/98df3f84-6c3c-43dd-9df5-57382a3f6452)

Upcoming events<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Touch on a few projects other than your own.
    - There isn't much I can tell you.
- I think it's getting too large to fit in the context, so I'll specify the purpose and then let them make a summary of just the parts that are useful for it and compress it.
- Grow until Wednesday with repeated divergence and convergence, then serialize on Thursday.
    - I was going to say, "I'm going to go to Kozaneba on Tuesday," but I think I might be able to squeeze in Kozaneba on Tuesday.

# chat3
I had him ask questions with a recap of the past, but I felt it was not very productive because there were so many questions about areas that had not yet been decided.
- (Maybe it's my imagination? Maybe it's "I felt something wasn't good enough" to be accurate, and you're just using the excuse that the quality of the question is not good enough? I'll observe from a third-party perspective after some time has passed.)

I threw a list of projects because I didn't have enough questions about projects other than my own.

- What specific evidence data will be used in the "EBSFP: Evidence-Based SF Prototyping" project and how will it contribute to SF prototyping?
    - I'm thinking of creating search keywords based on the SF prototype and loading the prompt with abstracts of papers found by searching with those keywords.

- In the "Thinking and Creating while Reading and Writing the Future" project, what will you think and create through reading and writing the future?
    - I'll dig into this later.

- What exactly will the SF prototyping demonstration look like?
    - I have a lecture in the planning stages that I'll share with you.

- What kind of feedback will be collected in the "Komorebikagami" feedback collection platform building project, and how will this help build the platform?
- What exactly will the "Scrapbox-based AI Chat Creation Project" create and how will it utilize Scrapbox data?
- What kind of communities will be targeted and what kind of AI will be built in the "Building Community-Centered AI" project?
    - I don't remember this area being coy.

## "Thinking and Making the Future While Reading and Writing" project
.
- Embodying the future in novel form: This is an important tool for thinking deeply about the future, as it is a means of understanding the abstract vision of the future in a more concrete way.
- Leverage AI: AI technologies such as ChatGPT are used to assist in the entire SF prototyping process. Specifically, AI complements and assists with tasks normally performed by humans, such as world-building, plot creation, and writing the main text.
- Participation is open: You do not have to participate in the entire process, just read, write, or think, or even just think of new ways to use AI.
- Evolution of Science Fiction Prototyping: In this project, the act of reading and writing science fiction itself is supposed to evolve, resulting in a new vision of the future. The methods of [[social science]] will be used to observe and understand this process.
- Knowledge sharing: There is an emphasis on sharing information among members on how to write, how to use AI, and ideas.

The idea that these elements will be intricately intertwined and formed as [[an activity to think about the new future]] and as [[itself part of the future]] seems to be a distinctive aspect of this project. It will be interesting to see how this project develops.

- Regarding the use of AI: What specific AI technologies are used in this project? And how are they applied to each step of the sci-fi prototyping process (world-building, plotting, writing the text, etc.)?
    - ChatGPT!
- Regarding freedom of participation: How much freedom does each participant have in their activities? For example, if some participants "just read" or "just write," how does their activity contribute to the overall project?
    - Individuals can do what they want to do, [[Connecting the Dots]]. Contributions will become apparent over time when we look back into the past.
- Regarding "the evolution of SF prototyping": can you elaborate a bit more on this point? Specifically, how is the act of reading and writing SF itself evolving? And how do you view and try to understand that evolution?
    - The act of writing SF is evolving by having ChatGPT write it.
        - The hurdle has been lowered with the help of AI, and people who would never have thought of themselves as writing science fiction are now participating in writing science fiction. This is related to the question of how to encourage residents' participation in civic tech
        - Unique social interactions have emerged, such as the sharing of unfinished plots and ideas on Scrapbox, and the generation of answer-song-like novels in response to novels written by others.
        - In terms of reading, the novel provided an experience not found in existing novels, in which the feelings resulting from reading are aggregated and clustered.

- Regarding social science methods: you mentioned that the project will use social science methods to understand the new "reading and writing science fiction" phenomenon, what exactly does this mean?
    - This I don't know, [[participant observation]]?

- Regarding knowledge sharing: How is information shared among members? And how are these findings reflected in the overall progress of the project?
    - Information sharing is done through a kind of wiki called Scrapbox
    - Normally, each individual works asynchronously at his or her own pace, and periodic audio meetings are prepared and synchronized there.
    - Synchronous communication is efficient because only pointers to asynchronous content are needed


Use of ChatGPT: The use of ChatGPT as an AI technology in this project and the way it is evolving the act of writing science fiction is very interesting. example at the intersection of technological progress and culture.

Free participation: The fact that participants are free to work based on their own interests and abilities enhances diversity and creativity, and can lead to new discoveries and results. The fact that each contribution will become apparent over time also indicates that this project has a long-term perspective.

New Reading and Writing Experiences: The unprecedented reading and writing experiences being offered are literally an evolution of science fiction prototyping. The resulting changes in social interaction will be part of a new cultural formation.

Knowledge sharing: Information sharing using Scrapbox and synchronous communication through regular voice meetings were found to play an important role in project progression and knowledge deepening.

In addition, I think a more specific explanation of the phrase "social science methods" would further enhance my understanding. The presumption of participant observation is indicated, but I would appreciate more specific information on how it is applied to the project and what other methods are used.

[chatlog3](https://chat.openai.com/share/4df64cb6-ba3b-4673-a434-16612738aef7)

# Kozaneba
![image](https://scrapbox.io/files/64c8c4734b7a33001b295ca3.png)
![image](https://scrapbox.io/files/64c8c5cde9c6a1001cef0c0e.png)
![image](https://scrapbox.io/files/64c8c97b448b81001b6fbc71.png)


![image](https://scrapbox.io/files/64c8cfb6e9c6a1001cf0130a.png)
- awareness
    - Voting anonymously "I think that's different" on AI output is a low psychological hurdle.
        - Compared to saying "I think that's different" in response to a human statement, "I don't mind because the other person isn't human."
        - Better because it is anonymous compared to speaking orally or on a social networking site with a name
        - No need to put it into words since it is a "yes/no" vote, and you can honestly express your discomfort when you feel uncomfortable.
![image](https://scrapbox.io/files/64c8d273516bc4001be22f1b.png)

opening section
- ![image](https://scrapbox.io/files/64c8d25fdcf687001c252886.png)

whole
- ![image](https://scrapbox.io/files/64c8e2c529cc45001bf5926f.png)

copy
- What kind of feedback will be collected in the "Komorebikagami" feedback collection platform building project, and how will this help build the platform?
- What exactly will the "Scrapbox-based AI Chat Creation Project" create and how will it utilize Scrapbox data?
- What kind of communities will be targeted and what kind of AI will be built in the "Building Community-Centered AI" project?
    - I don't remember this area being coy.
    - Added: After creating Kozaneba, I read it again and surprisingly it didn't answer my question.
        - In other words, this is "a flood of human 'answered and unanswered' buffers".
        - In addition, "Kozaneba is a tool to expand human temporal memory.
- What kind of feedback will be collected in the "Komorebikagami" feedback collection platform building project, and how will this help build the platform?
    - [[AI Novel: "Phantom"]].
    - [[Polis:AI Novels: "Phantom"]].
    - For example.
        - The future will look like this." "I don't think so."
        - Scary." "Scary."
        - 'Character A is bad' or 'A is not bad.'
- What exactly will the "Scrapbox-based AI Chat Creation Project" create and how will it utilize Scrapbox data?
    - Not clear yet.
    - What kind of people would like to talk to a chatbot and for what purpose depends on the community, so the following questions are relevant
- What kind of communities will be targeted and what kind of AI will be built in the "Building Community-Centered AI" project?
    - First, the smallest unit of community is one person
        - This would be an AI that learns and speaks the information that that one person transmits or gathers.
        - Used by people interested in the individual (especially the individual himself/herself)
        - For example, you ask a question and the AI answers, and the person sees this question, which triggers a better explanation.
        - There are many "[[Question Box]]-like services out there.
    - Communities collecting information on specific topics
        - This poses a question for those interested in the subject
        - Seeing a failure to answer a question will provide an opportunity to add information.
    - Communities running specific projects
        - This is where the unknowns start to come in.
        - People interested in the project ask questions about the project.
        - If someone is interested in a culture, that culture corresponds to "collecting information on a specific topic".
            - [[g0v]] and [[Cybozu style]] are equivalent to this.

awareness
- Writing about the "personal" example, I noticed that there's a "question box" as a service that fills a close existing need.
    - The "Qualia-san Question Box," "AI Nishio's Question Box," "Omoikane Project Question Box,"...
    - I feel it would be beneficial enough as a prelude to a chat.

![image](https://scrapbox.io/files/64d5c4ab4bef33001c87e0ea.png)
- The reason why [[Deepening Knowledge]] is so important is that working on a project is "[[practice]]," through which [[practical knowledge]] is gained, and the members working on the project become a [community of practice Because

![image](https://scrapbox.io/files/64d5c4a757ebea001c451467.png)
- It's not perfect yet, but it's coming together pretty well.

They're all hooked up.
- ![image](https://scrapbox.io/files/64d5c4a3a9e992001c7b7a47.png)

2023/8/3
- I looked at Kozaneba and scrubbed through the material.
- As for the questions, we adopted some of them verbatim.

2023/8/4
- Read it again after a night's sleep, add and revise.
    - [[Omoikane Study Group]]

2023/8/8
    - [[Examples of Reorganizing]]
    - [[Nodal Point of Thought 2023-08-08]]
2023/8/10
    - [[Nodal point of thought 2023-08-10]]
    - [[GPT4 and the Nodal Point of Talking Thoughts 2023-08-10]]
    - [[Kozaneba:Neri Neri]]

---
This page is auto-translated from [/nishio/オモイカネ勉強会の準備](https://scrapbox.io/nishio/オモイカネ勉強会の準備) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.