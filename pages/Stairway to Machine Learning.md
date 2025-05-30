---
title: "Stairway to Machine Learning"
---

- [[stairs]] to [[machine learning]]

First.
- What computers can do is "automate decisions" (using physical robots is not considered on this slide).
- The accuracy of decision making is basically lower than that of a human being, who can instead make decisions faster, massively more quickly, and without tiring.
- This "low-precision but fast, automated decision making" is the source of the value we provide to our customers.

# Step 1
    - Q1 What makes customers happy?
        - What is the customer value?
    - Q2 How would a human being do that?
    - How you would do it if you were doing it yourself
    - Don't think now about things like "too much, too much, too much."
- ![image](https://gyazo.com/d2219d15dac5753025db78c274331857/thumb/1000)
- Specific example (spam filter)
    - Q1 What makes customers happy?
        - A1 Customers have a problem with a lot of spam in their mailboxes, and would be happy if the spam would go away.
    - Q2 How would a human being do that?
        - A2 If it's done by a human, look at the body of the email, determine if it's spam or not, and move the spam to another folder.


# Step 2
- Think of a human being in a box.
    - Suppose that only electronic data can be put into this box and only electronic data can be put out of this box.
    - You might imagine remote work or something like that.
- question
    - Q3 What input data needs to be placed in the box for a human to perform the activity in Q2?
    - Q4 What output data does a human need to produce from the box for the activity in Q2?
    - Q5 How do I get the input data for Q3? (First step and how to do it continuously)
    - Q6 How do we connect the output data from Q4 to the customer value in Q1?
    - ![image](https://gyazo.com/d43778a0a3dc75e29a7b1585e4839f60/thumb/1000)
    - The order in which they are answered may be interchanged.
        - For example, going back from a customer
            - Because I want to do these things for my customers (Q6)
            - I need this kind of data for that (Q4)
            - I need this kind of input for that (Q3)
            - How shall I obtain this? (Q5)
        - For example.
            - This kind of data is available now (Q5, Q3)
            - How do we create customer value from this? (Q6)
            - What kind of output is needed for this? (Q4)

- concrete example
    - > Q1 What makes customers happy?
        - > A1 Customers have a problem with lots of spam in their mailboxes, they would be happy to get rid of the spam
    - > Q2 How would a human being do that?
        - > A2 If it's done by a human, look at the body of the email, determine if it's spam or not, and move the spam to another folder.
    - Q3 What input data needs to be placed in the box for a human to perform the activity in Q2?
        - A3 Information in the body of the email is required for Q2 activity
            - If I could have the title and sender as well as the text, I would.
    - Q4 What output data does a human need to produce from the box for the activity in Q2?
        - A4 Output "spam, not spam" label for each email
    - Q5 How do I get the input data for Q3? (First step and how to do it continuously)
        - As a first step, if you could export your email for now.
        - To do this on an ongoing basis, I would need to create a way to get the data from the mailer or modify the mail server side.
    - Q6 How do we connect the output data from Q4 to the customer value in Q1?
        - Mailer sorts mail based on labels that are/are not spam
        - I thought earlier that Q4 outputs "is/isn't spam", but it could be "output a list of non-spam emails" here.
            - You may want to change your answer to the previous question while digging into such things as
            - In such cases, instead of retroactively and destructively rewriting, it is better to save what you have written so far as "Draft 1" and make a separate list of answers.
            - Draft 2" with Q4 rewritten to "Output list of non-spam emails" may change the answers to other questions.
            - Because if you're retroactively and destructively rewriting things, you're going to get inconsistencies and things that are going to be confusing. What we are doing now is a process of dividing our thinking so that it is not confusing, so we should avoid anything that might be confusing.

- Preparing for the next step
    - Consider that the person in the box is a part-time worker with zero business knowledge.
    - (7) Prepare a manual for this part-time worker to be able to do the job.
        - It doesn't have to be a perfect manual, it is a preparation for what you will consider in the next step, so write it down roughly and move on.
    - ![image](https://gyazo.com/9c53709f6ff7978a316ec41c8b1193fa/thumb/1000)

Step 3
- Consider that the person in the box is no longer [[a flesh-and-blood person]] but a computer.
- (8) Write a manual (=program) for this computer to do the job
    - ![image](https://gyazo.com/83e13a4a5ae08e43ecd103ac5d583ecf/thumb/1000)
    - It is not necessary to write a program that can judge perfectly
        - If it were a problem that could be exposed to a program that could judge it perfectly, we wouldn't have any trouble.
        - A naive algorithm, a few if statements or something like that, is all that is needed.
        - No need to be highly confident of accuracy in advance.
        - Better than random" is about right.
        - At least something that works for now.
            - The goal is to be able to "try out the data".
        - Clarify what's wrong with your writing and what you don't know yet.

- (9) Put actual data into the program and observe its behavior.
    - How accurate or how fast?
    - Q10 Will the customer be satisfied with the performance? If not, what is missing? (Accuracy? Speed?)
        - If a naive program is sufficient, there is no need to use machine learning. You should not use it.
- (11) Create teacher data
    - Compare the program's output with human judgment and record whether it is correct or incorrect, and if not, what is the correct answer.
    - This data is essential for supervised learning in Step 4
    - The amount of this data has a significant impact on accuracy.
    - A sufficient amount of data is needed. However, "how much is enough" is problem-dependent and cannot be determined without trying.

- Example
    - (8) Programs that determine spam if certain keywords are included
    - (9) Observation.
    - A10 If this is sufficient, there is no need to use machine learning to create spam filters.
    - (11) Create teacher data
        - For example, an example of an incorrect judgment is
            - It's not spam, but there are keywords.
            - Spam but no appropriate keywords
        - is possible. The latter can be done by adding keywords, but the former is difficult
        - It means that it is now necessary to utilize "ambiguous hints" that cannot be divided by True/False
        - So [https://www.slideshare.net/nishio/ss-53221829](https://www.slideshare.net/nishio/ss-53221829)

Step 4
- Supervised learning is to let the machine itself create a manual from the "input and correct data" pairs prepared in 11.
    - ![image](https://gyazo.com/8d188467ad4889e1abf200c795f8fd16/thumb/1000)
- (12) Perform supervised learning using the "input and correct data" pairs prepared in 11.
    - Check the distribution shape in each dimension of the input
    - First, check accuracy with logistic regression (baseline)
        - Ensure that the customer's needs are met
    - If the accuracy required by the customer is not reached
        - Observe what features seem important in the decision tree
        - Devise ways to process data (feature engineering)
        - Go for new data.
        - (I wrote it this way just in case, but since the accuracy is not something that can be reliably improved by making the effort in the first place, the contract should not be structured in such a way that the system must be up to the level required by the customer).

Step 5 Active learning
- Put "data with no correct answer yet" into the model created in (12), and sort and display in order of least confident in judgment.
- By teaching the answers to these questions, humans can efficiently create data for training.

- v0.1 [https://www.slideshare.net/nishio/01-68382174](https://www.slideshare.net/nishio/01-68382174)

---
This page is auto-translated from [/nishio/機械学習への階段](https://scrapbox.io/nishio/機械学習への階段) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.