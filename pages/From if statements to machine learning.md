---
title: "From if statements to machine learning"
---

![image](https://gyazo.com/e6afaa643e5d90b03e2983764d9aa62b/thumb/1000)
From if statements to [[machine learning]] 2017-09-26 BPStudy#121
Cybozu Labs / BeProud Technical Advisor Doctor of Science / Master of Technology Management
NISHIO Hirokazu
ver.2 published 2017-09-29
ver.3 2018-06-22 diagram cleanup
ver.4 2023-06-10Clean up and add OCR results

![image](https://gyazo.com/678badbaf3519afe5324b43b56057ea7/thumb/1000)

Do you think machine learning is a world away from the programs you are writing now?

![image](https://gyazo.com/2ac79c15ccd864452d5dc1da9b655b3a/thumb/1000)
Purpose of this slide
- We will bridge the gap between if statements and machine learning, which everyone is familiar with, so that we can connect the ground and use machine learning in practice.
- He will also explain how to proceed with the business implementation of machine learning in four steps, step by step.

![image](https://gyazo.com/2608d362e16adbca7400a3553c1a0e11/thumb/1000)
if statement 4 if(`condition`){ ...}

![image](https://gyazo.com/d3497b5db2fd5e7844aaf3bf4c9b6457/thumb/1000)
How if statement works
- Execute contents when the condition is True.

![image](https://gyazo.com/0cef01d7cf9bcf217e4214d21c3a8bbb/thumb/1000)
When there is more than one condition
- What if I want to run when either condition x1 or condition x2 is True?

![image](https://gyazo.com/b4431e9b8bb3903f3d2fdc759cd7b41e/thumb/1000)
or
- `if(x1 or x2){ …}`

![image](https://gyazo.com/69bd44856d9f2285220fc323508164de/thumb/1000)
When there is more than one condition
- What if I want to run when both condition x1 and condition x2 are True?

![image](https://gyazo.com/d72be5377d0a3983ccbfdcd350d14151/thumb/1000)
and
- `if(x1 and x2){ …}`

![image](https://gyazo.com/03d5a280e95da798cdadfe8e2b07fc78/thumb/1000)
When there is more than one condition
- What if I want to execute when two or more of the conditions x1, x2, x3 are True?

![image](https://gyazo.com/facfe680f16b01fcebcda515f5cf3177/thumb/1000)
Complicated!
- `if((x1 and x2) or (x1 and x3) or (x2 and x3)){ …}`

![image](https://gyazo.com/1846ba35a0e14355e161b4868a882f93/thumb/1000)
When there is more than one condition
- What if I want to execute when 3 or more of the conditions x1, x2, ..., x5 are True?

![image](https://gyazo.com/ba6368d2da9a70acd23c06e5fe46f8d3/thumb/1000)
Complicated!
- `if((x1 and x2 and x3) or (x1 and x2 and x4) or (x1 and x2 and x5) or…){ …}`

![image](https://gyazo.com/dd99a61bf5d2979a309b7ea1ff6b6519/thumb/1000)
There is a better way!

![image](https://gyazo.com/cc5c2293acc809279378d9a7bb286701/thumb/1000)
[[true/false value to be numeric]].
- Converting True to 1 and False to 0 changes "3 or more True" to "3 or more when added".
- `if((x1 + x2 + x3 + x4 + x5) >= 3){ …}`

![image](https://gyazo.com/e6c32404c0b84b44e4174b40a44a3cdd/thumb/1000)
Both and and or can have the same form.
- `x1 and x2 and x3 and x4 and x5` = all of the conditions x1, x2, ..., x5 are true = add up to 5 or more
- `x1 or x2 or x3 or x4 or x5` = any of the conditions x1, x2, ..., x5 are true = add up to 1 or more

![image](https://gyazo.com/5fa7ff716d1dcd1460df8b8b9be293b4/thumb/1000)
Both and and or can have the same form.
- Condition x1, x2, ..., x5 are all True
    - `(x1 + x2 + x3 + x4 + x5) >= 5`
- At least 3 of the conditions x1, x2, ..., x5 are True
    - `(x1 + x2 + x3 + x4 + x5) >= 3`
- One of the conditions x1, x2, ..., x5 is True
    - `(x1 + x2 + x3 + x4 + x5) >= 1`

![image](https://gyazo.com/076f4e8c6975883a642d2b39c2dcf49c/thumb/1000)
Try to align the right side
- Condition x1, x2, ..., x5 are all True (weak)
    - (1/5 *x1 + …) >= 1
- At least 3 of the conditions x1, x2, ..., x5 are True
    - (1/3 *x1 + …) >= 1
- One of the conditions x1, x2, ..., x5 is True (strong).
    - (1 *x1 + …) >= 1


![image](https://gyazo.com/6e770115e61dfbc3f13e458737536689/thumb/1000)
Strength = Weight
- Something like the "strength" of the condition is expressed by the magnitude of the coefficient ([[weight]]).

![image](https://gyazo.com/ffe9c0ca59d9a378ff8130d3ea02438d/thumb/1000)
question
- How can I express that all of the conditions x1, x2, ..., x5 are True, or at least 3 of the conditions x6, x7, ..., x10 are True, or any of the conditions x11, x12, ..., x15 are True?

![image](https://gyazo.com/b8b54921f347a17194d4770aa6bbab08/thumb/1000)
Weights may vary from condition to condition
- 1 *x1 + ... + 1/3 * x6 + … + 1 * x11 >= 1

![image](https://gyazo.com/c7609fc432680f2e0b30fee3cdcc137c/thumb/1000)
Weighted sum method
- Set the true value of true to 1, false to 0, multiply by the strength of the condition as weights, and add them together.
- This allows for the description of complex conditions that would be difficult with and or combinations.
- Negation can be realized with negative weights and xor cannot be expressed, omitting the fact that xor

![image](https://gyazo.com/a85146d3aef08470c3995de225807c06/thumb/1000)
How do you adjust the weight?
- 1: People decide, just like we just did.
- 2: Machine decides based on a large amount of data = machine learning

![image](https://gyazo.com/7822bfdf9a569437e4bf141d1c507d74/thumb/1000)
Specific Codes
- The contents of this issue can be studied using [[logistic regression]].
- If you do `from sklearn.linear_model import LogisticRegression` and call `fit(X, y)`, the weights will be adjusted automatically and if you call `predict(X)`, the weighted sum will be calculated and determined. Easy.
- If you want to learn more about logistic regression, I recommend the series of articles by Hidehiro Nakatani of Cybozu Labs on the Gijutsu Hyoronsha website.
    - [18th logistic regression | gihyo.jp](http://gihyo.jp/dev/serial/01/machine-learning/0018)

![image](https://gyazo.com/22948174b3cdeeaa2007aa9b55241329/thumb/1000)
summary
- Complex conditions are difficult to write with and/or.
- It is easier to replace them with weighted sums.
- Weights can be determined by machine learning if there is enough data.
- The level of detail described in this article can be done in a few lines using scikit-learn.

![image](https://gyazo.com/b0dbff4c39165e40f944e07856a96f54/thumb/1000)
Machine learning techniques so far
Here are 4 steps to the business of machine learning

![image](https://gyazo.com/b365eee5095d50b7bc6b50e95e7b6ddf/thumb/1000)
Differences between Academia and Business
    - [[academia]]
    - Data is publicly available.
    - Withered technology was investigated long ago.
    - Devise new methods and compete for accuracy.
- business
    - Data not publicly available.
    - (Use of dead technology)

![image](https://gyazo.com/1ffa3b1f2dd43389bfa758fee341e4a5/thumb/1000)

Business Objectives
    - [[customer value]]
- ([novelty (patentability) not)

![image](https://gyazo.com/90a2986632d1803becd10903cfdc80dc/thumb/1000)
Sub-questions to experience customer value
- A certain gemstone has a 1/2 chance of containing a gem when broken and sells for 20,000 yen.
- One rough stone can be bought for 9,500 yen. Rough stones are hard and only 20 can be broken per day.
- Q1: What is the expected amount of revenue you can earn per day?

![image](https://gyazo.com/a4119bf74ac65c2c56dd3cae6d388e37/thumb/1000)
A1 Revenue Expectations
- A1: The expected value of income per unit is 10,000 yen because you get 20,000 yen at 1/2 chance.
- The purchase price per unit is 9,500, so the revenue per unit is 500 yen.
- Since 20 units can be processed per day, the revenue per day is 1,000 yen.

![image](https://gyazo.com/e9bccade278d7111b91fabc3c685bffb/thumb/1000)
Q2 Machining speed doubling device
- Q2: Suppose you have a machine that can break a rough stone twice as fast as a human.
- In other words, suppose the number of gemstones that can be broken per day increases from 20 to 40.
- How much more revenue can I expect?

![image](https://gyazo.com/c4414907eb24a8144a0b0c0b46d0f209/thumb/1000)
A2 Machining speed doubling device
- A2: It is still a profit of 500 yen per gemstone.
- The amount that can be processed per day increases from 20 to 40.
- Since there will be 20 more units, profit will increase by 10,000 yen.

![image](https://gyazo.com/78a99b9fd5288a6f023048d38e2b20b6/thumb/1000)
Q3 60% discriminator
- Q3: Suppose you can buy an identifier* that has a 60% chance of guessing the gemstone that contains the gem.
    - *Suppose that by using it before buying the gemstone, you can get a "gemstone with a 60% chance of containing a gemstone" for 9,500 yen.
    - I am not concerned this time about the fact that the store owner might not like it.
    - Also assume that the machine in Q2 is not in hand and the number of pieces that can be broken per day remains 20.
- How much more revenue can I expect?

![image](https://gyazo.com/deda9a9fc5b9e4a00ca891953de2531a/thumb/1000)
A3: 60% discriminator
- Since there is a 60% chance of getting 20,000 yen, the expected income per unit is 12,000 yen.
- Since the purchase price per unit is 9,500 yen, the revenue per unit is 2,500 yen.
- Since 20 units can be processed per day, the revenue per day is 50,000 yen.
- 40,000 more....

![image](https://gyazo.com/c2367038f172aeedf2c7fbe5876dff31/thumb/1000)
In other words, in this problem setting
- The "device that doubles the processing speed" increases the customer's profit by 10,000 yen,
- The "identifier with 60% accuracy" increases the customer's profit by 40,000 yen.

![image](https://gyazo.com/524a8c04a98e2b004da22e17cbc7e68f/thumb/1000)
lesson
- In this problem setting, a "discriminator with 60% accuracy" has four times the customer value of a "device that doubles the processing speed.
- How much accuracy and how much customer value can be generated depends on [[Business Requirements]].
- Accuracy is not always important.

![image](https://gyazo.com/c7d047af5c2e3730b304e38971a8332d/thumb/1000)
Business Requirements
- Before thinking about improving accuracy, it is necessary to first clarify [[what customers want]] and what kind of [[constraints]] they have.
- Even if a method described in the latest paper is implemented, if the customer cannot provide the amount of data required by the method, then the implementation has no customer value.

![image](https://gyazo.com/247dc788120a5b347094b8c0f2178cc3/thumb/1000)
Customers are not experts.
- In many cases, customers are not experts in machine learning and cannot clearly verbalize either the required accuracy or the constraints that must be met.
- So it is necessary to learn this fast.

![image](https://gyazo.com/a3444a0672815f849793029a4690c5d8/thumb/1000)
[[Minimum Viable Product]]
- A concept advocated in the "Lean Startup" methodology of IT venture management.
- Ventures have limited funds and must quickly understand customer needs.
- Therefore, by creating miscellaneous products at minimal cost and actually showing them to customers, we can find out where the customers' needs lie.

![image](https://gyazo.com/266ac1da93352348751aa9fb9b32696e/thumb/1000)
Minimal implementation = no implementation
- It's called "[[concierge-type MVP]]."

![image](https://gyazo.com/83a5de9e5964bc206493fbaf97cd3c0d/thumb/1000)
Step 1
- Let's assume it's a human and answer the following questions
    - ① [[customer value]] : What makes the customer happy?
    - (2) [[How people do it]]: If people do it, how do they do it (are there people who already do it?)? No?)

![image](https://gyazo.com/89af264374c78c751c8eac8a1e9b1d0a/thumb/1000)
(2) How humans do it
- Someone is already doing it, or knows how to do it.
- But it takes too much time and effort.
- → Opportunity! Mechanization to reduce time and labor is customer value!

![image](https://gyazo.com/5d9d44baa4a45d32876c3e95ab502108/thumb/1000)
(2) How humans do it
- There are people doing it on the client side, etc., but I don't know how to do it.
- → There is some important information being omitted from being communicated.

![image](https://gyazo.com/80a28a46c291fb43ac63e53b014b79ba/thumb/1000)
(2) How humans do it
- Neither the customer nor myself know how to do it the way humans do it.
- → Possibility of being recklessly delusional in the first place.

![image](https://gyazo.com/0721a06be0dcec2cad1638dbdd15c829/thumb/1000)
Example: Spam Filter
- Q1 What makes customers happy?
- A1 Customers have a problem with a lot of spam in their mailboxes, and would be happy if the spam would go away.
- Q2 How would a human being do that?
- A2 Look at the body of the e-mail to determine if it is spam or not, and move spam to a different folder.

![image](https://gyazo.com/6d2a0c22cc8ddba81b87c7ef26856136/thumb/1000)
Step 2
- Putting humans in a box.
    - Only electronic data can be put in and out of this box.
    - (Can be considered remote work).

![image](https://gyazo.com/dbb77c9716d7122a81cedfdc731007c6/thumb/1000)
Step 2
- (3) Input data: What data does a human put in the box to do (2)?
- (4) Output data: What kind of output data comes out of the box when a human does (2)?

![image](https://gyazo.com/96f424014443c9cb4a7318179989d194/thumb/1000)
Step 2
- (5) How to obtain: How to obtain input data (3)? (first step and how to do it continuously)
- (6) How to give: How do we connect output data (4) to customer value (1)?

![image](https://gyazo.com/8c650af8930351e96206a114682cdef8/thumb/1000)
The order in which these four questions are answered does not matter.
- Example 1: To do ~ to a customer (6), output ~ (4), therefore input ~ (3), how shall I get this? (5)
- Example 2: Now that we have the data (5, 3), how do we generate customer value from it? (6) What outputs are needed to achieve this? (4)

![image](https://gyazo.com/b25029ef607e5f77be73b1df99a3e705/thumb/1000)
Example: Spam Filter
- Q2 How would a human being do that?
- A2If it's done by a human, look at the body of the email, determine if it's spam or not, and move the spam to a different folder.
- Q3 What data needs to be included for a human to (2)?
- Need information on the body of A3 emails. I'd like to get the title and sender if I can get them.

![image](https://gyazo.com/7310d7584a70d6033a375a7d94a9ebd6/thumb/1000)
Example: Spam Filter
- Q4What output data comes out of the box when a human does (2)?
- A4Output "spam, not spam" labels for each e-mail

![image](https://gyazo.com/f25c1b978c867c1806b8042137537af7/thumb/1000)
Example: Spam Filter
- Q5 How do I get the input data (3)?
- A5 As a first step, if you could export your email for now.
    - To do this on an ongoing basis, I would need to create a way to get the data from the mailer or modify the mail server side.
- PS: Which is a higher priority, receiving the data for the first step and experimenting or modifying the mail server so that data is continually available?
    - Basically, "can it be identified by machine learning" is uncertain, so the sooner it is verified, the better.
    - It depends on the situation, so we need to decide on a case-by-case basis which to do first, or whether to do them in parallel.


![image](https://gyazo.com/0879baad881c2caefbb9052277b1d2d4/thumb/1000)
Example: Spam Filter
- Q6How do you connect output data (4) to customer value (1)?
- A6Sort mail by looking at the label that is/isn't spam
- PS: Once we have verbalized that we need to "sort mail" in order to connect to "customer value," the next question is, "How can we do that sorting?" and then we can dig deeper.
    - Can we modify the side of the program that displays the email?
    - For example, do you put a specific string in the header indicating that it has been flagged as spam and ask the user to configure the sorting settings?

![image](https://gyazo.com/31c5a1dc3b9c17e5c05d247fed8d8b50/thumb/1000)
part-time job
- (7) If the person in the box is a part-time worker with no knowledge at all, what manuals do you need to provide? Thinking about this will make the next step easier.

![image](https://gyazo.com/06f41fcadaf35bf4c7dcd2209adeb929/thumb/1000)
Step 3
- Step 1: Human beings do it.
- Step 2: The person in the box does it.
- Step 3: The machine in the box does it.
- Replace the person in the box with a computer.

![image](https://gyazo.com/81315673a08b3471604deb5efd160bf5/thumb/1000)
First Program
- (8) Write a program for the computer in the box to do (2)
- It doesn't have to be perfect.
- Does not have to be a sophisticated algorithm
- Accuracy can be low.
- It's enough to say, "It works for now."

![image](https://gyazo.com/87559a341c14e9388f085dce931723b5/thumb/1000)
Run it and show it to your clients.
- (9) Put actual data into the program (8) and observe the behavior. (How is the accuracy? How fast is it?)
- (10) Will customers be satisfied with this?

![image](https://gyazo.com/e99aeb165521a181c983c563af3e9735/thumb/1000)
Afraid to show your clients?
- Afraid to show clients if it's not accurate?
- But only the customer knows what the customer values.
- Even if a customer says it's low quality, it's an opportunity to learn what the customer values. see "[[Lean Startup]]."

![image](https://gyazo.com/b39ca81e84965aadc16736a92a5892aa/thumb/1000)
If the customer is not satisfied.
- (11) Gather how you are not satisfied [[specific dissatisfaction]].
    - (What kind of output do you want for what kind of input? This is called [[teacher data]].

![image](https://gyazo.com/b1a9434f253aba06f7d81479b3ee77ee/thumb/1000)
Step 4
- Finally, machine learning!

![image](https://gyazo.com/f18fe3a70c5957694e082f39347edbe5/thumb/1000)
scientific methodology
- When the teacher data is enriched, the quality of the algorithm can be quantitatively measured.
    - (A portion of the teacher data is used for validation)
- Compare with program (8) neatly, because just because it is made into machine learning does not mean it will be better.
- Cycle of hypothesis, experiment, verification, and revision.
    - ( [[PDCA cycle]] / [[scientific methodology]] )
    - cycle and [[improve]] it.

![image](https://gyazo.com/8ad67b18a62bf39ad90f4fb10b16dc6f/thumb/1000)
Specific Methods of Improvement
- Extract and view "data that the current algorithm is unable to classify correctly" and consider what can be done to classify them correctly. (e.g., adding features).
- If the algorithm returns "confidence in the decision", such as logistic regression, then look at the "unconfident results" and add more teacher data. ([[active learning]])

![image](https://gyazo.com/09ad0d2020987f7ccfdb6e7e5159f610/thumb/1000)
I'll say it again and again so you don't make a mistake.
- What matters in business is customer value. Not accuracy.
- Even if the accuracy is 99%, if the 1% that makes a mistake is fatal to the customer, a program with 60% accuracy that does not make that mistake is more valuable to the customer.

![image](https://gyazo.com/434afc8e9a3fa8b193bb1d9e920cb3ff/thumb/1000)
summary
- Customer value is important in business.
- Neither the customer nor you understand exactly what customer value is.
- Repeat experiments with minimum man-hours for quick understanding (Minimum Viable Prodict)
- Experiments gradually materialize dissatisfaction and customer value.
- Iterate improvements to increase customer value.

![image](https://gyazo.com/b8723e89dee56ac0ffbcdbb63c5b175c/thumb/1000)
Supplemental information and questions/answers below

![image](https://gyazo.com/53c4188fa0b246a64536737c483e1619/thumb/1000)
supplement
- This is similar to "software development without clear customer requirements or specifications.
- The difference is that if a customer is dissatisfied, it could be solved by "adding that information to the training data" instead of "reworking the software".
- However, it is not always possible to solve the problem with data, so it is still important to experiment with minimal implementation.

![image](https://gyazo.com/1e2782fc81f6f34cb3a7c345987624d6/thumb/1000)
Supplement:Bad Pattern
- (1) Easy way
- (2) Textile data
- (3) Amazing Machine Learning
    - Use up all your time here.
- (4) Highly accurate output data
- (5) bumping into each other in a miscellaneous manner
- 6) Mismatch: Customer "this is not the one".
- (vii) Complaints without a snowball's chance in hell
To avoid this, it is important to have a form of experimentation that can be repeated.

![image](https://gyazo.com/028b6f361f287e5f4c71128096950f91/thumb/1000)
Q&A Manual Writing
- Question about (7) and (8): "If you can write a manual for a part-time job, shouldn't you also be able to write a program?"
- Yes, I did. What I wanted to say was, "If the specifications are so vague that you can't write a manual for part-time workers, it's impossible to write a program.
- How do you write a manual?" This is how we notice what has not yet been verbalized, and this is how we encourage verbalization. (See examples on the next page).

![image](https://gyazo.com/85cff9c46f65d0cd51d5d907b15e3894/thumb/1000)
- Example: Spam Filter
- What we want to achieve: >(2) "Look at the body of the email to determine if it is spam or not, and move spam to a different folder."
- You "look at the text to determine if it's spam."
- Byte: "How do you judge?"
- You say, "For example, if the word ____ is in there, it's spam."
- Noticed: You should make the first step program (8) "determine if NG keywords are included".
    - Supplement to the Supplement: The purpose of writing the manual for the part-time program is to help in writing the "first puerile program," so you can skip it if you can write the program without much effort.

![image](https://gyazo.com/4a3dfee51ecfe07b6d88a301aea93aee/thumb/1000)
production requirements
- Q: How many man-hours should I expect it to take?
- A: Case by case.
    - For example, when data is entered into logistic regression, which is a well-developed technique, sometimes the accuracy is so good that the client gives a one-shot OK, while other times it is completely inadequate. The only way is to experiment.
    - Since it is difficult to estimate man-hours, it is dangerous to enter into a contract that promises results in a fixed amount of time.

![image](https://gyazo.com/fc41f62b85bfe9cc2307f72bbfc8a771/thumb/1000)
accuracy
- Q: If a customer asks for an accuracy guarantee
- A: We need to make it a common understanding with customers that "we will not know how accurate it will be until we experiment with it.
- It is better to have a contract in the form of payment for "trial and error that may produce a good product" rather than a commitment to accuracy.
- We need to experiment with as small a unit as possible and communicate closely with customers.

![image](https://gyazo.com/080326429c6036788508564f241ef605/thumb/1000)
- Cost and accuracy of decisions
- Knowledgeable "experts" make decisions
- A "part-time" worker with no knowledge makes a decision.
- Machine determines
- The accuracy and cost of decision making is high up there.
- Machines don't get tired of working 24 hours a day and the labor department doesn't get mad at them.
- Accuracy is not necessarily high*, but lower costs create business value. (*Depends on your efforts)
- 2023 note: GPT-3.5 exceeds humans for a wide range of tasks.
    - [[ChatGPT Outperforms Crowd-Workers for Text-Annotation Tasks]]
    - So the "machine" is now more accurate than a "part-time worker with no knowledge."
    - The time has come to say, "It is better to use GPT-3.5 than to crowdsource teacher data to amateurs who have neither the knowledge nor the motivation to do so.

![image](https://gyazo.com/129dbf5d9009c5acb00cf6e9e5222364/thumb/1000)
Deep Learning
- Q: "Can't Deep Learning do this automatically even if a human can't define the conditions?"
- A: Half right.
- In the field of image processing, for example, even a 100x100 monochrome image is in the painful state of "there are 10,000 input values. Experts have been devising various conditions for decades in order to handle such inputs well.
- I created a special form of neural net that repeats convolution and trained it with a large amount of data, and surprisingly, it showed better accuracy than the one devised and implemented by the experts.
- This is the correct half. The incorrect half is on the next page.

![image](https://gyazo.com/6f6bcd421095ca0da5132434ecc692d1/thumb/1000)
Deep Learning
- This success draws attention to Deep Leaning, takes out the context, and warps the message game to say that Deep Learning can be used to create programs that make more accurate decisions than humans.
- As a result, more and more people think, "This too can be managed by Deep Learning" for problems with totally different conditions.
- Since the effectiveness of a method changes as the problem conditions change, the only basic rule is to "repeat small experiments in the order of the dead methods.

![image](https://gyazo.com/122c20f164c55c426df1f25b89a881dd/thumb/1000)
active learning
- Q: Is it better to do active learning with logistic regression rather than [[naïve Bayes]]?
- A: Naive Bayes is also a method that can produce a confidence level similar to logistic regression, so you can do active learning with Naive Bayes.
- Tip: Although I omitted it this time, both logistic regression and naive Bayes are "[[stochastic model]]", which is a model that produces outputs like "the probability that this input is class 1 is 0.8". This was expressed as "[[decision confidence]]" in this presentation.

![image](https://gyazo.com/4a3ee64749819d105511033f7af924f1/thumb/1000)
differential (e.g. calculus)
- Twitter Thoughts, "No matrices or derivatives showing up."
- When the machine adjusts the weights, it says, "Let's change the weights a little bit in the direction of a smaller deviation from the correct answer.
- In mathematical terms, this would be "Differentiate the 'deviation from the correct answer' by the weights to obtain the gradient, and change the weights slightly in the direction of the gradient.

![image](https://gyazo.com/866db9f8c322d2d08ee39ee3d403825d/thumb/1000)
matrix
- In logistic regression, for example, if there are 15 conditions, 15 values of "weight" can be created.
- The mathematical term for this is "vector".
- A neural net is a collection of multiple logistic regression-like pieces, so if 10 pieces are collected, 15x10 values can be produced.
- The mathematical term for this would be "matrix.

![image](https://gyazo.com/010ed83b713d9319fc3c8d5a32cf187b/thumb/1000)
Ambiguous judgment
- "P21 is 17/15 if, for example, x1, x2, x3, x4, and x6 are True, which is True. Mathematically incorrect."
- Yes, that's the important part (I forgot to emphasize).
    - The original equation and the weighted sum equation are not equivalent.
- However, when trying to use machine learning, we do not understand "what kind of conditionals will create customer value" in the first place.
    - Therefore, "being equivalent to the original formula" has no customer value.
- Let go of the need to describe things logically and properly, and instead express them in a messy and ambiguous conditional expression, and test them on real data, not logic, to see if they work properly. This is the basic stance of machine learning.

![image](https://gyazo.com/a694f0b35ecfdec0b7641b1086001d3c/thumb/1000)
Supplement (advertisement)
- I forgot to specify and emphasize that "It is important to observe the data.
- PyQ's "Machine Learning for Beginners," which I supervised, explains everything from observing data and making if statements to logistic regression, step by step, in small steps.
- Let's learn the basics of machine learning from if statements.
- Let's find the thresholds.
- Visualize and find thresholds
- How to handle data for which thresholds cannot be determined
- Classification from 2D data
- Plot 2D data
- Classification using linear equations
- Machine Learning for Beginners: Logistic Regression

---
This page is auto-translated from [/nishio/if文から機械学習への道](https://scrapbox.io/nishio/if文から機械学習への道) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.