---
title: "Kozaneba Development Diary 2021-09-08"
---

from [[2021-09-07]]
![image](https://gyazo.com/9424e7b64aacc23712232345e0d3efdc/thumb/1000)

---
Write down what you do.
- Python script to generate JSON for import
    - Add Create Group
    - Change the sample source code visualization to one that uses groups.
    - How many sides will there be?
- Support for item deletion
- physical operation
    - Operation is prohibited during execution.
    - Pin, unpin
    - Introduce group contraction?

---
Today we're going to improve the source code visualization functionality - first, we'll be able to create groups from Python scripts.
- Pomodoro start
- I can now create groups.

Next, start Pomodoro, which represents folder hierarchy as a group.
- end
- The Python library was badly designed and found to be difficult to use.
- I had separated the creation of instances and adding to Ba, but the state of not creating and adding is unnatural in the first place

Change design, start Pomodoro
- I wrote tests in pytest, watched them in pytest-watch, and refactored them.
- I just took a sip of Coke and did 10 squats.

The next step is to create a visualization code with this new design.
- start
- Without the arrow, it worked, but the arrow is mysteriously undefined.
- Ten incline push ups and a sip of coke.

- Arrows to the contents of the closed group
    - Do you want it to be an arrow to the group or do you want to turn it off?
    - It would be bad if it disappeared.

Let's fix the bugs... start the Pomodoro.
- Uh, NaN.
- Should it be reproduced with smaller data?

- No type error via JSON, so when reading Python-generated material, it could be an incorrect value.
    - If undefined is included, an error will occur at the time of saving to Firestore.
    - Should there be runtime checks on import?

Start Pomodoro to make small samples and fix bugs.
- Fixed a bug.
- ![image](https://gyazo.com/6fec08b1824fccef497b685daf1a6bad/thumb/1000)

![image](https://gyazo.com/25b415aebf4f5fe65f61d5975b634348/thumb/1000)

Mm, it will.
- ![image](https://gyazo.com/1b4e1e9bb496257d9a66d672ba85dc99/thumb/1000)

I opened a relatively better one.
- ![image](https://gyazo.com/084abc398e5d0466382139fe7802d4e9/thumb/1000)
- Hmmm, it's obvious that the selection is reset by an event and that the selection information is obtained from the drawing part, so this reference is necessary...

The lines have been thinned and transparency has been added so that strongly related objects appear darker.
- ![image](https://gyazo.com/cf0f4c0380621dd35072d4141448859d/thumb/1000)

Relationship between Canvas and Menu, what?
- Oh, the utility function is still in here.
- ![image](https://gyazo.com/1be558bd6bd328c3bd90b992bd1efb58/thumb/1000)
- It's important to be able to see the thick and thin, because a thick relationship is like, "Well, that's just the way it is." When a thin relationship is in a strange place, it leads to the discovery of something that shouldn't be there.

![image](https://gyazo.com/998e38303d3f7a098dbe74037886c737/thumb/1000)

Chiru-chiru...wow!
- ![image](https://gyazo.com/53dc2ebe85bead86d7ea5b9b87cb4346/thumb/1000)
- Physics, when there is a closed group, the closed group should move, not the contents...

1. fix pomodoro physics...
- When a group is closed, the group is the target of the move.
- Pinning function.
- Pomodoro done

Ah, well, the language specification doesn't distinguish whether it's referenced from outside the directory or only from inside.

Even if we were to use style B because type A is complicated, the center circle would be "something that interacts with a great many things".
- It may be necessary to highlight the arrows that go in and out of the selected object, or conversely, to reduce the presence of the arrows that go in and out of the selected object and do not participate in the physics calculations
- ![image](https://gyazo.com/3e11f55a16fe6fef6459f17e0588466a/thumb/1000)

Turn off these four hubby-ish things and it will clear up.
- ![image](https://gyazo.com/ee8200d6aeac22c63f569f36f708d232/thumb/1000)
- The rest looks like this
    - ![image](https://gyazo.com/9c415198f7b77e5e769d865c4cbdafa8/thumb/1000)

When I first visualized it, I thought, "I don't understand anything!" But when I opened the file and checked it, I found that I had written it wrong after all.
- When I wanted to use the logic that A was using and B wanted to use it, I bundled it into a function or module and called it from B, but that wasn't enough.
- ![image](https://gyazo.com/ec15c6104492a7d97d2c00dcd409a3b7/thumb/1000)
- The correct answer was to bundle them together as in #3.

For example, why does the Physics directory of physics operations interact with other things?
- So three things: "cloud saving must be stopped during physics," "pinning when position is determined by dragging," and "there's the ability to unpin from the selection menu."
- ![image](https://gyazo.com/9424e7b64aacc23712232345e0d3efdc/thumb/1000)


If you want to tinker with it, click here. It will not be saved, so you can tinker around as you like. However, your MacBook will be hot.
- [https://kozaneba.netlify.app/#view=ycoPTxkIAT2PfKhVHGFi](https://kozaneba.netlify.app/#view=ycoPTxkIAT2PfKhVHGFi)
Here is the code to be analyzed, and the script used for the analysis is in the python directory
- [https://github.com/nishio/kozaneba/tree/f4c3233e3dedc424f16bd51dce5b721845926a5d](https://github.com/nishio/kozaneba/tree/f4c3233e3dedc424f16bd51dce5b721845926a5d)

- [[Kozaneba Development Diary 2021-09-09]]

---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-09-08](https://scrapbox.io/nishio/Kozaneba開発日記2021-09-08) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.