---
title: "Builderscon 2018"
---

Events [official website](https://builderscon.io/tokyo/2018)

- Interesting.

- It's been a while since I attended an engineering festival of sorts, and it was great. I used to attend, but not for a while recently, and I think I need to be proactive about it.

- If we don't regularly bathe in the energy of pure creation, which we create just because we want to create it, without thinking about its usefulness or anything else, we will run out of vitamins for our minds.

- What's good about it.
    - "I made it shine just for the heck of it," "I wanted to make it, so I made it."
    - Filled with pure "engineering principles".
    - I'm dazzled that I used to be like that (more than 10 years ago).
        - I'll write the details on another page when I feel like it [[negative personal history]], since it would be "abrupt self-talk" if I write it here.

- Why did you participate in this event?
    - Electronic nameplate. See [[digital nameplate]].
    - The blog post went viral on Facebook.
        - [Unusual Efforts in Electronic Name Tag Development or How I Stopped Worrying and Started Making 'Mystery Gadgets' - builderscon::blog](https://blog.builderscon.io/entry/2018/08/09/100000)
    - I bought it right away because it said, "You can get it if you buy a sponsor ticket."
    - Because the cost of the parts alone is likely to be around 10,000 yen, and if you add the labor cost of the trial and error to make it work, it's clearly a bargain.
    - [2018-08-10 Facebook](https://www.facebook.com/nishiohirokazu/posts/10216022060800871)
        - > If you purchase a digital nameplate, it comes with a ticket to the event.
        - > I'll have to remember to go to the event... it's not mail order, so it won't be delivered to my house...

- as a matter of fact
    - I didn't grasp that Cybozu was sponsoring the event.
        - Maybe I saw it in our internal kintone, but instantly forgot about it.
    - I knew uchan_nos was going to talk about OSS policy somewhere, but I didn't remember it being here.
    - I didn't grasp that Thursday was the eve of the festival.
    - I didn't grasp what I needed to pre-register for the reception.

The following is a quote from my Twitter feed without any particular source indicated.

Thursday
- the eve (of festival)
    - ![image](https://gyazo.com/6abd61366b3b4e754c54aed9b1c5be54/thumb/1000)
    - uzulla: toast & wearable mystery gadgets."
    - cho45: after my own BLE keyboard.
        - > I've been away for a long time, but I'm starting to feel like I should attend these events more often.
    - kazuph: The Dark Side of IoT Development."
        - SNS ban presentation
        - I'm scared. I'm scared."
        - > I enjoyed the "Don't Tweet" announcement. I really liked the preamble of "I'm scared... scared... scared..."
    - KAYAC hara: The Virtualization of Humanity
        - 'It's hard to interview someone who doesn't have their own avatar, their own identity.'
        - [Ask Kayak about the benefits of VR hiring interviews What personalities can be seen through original avatars [[Weekly VRChat]] - PANORA []](https://panora.tokyo/66480/)
    - Pepabo Make Dept.: Demo 00 Series - Fireworks at the end of summer.
        - [I built a robotic ball Omicro - Hardware is Hard - Medium [https://medium.com/tichise/%E3%83%AD%E3%83%9C%E3%83%86%E3%82%A](https://medium.com/tichise/%E3%83%AD%E3%83%9C%E3%83%86%E3%82%A) 3%E3%83%83%E3%82%AF%E3%83%9C%E3%83%BC%E3%83%AB-liveball%E3%82%92%E4%BD%9C%E3%81%A3%E3%81%9F-7185b45f6e88]
        - > mbed has libraries on the official website, so it's easy to find from IDEs, etc. / mbed has fewer libraries and examples than arduino.
        - > Elecrow, you even cut the acrylic?
- IoT-like presentations were gathered, which was just right for my interests.
    - very deep in the dark
    - We need to make it shine anyway.

Friday
- ![image](https://gyazo.com/f6432693f40b72608c2fa3fa9b9dabca/thumb/1000)
    - [https://twitter.com/jollyjoester/status/1037873641541623808](https://twitter.com/jollyjoester/status/1037873641541623808)
- Talk about a Raspberry Pi in serious industrial use."
    - > CI for embedded devices, Raspi directly connected to the microcontroller of the installed device, push to the repository, Jenkins will make a binary and Raspi will write to the microcontroller, I see... super convenient!
    - > Raspi collects logs and throws them over the net.
    - Discover something new
        - J-Link has binaries for ARM, so you can write microcontrollers from RasPi.
        - For hobby purposes, ESP systems that connect to Wifi are popular, but they consume electricity. nRF52, a BLE microcontroller, is a good choice.
- 「Algorithms in React」
    - > This is a very helpful story as I recently started using React: the traverse that used to be implemented with recursive calls in React blocks the UI when it grows too large because it can't be interrupted, so the recent React has made it possible to interrupt it using fiber.
    - > It's very good to explain what problems existed in the old implementation, how they changed it, and how it forced library users to change the way they wrote it (e.g., asynchronous state updates).
    - > The priority of side-effects. User input events are high priority, so if you do heavy processing there, the input is blocked and the user is uncomfortable.
    - > Suspense, a mechanism similar to error boundaries, which throws promises instead of errors. It is caught immediately inside the library, and the parent link is traversed asynchronously. You can only issue a loading if it takes a long time.
    - > Suspense, interesting and seems very important to reduce user stress, but it doesn't seem very dead yet.
- Understanding Static Inspections Without Prior Knowledge.
    - > It was a good explanation of what a person with no prerequisite knowledge needs to know when they decide to do a static inspection, but it was hard to see the slides when looking forward, and the annoyance of falling asleep when your gaze goes down to the slide at hand...
    - > Since many languages that have libraries for creating abstract syntax trees do not need the entire first half of the parsing implementation, it would have been better to show the second half first, as if it were there first.
- The "True Story! A year in the development of a 'mystery gadget' as seen by a person in charge."
    - > "Let's keep buying and trying devices we don't understand!"
    - > "Convince them it's not new" lol.
    - > Knowledgeable about how to buy screws.
        - Buy a little of each kind at Nishikawa Electronics, assemble them at a nearby cafe, identify the correct screws, and then go back for more.
    - > MDF from 100 yen store stinks lol
        - I also used a laser cutter to cut MDF sold at Techshop, but all I could smell was wood, so I thought the MDF from the 100 yen store was just inferior.
- The World of JavaCard."
    - How Java is running inside the IC of SIM cards and credit cards!
    - > I can't use big primitive types, I can use floats and ints only here and there" What is big lol.
    - > Java card looks interesting but too hard mode to create an environment to write in lol
    - > Even if there are multiple applets, they are not preemptive, so if you don't let go of the process, it will always run, and you have to know who to pass the process to and issue an explicit instruction to select it to switch the initial state... Was it necessary to separate the applets?
    - > I was sitting in the lowest seat for two sessions in a row and I started yawning like crazy, so I moved to a higher seat because I thought I might have acid indigestion.
- lld - a story about creating from scratch one of the main components of a development tool."
    - > I feel like I'm taking one step at a time, watching my step very carefully.
    - Bump Allocator is fine as it is not needed in the middle of the process.
    - Split into tasks and parallelize them, which looks like a clean design but is actually too complex to be fast.
    - Parallel for only highly parallel processes
    - If someone doesn't take responsibility for keeping it clean, it gets dirtier and dirtier.
    - >  "[[CARGO CULT]] doesn't, it's not right to follow the default values that were decided in the 1980s, and if it's unreasonable to reason everything out, we won't follow them just because that's what the past has done."

Saturday
- Security, Privacy Protection, and Performance in Next Generation Communication Protocols."
    - > Hot Battle between Enterprise Firewalls and TLS1.3
    - > An interesting battle between stakeholders.
    - > [ono_matope](https://twitter.com/ono_matope/status/1038241826350583808) If a carrier's middlebox reads the QUIC protocol and optimizes it, protocol rigidity (ossification) This makes it difficult to improve the protocol. Hiding information and explicit export is important.
    - I guess even >TCP is not immortal.
- "Technical Choices and Project Management Failures Faced in a Project to Break Dependence on Excel in Securities Trading Operations."
    - > "Abolish all Excel, in 4 months" It's impossible...
    - > I think it's not Excel's fault after all, but rather the situation of organizations that don't realize that Excel is indispensable to their business and are forced to follow the technological choices made by people three levels above them in foreign countries...
    - > The architecture proposed by the presenter certainly sounds like it would be a good idea, but it doesn't sound like it would be adopted in that organizational situation, and maybe changing jobs was a realistic solution.
    - > The IoT darkness story on the eve of the social networking ban was interesting, the Excel story was interesting, and sharing failure stories is a great way to learn by proxy what you haven't experienced.
    - > What is the difference between useful and unhelpful negative talk?
- Lunch Session (VOYAGE GROUP Inc.)
    - > I got in line to experience the lunch session and it was ajitoFM live and I sat at the front of the line even though I had never heard of it, so awkward lol.
    - > "Natural work assignments and aquaculture practice assignments," "I've never been taught how to teach, and now I'm being asked to teach."
    - > "I was wondering if there was any significance to the existing code, but there wasn't, and it became fun once I realized I was free to rewrite it." lol
    - > "There's a lot of natural products work that involves reading, interpreting, and rewriting code written by others."
    - > "There is the curse of the middle-aged man who goes too far and is cursed with the middle-aged man of his past."
    - > "The complexity of the writing process is a complexity that we engineers brought with us."
    - > "It would be good to have a design pattern on migration," "Refactoring alone will not change the behavior model," "I am having trouble increasing the number of aggregation axes in an app design that was designed 9 years ago."
    - > I guess the natural problem is that a lot of things are intricately connected, and aquaculture is being cut out. Is it important how to cut up [[making finite]] a large amount of intricately connected information?
- Who says you can't E2E test hardware? - Methods to Automate IoT Testing."
    - > I never thought of running Jenkins on a Raspi, but it looks good!
    - > Communication between RasPi and Arduino, putting JSON on serial?
    - > I became a fan of Akern, a device tested a million times.
- Who Owns the Patches Written on Work Time? The Trap of OSS Activities"
    - > Is it OK to release patches written during work hours outside the company? Who should I ask permission from? Is it under the company's name or my name? Who signs the CLA? The trap of "Who signs the CLA?
    - > Limited to the conditions under which the copyright belongs to the company, contains confidential information, or was created under the express direction or approval of a superior. Hobbies Patches to OSS are automatically transferred to the individual.
    - > "For CLAs that have been legally confirmed, a common employee may sign in the name of the president." strong
    - > No, no, no, there was a process of holding briefings and soliciting opinions from many people along the way, lol.
    - > Maybe you didn't get the message that the basic premise is that an employee work is automatically a company work, and that we are expanding individual discretion by explicitly limiting or automatically assigning it?
    - > You're so sharp with your questions about labor management, or if the patches that were automatically transferred contained something that infringed on another company's patents...
- Why do I make keyboards?"
    - > The keyboard swamp session is overflowing with people and standing around, but isn't the swamp too big already? LOL!
    - > I'm tempted to buy a whole set of switches (swamp).
    - > "Is it OK if my pinky and thumb are on the same axis?" me "Ta, indeed! Swamp
    - > Could it be possible to give a click feeling only in the home position?
    - > I see, you have two so you can fail twice lol.
    - > I'll get one that doesn't require soldering...
    - > "Burn PCB with temperature control soldering iron" Why not?
- LT
    - [Support for engineers to speak at the conference - connpass](https://engineers.connpass.com/)


---
This page is auto-translated from [/nishio/Builderscon 2018](https://scrapbox.io/nishio/Builderscon 2018) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.