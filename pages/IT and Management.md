---
title: "IT and Management"
---

- Tokyo Tech MOT Special Seminar [[2017]]-12-28 [[NISHIO Hirokazu]].
    - Title [[information transmission network]] and [[management]]
    - [MOT Special Seminar (12/28) | Event Calendar | School of Environmental and Social Science and Technology, Tokyo Institute of Technology, Professional Degree Program in Management of Technology / Innovation Science](https://educ.titech.ac.jp/isc/event_information/2017/054940.html)
- [slide](https://www.slideshare.net/nishio/it-85153914)
    - What is IT?
    - IT and Business Strategy
    - IT and [[parallel carrier]].


--Drafts of the following documents at the time of preparation--
I usually speak to software engineers and information technology college students, but this time, since I'm in management, I'll start by talking about IT.

What is IT?
- IT: Information Technology
- Dealing with information
- Computer use technology" in effect because computers are much better at it than humans are at handling it.
- A computer is something that computes, and computer science is called computer science in Japanese.
- A major step in the history of computing
    - 1952 IBM 701 announced.
        - 1071 vacuum tubes
        - Monthly rental fee of approximately $10,000 to $20,000
        - You know what happened to IBM after that.
    - 1957 FORTRAN announced
        - FORmula TRANslation system
        - The first "programming language" used by almost all modern programmers
- Instructions on what to have the calculator calculate are the "program.
- The "calculator" as a physical object and the "program" as insubstantial information
    - Before the split, wires were wired to describe the calculations.
        - [[ENIAC wiring scenery]]
- The former is called "hardware" and the latter "software.
- In the modern era, programming means to create a program using a tool called a "programming language" (= this itself is a program).

- The software engineer's job is to
    - Figure out what the computer can do,
    - Think about what you want the computer to do to create customer value,
    - It is then compiled into instructional information in a form that can be understood by a computer.
    - Design to create value more efficiently.
- Company management is
    - Figure out what each employee can do,
    - Think about what you want your employees to do to create customer value,
    - Put it into instructions in a form that employees can understand.
    - Design to create value more efficiently.
- Roughly the same.

    - [[Similarity -> What is the difference?]]
- Easy part, difficult part
    - Computers do not have emotions, so there is no need to take motivation into account. They don't get sick of their work and quit.
    - Computers cannot guess, so detailed instructions must be given.

- It is tedious to give detailed instructions!
    - Need to verbalize what it is that you want us to do
    - Especially in the case of outsourcing, etc., the "customer" who has something they want the computer to do and the "programmer" who instructs the computer to do it are two different people, so we need to do our best to verbalize what we want it to do.
- Programming languages have therefore been developed to facilitate giving instructions
    - [http://archive.oreilly.com/pub/a/oreilly//news/languageposter_0504.html](http://archive.oreilly.com/pub/a/oreilly//news/languageposter_0504.html)
    - Upper left FORTRAN

- Hello! in C
C

```
#include<stdio.h>

main()
{
    printf("Hello!\n");
}
```


- Python for Hello!
python

```
print("Hello!")
```


    - This is a poster made in 2004
    - What has happened in the last 10 years?
        - Objective-C has long been used to create programs on Apple products
        - Swift Release
            - ObjC was released in 1984
            - Swift was released in 2014
        - Death of Flash/ActionScript
            - iPhone decides not to carry Flash
            - HTML5/JavaScript breakthrough
            - YouTube was founded in 2005 and became famous for video playback using Flash
                - In 2007, Apple releases the iPhone. However, Flash was not available on the iPhone.
                - Adobe declared that they will discontinue support for Flash in 2020 (in July of 2017. That's awfully recent!)
        - Visual Studio 2005 Express Microsoft offers programming language free of charge
            - Programming language sales market scorched.

- Python's market share has expanded dramatically due to the boom in machine learning and artificial intelligence
    - ![image](https://gyazo.com/88343f390f12b36c48cf70fe28f2047b/thumb/1000)
    - [https://spectrum.ieee.org/computing/software/the-2017-top-programming-languages](https://spectrum.ieee.org/computing/software/the-2017-top-programming-languages)

    - Excel Python
    - At this time, it is still possible to use Python to manipulate Excel. Also supported by Pandas, a well-known data analysis library.


- Special Manufacturing
    - Using language (programming language) as a tool to create things
    - The word itself is the object of creation.
    - That language changes depending on external factors.

- Douglas Engelbart
    - intelligence enhancement

- Create a concept
    - Assignments, functions, recursive definitions, modules, classes, traits
    - character string
    - Concept of Variables
        - It's just a series of zeros and ones in memory.
        - Read and write by specifying the number
        - It's hard on people.
        - We made it possible to give it an easy-to-understand "name".
        - x = 1 to write to the address in memory associated with the name x
    - Function Concepts
        - Enable reusability by giving easy-to-understand names to parts of the code that are used repeatedly
        - Major difference from physical manufacturing
            - In physical manufacturing, if 100 units of a certain component (e.g., a water tap) are used, the cost of 100 units will be incurred.
            - In information space manufacturing, even if a function is used in 100 locations, the cost of creating the function itself is constant.
            - Strong incentives to make reusable parts
            - Of course, a design that is divided into parts will have overhead at the joints of the parts, which will reduce global performance. It is the same as physical manufacturing. #Modular and Integral
            - But Moore's law

    - Technology Supporting Coding
    - ![image](https://gyazo.com/576f6977667de721f0a9a0165f5c10e5/thumb/1000)
    - The book was published in April 2013 and is still often mentioned positively on social networking sites

- CUI and GUI
    - Graphical User Interface
    - It was easy for the average person to catch on.
    - Like communicating by gestures of pointing at things.
    - With the advent of voice user interfaces, "verbal instructions" spread to the general public.
    - The effect of the easier process is to widen the gateway to the market.
        - The same way that the need for memory management has increased the number of programmers by eliminating the need for memory management.
    - Will I lose my job?
        - Gone is the job of piecing together the wires.
    - The demand for programmers in the current sense may decrease, but instead there will be more "something programming" that more people take for granted.
        - Ministry of Education, Culture, Sports, Science and Technology Programming education in compulsory education
        - Mastery of Programmatic Thinking

What is Agile Development?
- The speed of change in IT and the low "cost of redesign" due to the fact that it was information and not physical objects made it a good fit with agile development, which emphasizes speed of learning.
- Explanation of what Agile is
    - First of all, the term business strategy has many meanings, strategy safari.
    - There are two schools of thought.
    - It is important to learn effectively from the environment and adapt to change."
    - It is important to analyze your company's strengths and weaknesses and formulate strategies accordingly."

    - By comparing the two ideas, we can see what is not written.
        - When one says, "It is important to formulate a strategy based on a thorough analysis of your company's strengths and weaknesses," there is an implicit assumption that strategy formulation is done in advance and then it is implemented. It is missing the perspective of what to do if you realize the mistakes in your strategy during the implementation phase, and how to learn from the environment.
        - Conversely, when one says, "It is important to learn effectively from the environment and adapt to change," there is an implicit assumption that the environment is subject to change and that it is inevitable to take time to develop strategies in advance. This means that prior strategy formulation is being disregarded.
    - [U Theory and Agile have the same root: ────U Theory, Ryo Nakadoi (4) / NISHIO Hirokazu's "How to Learn to be a Continuous Engineer" | Cybozu Style](https://cybozushiki.cybozu.co.jp/articles/m000930.html)

    - Neither is the right answer.
    - The author feels very close to the idea of learning schools. This is because I feel that it is very important to learn from the environment and adapt to change, not only in the management of a company, but also in the "self-management" of an individual engineer.

- Some of you may associate the term "agile" with the idea of "designing a specification well in advance and then implementing it. Although the definition of the word "agile" is not very clear, it can be said that it is a development style in which the client is provided with the product quickly, and the specifications are changed based on the results of the customer's experience. The relationship between these two development styles is similar to the relationship between design schools and learning schools described above. Learning efficiently" is the goal of agile development.
    - [[Lean Startup]]
    - Management books often referenced and referred to in the IT industry
        - [[Construction, measurement, and learning loops]]
    - Startup Management Theory
    - Proceed with spending limited money.
    - Before money runs out, you have to find "customers" who will pay you for what you create.
    - The idea that "if we make this kind of product, it will sell" and the hypothesis that "there are customers who will pay for it."
    - Hypotheses must be tested.
    - We need to verify this as soon as possible, and if it doesn't look right, we need to change our policy.
    - If you spend all the money you have to make version 1 of your product and there are no customers for it, you will go bankrupt.
- Despite differences in detailed constraints, Lean concepts can be applied to a wide range of areas

The Era of Parallel Careers
- Prime Minister's Office Workplace Reform
- Revision of the MHLW Model Employment Contract
- Federation of Economic Organizations (Organisation)
    - [Company employees to be allowed to work side jobs and concurrent jobs, Keidanren changes policy - SankeiBiz (Sankei Biz)](https://www.sankeibiz.jp/smp/business/news/171218/bsg1712180500002-s1.htm)
    - [Keidanren does not recommend side jobs, affects core business, difficult to manage : Kyoto Shimbun](http://www.kyoto-np.co.jp/economy/article/20171218000200)
- To all the graduate students now, in your parents' time, it was common to work for only one organization, with no side jobs allowed.
- The image of "job hunting" after graduating from college, joining a large company, and working there until retirement.
- Drucker's Parallel Career
    - Year 2020
    - Japan
- Large companies: companies that do not go out of business
    - Longer life than humans in Japan
    - Company born before the development of IT technology
- Pressure to create something new
    - Need to obtain knowledge from outside the organization
    - open innovation
    - Man as a Vehicle of Knowledge
        - Where knowledge is stored, it can be electronic.
            - The ability to observe a situation, isolate key features, and then retrieve "written knowledge" that can be applied to the situation.
        - Where we create "new bonds."
            - Some people say things like, "Computers can't do that," but I disagree.
            - All I can say is, "Where computers can do it, they will do it quickly and it will not lead to competitive advantage."
            - It is slightly outside the boundaries that creates competitive advantage

    - physical aggregate
        - Location dispersion
        - Time Asynchronous
        - Scrapbox
            - Masui Lab.
            - University = place where most people are gone in 4 years = 25% turnover

- Venn diagram, overlap
    - communication cost
    - How is a common vocabulary acquired?
    - As a member of a community
    - collaboration


- Communication difficulties
- Different organizations have different objectives.
- Prisoner's dilemma, optimizing each other individually and then falling into a solution that is not the overall optimum.
- A solution to the prisoner's dilemma, introducing an observer
- Factors contributing to the formation of this network structure
- Networking system for projects conducted by IPA
- College is a promising option
    - Networking with people who will be in different positions after graduation
- For companies, maintaining relationships with retirees and parallel work

- [[Lecture Draft]]

---
This page is auto-translated from [/nishio/ITと経営](https://scrapbox.io/nishio/ITと経営) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.