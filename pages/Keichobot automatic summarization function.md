---
title: "Keichobot automatic summarization function"
---

2023-03-13
I added a function that automatically returns a summary when the chat logs become too large, so I chatted with them to test it out.

memo
- As for the first summary, it wasn't triggered by a bug, so I fixed the condition in the process.
- The OpenAI API's latency has caused the Heroku side to time out and die many times, making it hard to make it practical.
- I feel it would be beneficial to get a summary and next action back to me at the appropriate time in the chat.

log
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What would you like to see happen in this conversation? (GPT)
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>We've added a function that automatically returns a summary when the chat logs become too large, so let's chat about it while we test it out!
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Is it a conversation log or another kind of log?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Here is the log of this conversation.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Is the conversation log you own the log of this chat? Or is it something else?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>That question is a touchy one.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Is it this chat log you are talking about this time? Is it another kind of log?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>The original algorithm asks certain types of questions and then does not repeat them. This means that if a subtle question is asked, you can just go through it and it will never come up again. With ChatGPT, however, it will come up again and again.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Now, can you give us some more of your thoughts on this "subtle question"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Even human counselors can ask subtle questions. This is because they are agnostic about the inner workings of their clients. ChatGPT repeats itself. This repetition is the most frustrating behavior of the client when using the ChatGPT version of Keichobot.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>ChatGPT is a natural language processing model developed by OpenAI and used for artificial intelligence dialogue generation.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>This next one is where you give explanations without asking questions.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>ChatGPT is a natural language processing model used for artificial intelligence dialogue generation; in the case of Keichobot, this repetition may be considered offensive to the client.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Keichobot's Japanese was a bit awkward at times, but his ability as a counselor is better than ChatGPT so far. I hope we can merge them well.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>How did you hear about ChatGPT?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I forgot.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>ChatGPT is an open source natural language processing model available on the Internet, and Keichobot is one application.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>If we keep it the way it is, we're going to have to reduce the ChatGPT weighting, right?
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>ChatGPT is an open source natural language processing model available on the Internet, on GitHub and other developer platforms.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>By the way, we've added a conversation feature to the Scrapbox ChatGPT Connector.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>You mentioned that you have added a conversation feature to the Scrapbox ChatGPT Connector.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>👎ChatGPT
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Is the Scrapbox ChatGPT Connector a tool that makes ChatGPT available on Scrapbox? Or is it something else?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>This is a tool that allows ChatGPT to converse with reference to Scrapbox data. Preferable to run on Scrapbox in the future, but not implemented yet.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>The Scrapbox ChatGPT Connector is a tool that allows ChatGPT to have conversations using Scrapbox data, but what are those conversations?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Don't think it's a mixed bag.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What kind of bot is "Keichobot"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>It's a bot that encourages verbalization by asking questions.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What kind of question?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>The original Keichobot behaves according to a coaching technique called Clean Language.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Keichobot is a bot that behaves according to a coaching methodology and can organize the other person's words and approach their inner world through questions.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>(esp. of men) one's prime (approx. age 30)
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Keichobot is a question-answering bot that runs on a program and follows a coaching methodology.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>That's right.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What types of questions was Keichobot designed to ask?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>The questions that take out the human mindscape without distorting it are
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Can you elaborate a bit more on the concept you described of "taking out the human mindscape without distorting it"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>When a question contains an implicit assumption, the respondent is influenced by it and gives a distorted answer. This is very bad because the respondent may misinterpret it as his/her own idea without realizing that it has been distorted by the question. Therefore, it is necessary to have a technique to extract the information without distorting it.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Can you give some more specific examples to illustrate the concept you mentioned, that if a question contains implicit assumptions, it will result in a distorted answer?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>For example, "Is it A or B?" I would answer with A or B, even if it is really C.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What is the "C" in regards to?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>For example, the question of whether it is OK or NG creates the misconception that one has to decide "now" which is which, but in reality, the decision can be postponed.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What type of "misunderstanding" did you describe? Can you describe them specifically?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>A misconception that makes us think there are only two choices when there are really more.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Is it important to you to have choices? Do you feel it is of any value to you?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>It is important to have choices. It is valuable. Too many and you won't be able to decide, but until you do, it's better to have as many as possible.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What does it mean to you to have a choice? Can you be more specific?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Hmmm, that's a tough question.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What is important about "choice?"
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I guess I feel like I made my own decision.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>How do you feel about the feeling of "self-determination?"
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>If they succeed after making their own decisions, it makes them feel that they have succeeded and increases their sense of self-affirmation. Conversely, a child who takes the college entrance exam as told by his or her parents and passes the exam may go crazy because he or she does not have a sense of self-affirmation.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What kind of self is "me"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>The self that proactively chooses to live his or her own life.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Is there anything else about yourself that you feel is important?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I think it's about being able to say, "I lived life proactively" when you die. It is easy to understand if you consider the opposite extreme. If you think, "I just followed my parents' orders all my life," you will feel like a robot.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What exactly is the "bot" you are talking about?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>An entity that can only move according to orders.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What exactly would an "order" look like?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Taking away the opportunity for proactive decision-making.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What exactly do you mean by "decision making" when you state "taking away the opportunity for proactive decision making"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Decide for yourself what actions you will take.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Where do you come from with regard to the "self" you described as "deciding for oneself what actions one performs"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>It's there when you realize it's there.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Can you tell us a little more about "chi"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>When you are aware of your existence, you already exist.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Who exactly do you mean by "yourself"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Human beings in general, not referring to any specific person here.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What exactly do you mean by "choices"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Its human behavioral options.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>How do you know what the alternatives are?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Sometimes we happen to know, and sometimes we actively take action to know. Back to the story, depending on how the question is asked, it can encourage the discovery of alternatives or, conversely, make them invisible, so a questioner without malicious intent is beneficial
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What do you think is the best way for the person to find options for action?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Basically, I'd prefer more information-gathering action.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What types of "actions" can the person take to discover behavioral options?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>For example, attending events, meeting new people, going to schools, etc. to gain new knowledge, joining new communities, etc.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>One of the other ways to increase your options for action is to increase your output. This includes writing down your thoughts and talking about them.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>that's so, isn't it
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>It is desirable for the person to discover more options for action.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>That's right.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>By "action," what exactly do you mean?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>What the specific action is depends on the situation. For example, I often consult with Keichobot about development, and in this case, "implementation" is the action. In this case, "implementation" is the action. There are several methods of implementation, or there are several objectives, and I am not sure which one should be prioritized.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>'Consulting Keichobot' is an 'implementation' action, but where are you actually taking that action?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>The implementation is done in front of a computer.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Could you be more specific about "implementation?" For example, what kind of programs are you implementing?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Sometimes it depends on the Keichobot itself.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>How is Keichobot actually developed?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I'm running it on heroku right now.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>How did you gather information to learn about Keichobot?

Summary so far
[Test chat log summary
- Test the chat log summary feature.
- The original Keichobot behaves according to clean language.
- With ChatGPT, even subtle questions are returned repeatedly.
- Even human counselors can be asked subtle questions.
- Depending on how the questions are asked, they can encourage the discovery of alternatives.
- It is important to increase action.
- Some actions for implementation, depending on the situation.
- Keichobot has its own implementation.
- It is running on Heroku.

[Next action.
- Make it work on Scrapbox.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>The summary function worked. I think I can run it on Heroku.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Can you tell us what Scrapbox is all about?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>A very easy-to-use, knowledge-storing mechanism
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What do you need to do to know its behavior?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>？
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What needs to be improved regarding "Keichobot itself?"
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>We are currently in the process of exploring the direction of combining Keichobot and GPT. If we decide to make the transition in earnest, I think it would be better to take this opportunity to rework many parts of the existing algorithm that we don't need.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What do you think needs to be improved about Keichobot?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I think it would be better to let LLM do the machine learning on its own.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Can you elaborate on what you can do?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>The keywords are scored using machine learning to determine which questions are appropriate. Replace there.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What kind of output would you like to see emerge from the "question"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>It is good if the user speaks with enthusiasm. We are now doing our own machine learning to determine this enthusiasm.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What kind of enthusiasm would you like to see as your desired output?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>It is desirable to get the user into a state of immersion and a lot of talking. New discoveries can be made from what is said in this way.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What kind of enthusiasm would you like to see as your desired output with respect to "The Question?"
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>It would be nice to have a situation where words start pouring out in response to questions asked, and more and more verbalization occurs without the user having to work hard at it.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Who exactly do you mean by "users"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Me first, then anyone who is interested and wants to use it.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What is the "Keichobot" program?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>A program that encourages such people to go further and further ahead by asking them questions and encouraging them to verbalize their Next Actions.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Can you explain exactly how you would pose the question?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Right now I'm throwing the whole mess to LLM, but it's not very good, so I guess I'll have to break it up into steps to execute it.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>If Keichobot is executed in steps, what are the specific steps?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>That's not enough experimentation yet, and it's hard to try it while tinkering with a system running on a server, better to create an experimental environment with local scripts.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What was the purpose of Keichobot?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>The effect of encouraging clean language verbalization is very impressive, but it is too expensive to make an appointment with a human for coaching, so it is worthwhile to allow a machine to do it, even if it is somewhat less capable than a human.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What exactly do you mean by "verbalization?"
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>To be able to put into words and explain matters that I cannot yet explain well.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>To begin with, who is Keichobot?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>It would be digital stationery.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>The relationship between "Keichobot" and "questions" is that Keichobot poses questions to users, encouraging them to deepen and verbalize their own thoughts.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Yes.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>How do you expect Keichobot to change the way "users" think?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>If you cannot verbalize your thoughts, you cannot look them over. Verbalization is the first step in being able to critically examine your thoughts and find solutions to the contradictions and problems you are struggling with.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>It would be nice if "users" could deepen their own thinking and verbalize their ideas so that they can examine them more critically and find solutions to conflicting problems, but what else do you expect?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>If you can verbalize it, others and your future self can read it. Ideas in your brain disappear quickly.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Do you expect anything specific to happen to "you"?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>I expect realizations to happen.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>I can tell you that after the verbalization happens, you will have a clearer picture of what is important to you, but do you expect it to lead to any specific actions?"
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Clarity of what is important changes the priorities of resource allocation, which in turn allocates those resources to actions that were not previously allocated mindshare, time, or money, and they begin to move.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What specific "actions" do you take once you realize what is important?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Actions are created to achieve what you think is important.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>We hope that their actions will lead to concrete steps to solve problems and issues.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>(esp. of men) one's prime (approx. age 30)
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Do you think that this verbalization can be more useful to others and to your future self than to yourself?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Of course I think there is.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Is this self the conscious self that exists in the brain? Or is it a physical self?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>A curious question. Since consciousness alone would not be able to act, it is the physical self in the sense that it is the subject that acts. It could be said that the physical self acts according to a course of action verbalized by the conscious self.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>We can think of this as a link between verbalization and action, which changes the priorities for resource allocation, allocates resources to previously unallocated actions, and creates movement.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>That's right.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>As verbalization leads to action, the priorities for resource allocation will change and resources will be allocated to previously unallocated actions, creating a movement that is eagerly awaited.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Yes, ask any questions.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Verbalization allows you to clearly understand your thoughts and feelings and thereby grasp the values and goals you hold dear.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Question.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>I think "verbalization" can be very useful to understand one's inner life clearly, but what does it mean to you?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>If you have a clear understanding of your inner self, you can live better
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>The "self" refers to the self as a being that understands its own inner self and values and is better able to lead a better life.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>That's a good summary.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Do you think there is a connection to Keichobot, a clean language designed to provide choice?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Clean Language is not designed to provide choice.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>Are the "options" drawn from your self-narrative?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>that's so, isn't it
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>So what do you think is the purpose for which Clean Language was designed?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>It's about drawing them out.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>The purpose of "clean language" is to perceive information for the purpose of explaining it.
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Hmmm, well, yes. You could say that the goal is to make the client perceive it clearly so that he/she can explain his/her feelings and thoughts to others. Maybe the related symbolic modeling is clearer on the idea there.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>By "others," what kind of people are you referring to?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>Other than yourself
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What characteristics does he/she have?
<img src='https://scrapbox.io/api/pages/nishio/human/icon' alt='/nishio/human.icon' height="19.5"/>You can't know what's in your heart without describing it in words.
<img src='https://scrapbox.io/api/pages/nishio/kei/icon' alt='/nishio/kei.icon' height="19.5"/>What do you mean by "the word?"
The limits of ChatGPT memory. Summary so far
- The chit-chat evolves from the topic of testing a chatbot with the ability to automatically return a summary of chat logs.
- Asking the right questions can put the inner human being into words.
- The importance of enabling clients to explain their own feelings and thoughts to others in words was raised as an objective to make them perceive them clearly.
- Clean Language is not intended to provide choices, but it does play a role in the related symbolic modeling.
- Keichobot and ChatGPT must be combined, starting with experiments in local environments.
- FUTURE WORK: Development of a combination of Keichobot and ChatGPT will be promoted.

[https://keicho.netlify.app/#talk=E1oJgUsPApdiVirNOUmV](https://keicho.netlify.app/#talk=E1oJgUsPApdiVirNOUmV)
#KeichobotLog

---
This page is auto-translated from [/nishio/Keichobot自動要約機能](https://scrapbox.io/nishio/Keichobot自動要約機能) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.