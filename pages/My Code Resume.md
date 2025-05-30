---
title: "My Code Resume"
---

> It would be interesting to enumerate what I have written so far since I started the program.
[https://satoru-takeuchi.hatenablog.com/entry/2020/03/17/153715](https://satoru-takeuchi.hatenablog.com/entry/2020/03/17/153715)

I tried.

- My father bought a JX and brought home a computer with BASIC on the ROM and a manual that came with it that explained programming in BASIC.
    - [https://ja.m.wikipedia.org/wiki/IBM_JX](https://ja.m.wikipedia.org/wiki/IBM_JX)
- I implemented a neural net after reading a newspaper commentary; I could get it to remember 0+0=0 and 1+0=1, but it just wouldn't remember 1+1=2 (just when I thought it had learned it, it forgot something else).
    - Looking back, I implemented a single-layer primitive neural net after seeing only the explanation and illustration of the Hebbian rule, so I could not solve linearly non-separable problems. I had chosen binary addition as an easy problem, but XOR in the addition is a typical linear non-separable problem.
    - [https://ja.m.wikipedia.org/wiki/ヘッブの法則](https://ja.m.wikipedia.org/wiki/ヘッブの法則)
- Wanting to do 3D, I made a program to rotate a cube using trigonometric functions as hard as I could. However, I didn't know about perspective projection, so I simply used the "ignore depth direction" method of parallel projection, and I didn't know about shading. If you are familiar with 3D, you will know that it looks like a "rectangle that expands and contracts. I was disappointed and quit.
- My home machine will be Windows; I'll get Visual BASIC. I made a little launcher and memo application. At the time, a magazine with a lot of freeware on CD was popular, and I received many requests to include it in the magazine. I took it to a used bookstore under the Sannomiya elevated railway tracks to see if I could sell it to a used bookstore, but was turned down.
    - He joined a mailing list with his father's e-mail address and posted the contents of the binary as it was, and he said, "To solve the problem of shareware passwords being distributed illegally, we can create a fake keyword that formats your hard drive when entered and mix it into the list of illegally flowing passwords. I got into a big fight with an adult by arguing that "if the risk is raised enough, it will be impossible to abuse the system. Too risky. Fortunately, I didn't do it (as I recall), but there were people who did and it became a problem.
        - [https://ja.m.wikipedia.org/wiki/WinGroove](https://ja.m.wikipedia.org/wiki/WinGroove)
- An "escape game" based on my paintbrush drawings, in which the story progresses when you click on a suspicious place.
    - I remember that the quality of the pictures was terrible, though they are now a shadow of their former selves.
    - My mother is great for looking at that awful graphic game and praising it with open arms.
- Artificial incompetence boom, CGI-powered chatbot was not playable enough due to the fact that internet connection was metered except during telehodai hours after 11 p.m. at the time, so a ported version was created to work offline.
    - Started building a kind of template engine for embedding variables (like calling them by name), and implemented conditional branching, etc., to create a mysterious home-made programming language.
    - Well, if you convert a string substitution template engine into a programming language by cheating, you will fall into the trap of evaluating the contents of the else clause of an if statement even when the conditional clause is false. I didn't have concepts such as "side-effects" or "positive evaluation and delayed evaluation" at the time, so I enclosed tags that are usually enclosed in curly brackets in square brackets and added something like a corrupt eval that "converts square brackets to curly brackets and then re-evaluates the string" (see below).
    - If I were to evaluate that language today, I would say that it was "a combination of the bad parts of LISP and PHP".
    - People who programmed in such languages appeared, some of whom had no programming experience and were liberal arts majors. Perhaps because of this experience, I am opposed to the idea that programming can only be done by a few talented people, and I believe that it is simply a matter of not finding the right combination of an "interesting subject" and an "understandable explanation.
    - A junior in middle school and high school did an interesting thing by porting this program to Delphi, DLLing it and making it callable from an external program, but I did not understand the fun of it at the time!
    - I had built in a mechanism to launch an external exe and delegate processing within the artificial incompetence process, but now that I think about it, I've built in some amazing vulnerabilities.
- My high school friends and I went to a venture company in the Amagasaki area and got a system for making various things with VRML.
    - The president claimed that the incubation facility was established because he submitted a proposal to the local government, and I thought, "Oh, that's not so bad.
- When I entered college, a venture company near my office lent me a server connected to the Internet for free, so I started making what would become my homepage. Then, I set up the Perl code of KENT CGI, read it, and started modifying it.
    - I wasn't sure about the decoding part of the POST request, but the exchange part was a black box because the decoded stuff was passed over to the main process.
    - I enjoyed playing a game called Nethack or something like that at the terminal, so I wanted to set up a game on my web page as well, so I created a text-based game that progresses by selecting links such as "right, left, straight ahead," etc. The game is based on a modified version of KENT's bulletin board CGI, so comments can be left on the dungeon walls. The fact that they gradually disappear as people pass by is also an imitation of Nethack.
- I participated in a local research group and talked about the above conversation application, which somehow led to a path among some important people, and I ended up joining a company that was making an online 3D virtual world in Keihanna at the time as a part-timer, looking at C++ physics and network communication code. I looked at the C++ physics and network communication code, but I didn't have much to contribute. I was so excited when the system had the ability to incorporate scripts written in Python that I created a lot of different worlds.
    - Specifically.
        - World where you can shoot an electron gun and observe it distorted by the magnetic field, with monopole
            - I use a lot of vector operations, and I've had the experience of replacing a vector arithmetic library that my seniors here were building with what they thought was a "good design" using classes and such, and the performance deteriorated dramatically.
                - In short, in situations where you need to update "position" and "velocity" vectors dozens of times per second, if you make all those vectors Python objects and then create a new object for each operation, the overhead is huge. I can see that now.
                - It's harder to plant strange bugs if you don't do destructive updates to objects, but performance will suffer. We have learned that kindness to humans is often at odds with kindness to computers.
        - World where objects are suspended by nonlinear springs and their trajectories can be observed.
        - 3D game with tutorial-like controls
            - I was impressed by the usefulness of mathematics when I realized that I could use Gramschmidt, which I had just learned in a linear algebra class in college, to solve the problem of pointing an arrow in the direction of an object here.
                - [https://ja.m.wikipedia.org/wiki/グラム](https://ja.m.wikipedia.org/wiki/グラム) and Schmidt's orthonormalization method
        - I'll give you an octopus with physics.
        - World where Brytenberg's car is placed inside a duck avatar and a genetic algorithm is used to evolve its behavior.
            - [https://en.m.wikipedia.org/wiki/Braitenberg_vehicle](https://en.m.wikipedia.org/wiki/Braitenberg_vehicle)
            - ![image](https://gyazo.com/ef6458fa6483f4c1e42850fa552f646a/thumb/1000)
            - Image right. It is written "Breitenberg" on the kanban. A guy like Domo-kun is a carnivore. They exert culling pressure by eating ducks. The 3D model of this guy was made by me with metasequoia.
    - It's 2001, so two years before the release of Second Life.
    - This is where I first encountered Python. And the idea of "embedding a scripting language processor in an application made with a compiled language.
        - Leading to the first book "Jython Programming" later
    - Hear about the implementation of a physics engine. It doesn't have to be the right physics, it just has to be fast enough and behave like it. Acquire the concept of pragmatism, that it is better if it feels natural to the user than if it behaves the same as in reality.
        - It led to GRINedit, a graph visualization software that put in different physical laws from reality.
    - The inclusion of transparent polygons in the virtual world made it necessary to sort the polygons, which worsened performance. Then a senior colleague improved the sorting algorithm, and performance improved dramatically.
        - I thought we changed the quick sort to a heap sort?
        - Of course I had learned about sorting types and such in my college classes, but I thought quick sort was fine for now. I realized here that knowledge of algorithms, and proper selection, can lead to practical, real-world benefits.

I was told about the unexplored youth at this part-time job and applied for it, but I'm tired of writing about it from here, as the story of the unexplored and the 18 or so years that followed still continues!

itemized list of miscellaneous items
- Unexplored money buys Delphi
- I'll do Java too.
- Part-time work on consignment for i-mode applications
    - Size restrictions are terrible.
    - Copyrighted material is a pain in the ass for rights holders.
    - Distrust of the media after witnessing newspaper articles that say things like "due to years of research and development by the ordering company" when the commission was written about.
- Graduate School
    - Visualization of Gene Expression Information by Java Applet
    - Converting the lab website to Zope, a CMS made in Python that was popular at the time.
    - To teach programming to younger students, he created content that explains the behavior of Python and Java while comparing them. This is where the idea that "comparing multiple languages leads to good understanding" in his later book "The Technology Behind Coding" was born.
- finding employment
    - At any rate, since we are a web app company, we decided to make a web app, so we created a website in Django that allows users to post their answers to a given question in various languages.
    - Feeling guilty about making the company pay for the server when there was no way to monetize it, the company ported it to Google App Engine and tried to run it on a free framework -> catastrophe.
    - I am acutely aware that the maintenance and operation of the service is not in character.
- Art Activities
    - Context-free art → performance problems → generate and render SVGs on your own → SVG renderer dies
    - Implementation to create a numeric type that handles numbers containing root 5 without arithmetic error for branch pruning and render it by itself with libpng.
- Motivational Systems
    - Static HTML+JS, hating to run servers
    - I decided to send the data for future machine learning encoded in GA
    - I was thinking of making it work like Akinator.
    - But the user's needs are satisfied by mere if statements without the need for machine learning.
    - Retrieving data that has been encoded and plugged into GA is more of a hassle.
- kintone recommended graphs
    - Putting so-called AI stuff in products.
    - This case was, well, a case where we needed to create an evaluation function, but I thought that most of the world's needs could be met with a more simple solution.
    - The man-hours to make it truly worthwhile are too heavy, and it tends to be implemented in a way that does not allow it to be truly worthwhile.
- JA Delivery Route Automation
    - optimization problem


---
This page is auto-translated from [/nishio/私のコード履歴書](https://scrapbox.io/nishio/私のコード履歴書) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.