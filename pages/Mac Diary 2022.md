---
title: "Mac Diary 2022"
---

2022-11-15
Need to build a new machine environment.
- Migration with the migration tool is no longer possible due to the company's management tool.
- So it needs to be built from scratch.

I was working on it in a very small amount of time and I couldn't really tell what was going on.
- You need to write down your thoughts properly as you go along.

Migration with migration tools is no longer possible.
- I ran the migration tool to the last machine, went to bed, and the next morning the new machine had the same environment as before, and I was able to continue working right away.
- Migration tool conflicts with some management tool and is no longer available
- Then, I couldn't "migrate while sleeping and start a new machine the next day," so I decided to migrate when the work was finished and put it off for a long time.
    - I lost the translation as I kept going back and forth because what I tried didn't work.
- I was recommended to migrate via OneDrive, but it failed with a mysterious permission error.
    - This is not a mystery, but a theory (current hypothesis) that there are files with special permissions in .ssh, .docker, etc.

- From finding out how else to move files
    - [Setting up file sharing on your Mac - Apple Support (Japan)](https://support.apple.com/ja-jp/guide/mac-help/mh17131/mac)
    - This is how to set up Samba on the old machine and copy from the new machine
    - Once the progress bar for the crazy long estimate shows up, but it looks like it could be transitioned at a realistic rate.
        - Experiment: Try to copy 36000 files 8GB
            - Estimated end time is 6 hours later (initially indicated 2 hours, increased to 7 hours as I write).
            - I was wondering if it would be over while I was sleeping, or if the time required would keep increasing and I wouldn't be finished when I woke up in the morning, but to my surprise, it was over in an hour!
            - Pattern of progress bar overreporting!

- To begin with, when selecting and copying target files from the Finder, are folders and files beginning with a dot copied?
    - A: Briefly, it is copied but not selected
        - Hidden by default.
            - Cmd+Shift+. Switch display with
        - So, if you "select and copy the entire contents of a folder," anything that starts with a dot is not selected and therefore not copied.
        - A/.gitignore, etc. under folder A are copied when folder A is copied.

Terminal settings are, of course, erased on the new machine.
- I looked into the possibility of bringing the settings from the old machine, but I don't know how to do that without a migration tool, so I'll just give up and re-configure.

It's been so long I've completely forgotten what I need.
- Four years ago and three years ago I was recording!
        - [[Mac Diary 2018]]
        - [[Mac Diary 2019]]

I copied some projects experimentally.
- I was able to copy without any problems.
- Need to test if development can continue without problems

2023-11-15
- I'm going to sleep tonight with a copy of everything but Dropbox all together.
    - It would take hours to get there.
    - At any rate, according to my current understanding, there should be no error (.ssh and .docker are not selected).
2023-11-16
- ![image](https://gyazo.com/263a8a284a35a1e37fc1e9979b95215b/thumb/1000)
- It didn't work.

[http://scorpionfish.blog.shinobi.jp/ubuntu/sambaでmacのファイルが"%20The](http://scorpionfish.blog.shinobi.jp/ubuntu/sambaでmacのファイルが"%20The) %E3%80%81 operation cannot be completed because you do not have access to some items%E3%80%82 "
> Check the permissions on the Mac terminal. There are files that are readable and writable, but have "@" at the end of the permissions.
> EA (Extended Attributes), which is additional information. . due to Mac OS X version upgrade (currently 10.6.3).

>  This additional information can be erased by
>  $ xattr -d com.apple.FinderInfo "14 Amazing Grace.m4a"

>  Solution for now.
>  ① Delete EA with xattr -d.　　(It's too much trouble)
>  2) Transfer by USB or external HDD.　　　(Too much trouble, no point in making a server...)
>  ③ Create a file server using a method other than Samba.　　(Use netatalk. EA is supported for 2.1 and above. But it will be hard)
>  > 4) Wait for Samba to support it.　　(Fingers crossed)
>
>  I decided to go for it and install netatalk.

I've checked to see what kind of things have the extended attribute, but it's on a lot of things, like .DS_Store, screenshots, etc.
- It doesn't seem to me that if you're lucky, you'll always fail.

next action
- Copy it on the command line to identify what is causing the problem.


---
2022-11-20
- I was so tired that I kept getting up and getting the wrong password and the old machine locked up.
    - While consulting with the IT department about unlocking the machine, the new machine was set up at the same time.
    - →11/22 Found to be in a state where remote unlocking is not possible due to an error on our part during the transition.
- Chrome
    - Installed.
- Mattermost
    - I didn't write down the server information, Chrome history remembered, I wrote it down.
- Zoom
    - I could go into the meeting.
    - I'm still waiting to see if I can SSO with my company account.

Problem to be solved
- Unable to input Japanese with thumb shift
- Chrome goes back with a gesture, I want to stop it.
    - ![image](https://gyazo.com/4e7ded581d7f4a04cb4661a099af1eab/thumb/1000)
- Need certificate to access company groupware

2022-11-22
- Slack
        - [[Slack single channel guest too difficult.]]

Fastest key repeat
before / after
![image](https://gyazo.com/285c40ef9203418a136d6a60aa7bc83c/thumb/1000)![image](https://gyazo.com/fe8e597233bc61dfe89d1c66e2a0f4f8/thumb/1000)

- [[Cmd+Shift+4 to enter clipboard]]

Enable Japanese input by thumb shift
    - [[Diary of Thumb Shift on Mac 2020-01]]
- 2021 [/shiology/06161 I have completed the setup to realize thumb shift "shio shift" using only Karabiner-Elements and will publish the simple setup procedure](https://scrapbox.io/shiology/06161 I have completed the setup to realize thumb shift "shio shift" using only Karabiner-Elements and will publish the simple setup procedure).
- [/shio/ 4 settings and 1 training for drafting on the new Mac](https://scrapbox.io/shio/ 4 settings and 1 training for drafting on the new Mac).
- I see. So Lacaille doesn't have to use it anymore.

![image](https://gyazo.com/334b81482dbad0960bd003cb9eb9685e/thumb/1000)
right-handed genealogist
Here's the thing (this is written in shio-shift)
I have no problem with shio-shift for writing Japanese, but I am a programmer. I type a lot of symbols that people who mainly write Japanese don't use.
- I tried to respect the shio-shift (and its base orz array) while also remapping the symbols to where they are easier to use...
- In the end, I came to the conclusion that "the state of mind when writing Japanese and programming are two different things, so the sequences should also be two different things.
    - I've always been a fan of writing comments and commitments in English while programming, so there's no advantage to using an array for Japanese input while programming.

I have an idea of the code that should be implemented, but I'm not sure if I've implemented it in the past...
There it is.
- from [/nishio/thumb-shift-diary](https://scrapbox.io/nishio/thumb-shift-diary).
    - August 2018
            - [[Diary of Thumb Shift on Mac 201808]]
        - The structure of overlapping Lacaille and Karabiner-elements is engineeringly weird.
        - Karabiner-elements alone can achieve thumb shift.
        - It's hard to mess with Karabiner's configuration files directly.
        - I made a script to generate a configuration file.
            - [[generate_karabiner_conf]]

As you can see from the source, when outputting JSON, the following conditions are added: "Japanese mode must be on" and "not a login dialog".

[[VSCode]]

git
- ![image](https://gyazo.com/2dc9c04f94b61e4ecfa492d17c9241c4/thumb/1000)
    - Wow, now Mac says something like this.
- ![image](https://gyazo.com/3f7a90a5d658218a4fc293c895092164/thumb/1000)
    - Seriously?
        - →It took me about an hour to finish.

Install Dropbox -> default to online and only offline mode for what you need.

I just realized that I can't type Japanese, so I'm using my phone, which is causing me to lose perspective.
On my PC, I'm getting lost, with tabs being opened in Chrome and Safari because of a weird Handoff setting.
I finally understand the reason for the confusion.
- [[I want to open Handoff in Chrome, not Safari.]]
- [[I want to fix the order of virtual desktops on MacBooks in any order.]]

The repository also contained pre-generated files, but I don't know how to use these...
How to use Complex Modifications in Karabiner-Elements
- > Save your own rules with a .json extension and place them in the folder below.
- >  /Users/username/.config/karabiner/assets/complex_modifications
    - [How to create your own rules in Karabiner-Elements - Webrandum](https://webrandum.net/karabiner-elements-original-rules/)
- Official Document: [Use more complex rules | Karabiner-Elements](https://karabiner-elements.pqrs.org/docs/manual/configuration/configure-complex-modifications/)


:

```
!@#$%^&*()_+
1234567890-=
qwertyuiop[]
asdfghjkl;'\
zxcvbnm,./
```

Hmmm, the right hand displacement is gone, but the symbols aren't correct.
Is this something wrong with the original data itself? Or is karabiner configured incorrectly?

[How to fix a Mac that recognizes it as a us keyboard even though it is a jis keyboard | unlogue-](https://www.unlogue.com/mac-jis-us/)
- > Check the "Preferences" > "Keyboard" > "Input Source" screen.
    - ![image](https://gyazo.com/83b99273d054648dd0e7d72df8405ca6/thumb/1000)
    - Certainly a different display than the actual keyboard.
- > If "Apple Internal Keyboard/Trackpad" is checked, uncheck it.
    - ![image](https://gyazo.com/ac2dc0bdf2555c2aea7c3990ee720496/thumb/1000)
        - It's off.
    - ![image](https://gyazo.com/3cb53c08bb29ec422ee5a3605dfbedc2/thumb/1000)
        - Fixed!

        - No, not at all.
            - If I turn off Modify Event, the thumb shift conversion in Japanese is also turned off, which makes no sense.

- [[Circle symbol with backslash]]
- [[Mac setup notes]]

2022-11-25
- [Problem with Karabiner-Elements recognizing JIS keyboard as US keyboard - Qiita](https://qiita.com/kenmaz/items/0ff152af776a3e6e5f6e)
    - > Open Karabiner-Elements Preferences and select Virtual Keyboard
- ![image](https://gyazo.com/f2a6e4299059e7709575a38e77b14f85/thumb/1000)
- ![image](https://gyazo.com/7fd391530d59d62650ad45370c411250/thumb/1000)
- right-handed genealogist
- @:*`;+
- OK!!


Delete the Ctrl arrow shortcut in Mission Control

qkatakosayyrachikutsuho ".
Ushikitekese h wa tokiin."
Nehisufu he nmeso,. ___.
[[Thumb Shift Diary on Mac 2020-01#5e00e8f5aff09e00000e2fb5]]
> I actually typed it in and noticed that the double brackets and asterisks were not showing, and the full-width slash and middle black were wrong.
> ![image](https://gyazo.com/afe02f6951348d9c024cad6f94fb1574/thumb/1000)
Hmmm, where was the last time I changed a layer of this?
- [[generate_karabiner_conf]]
    - [https://github.com/nishio/generate_karabiner_conf/blob/master/nishioshift/SPECIAL.txt](https://github.com/nishio/generate_karabiner_conf/blob/master/nishioshift/SPECIAL.txt)
    - Now I've decided to change it.
    - I passed on colons, underscores, circle symbols, etc., because I wrote them at this point but didn't use them at all after that and didn't remember them.
    - Added exclamations and braces with no middle black and center shift in the lower right corner
    - [https://github.com/nishio/generate_karabiner_conf/commit/f1a52b08bd5760a0424e61c070620b4a08c3dd3d](https://github.com/nishio/generate_karabiner_conf/commit/f1a52b08bd5760a0424e61c070620b4a08c3dd3d)


- [[Make the default editor vi -> VSCode]]

2022-12-04
    - [[Installing ipython]]
- Put in Adobe XD
    - I wondered how the license management or whatever was going on, but the installer opened a browser tab, authenticated me, and asked me to log out one of the two machines since I was already logged in on two different machines, easy.

2022-12-19
- [The Missing Package Manager for macOS (or Linux) — Homebrew](https://brew.sh/)
- `$ brew install ffmpeg`
- [[Whisper]]

2023-01-11
    - [[Create a development environment for Kozaneba]]

2023-01-16 [[VSCode]] forgot to set auto-format on save
- 2023-01-26 Put in [[Prettier]] and set up default formatter
    - [vscode settings - VS-Code Prettier Format On Save doesn't work - Stack Overflow](https://stackoverflow.com/questions/59433286/vs-code-prettier-format-on-save-doesnt-work)

2023-01-17 Old machine salvage
> 2022/12/9
>  Machine B locked up during transition from machine A to machine B to machine C.
>  Machine B cannot be remotely unlocked due to improper migration of Machine A to Machine B
>
>  If so, it's currently unclear if it's possible to unlock machine B or if it's just a matter of restoring it to the state it was shipped in.
>  I guess "Next action: salvage data from machine A" would be a good place to start.
>  I'm slammed until next Friday, so I'll check after that.

I tried to start machine A, but when I mistakenly started machine B, I was able to log in (eek).
- Lock released over time?
- Did a reboot from complete battery depletion reset some state?

Mysterious hang-up when using Finger ID to re-login from screen lock after time elapsed.
- The login process does not proceed.
- Cancellations can be made.
> When I canceled and tried to log in with my password, I got "Account is locked".
> I don't know if the condition for unlocking is the passage of time or a restart from battery depletion, but I would like to try the latter. And it's possible that even if you return from a screen lock, it might work if you put in the password.

next action
- Leave Machine B until the battery is fully discharged.
    - It's hard to conserve battery because it goes to sleep right at the login screen...
    - For now, leave it until tomorrow.
        - I'll check tomorrow and if the battery doesn't seem too low, I'll figure out another way.
- Reboot and log in with your password
    - Note that the password is different from Machine A due to the change in password policy.
- Connect from machine C with Samba
    - Copy the project folder from the one with the newest update date
- In parallel, try the following
    - Can the lock time for non-operation be released or made longer?
    - Can we turn off Finger ID?

2023/1/23
- I had 12% battery left, but I could log in.
    - Unlocking over time?
        - ![image](https://gyazo.com/da550b7f8a63b15e7fa2f0ec880fb682/thumb/1000)
        - This display must be strange.
            - I left it off for 6 days since the 17th and now it's showing like it was on until 3am this morning.
            - Was there something wrong with the indication that the battery had 12% left, once it was empty, and then the indication went even more wrong?
            - No, but it was a speedy startup, not like from a full discharge...
                - I should have activated the AC and checked it before hooking it up.

- Samba connection is not available
    - Why? I was able to do it last time.

- ![image](https://gyazo.com/4f5e471ed3e0553e151c0df2631e218b/thumb/1000)
    - I was able to get my Mac to not use Finger ID to unlock.
    - When I try to turn off the password autofill as well, it asks for the password.
    - If you put your password here, it will be rejected.
        - I can log in with that password, why?
        - Something funny going on around authentication...

- Unable to connect to Samba
    - password is rejected when I enter it / I can log in with that password, why?".
    - Grant read access to the guest and try to connect with the guest
        - ![image](https://gyazo.com/7c49a002ea7836f3e67ee2bc346241ea/thumb/1000)
        - hmm
- Login to your MS account and pour into OneDrive Challenge
    - You don't give an end time estimate or anything.
    - ![image](https://gyazo.com/947971c55646b59549f6515980e76df6/thumb/1000)
    - This one was in node_modules, so I decided to delete the whole thing.

I guess I'll leave it alone for now for a while and see how the synchronization went.



2023-01-26
- Gyazo GIF
- ![image](https://gyazo.com/85e7ec00fe78b34d3fc2eefc5893e678/thumb/1000)

Something was wrong with the local development environment settings, and something that didn't warn me locally and went through was failing in the production build.
- That kind of thing is a pain in the ass, so I'd like to make the local warnings stricter.
- Did you forget to include eslint in your development environment?
- VSCode extension, ESLint and Prettier ESLint, which is it?
- I put the former in and now it warns me properly.

2023-02-01
[[Docker for Mac]]
- ![image](https://gyazo.com/a400c59b94f172c3a78a7c4a5ae0cb3a/thumb/1000)
- ![image](https://gyazo.com/2cbb5f581b6849a58f0b38587cefedba/thumb/1000)
    - I downloaded it from the top page, but upon closer inspection it said Intel Chip.

---
This page is auto-translated from [/nishio/Mac日記2022](https://scrapbox.io/nishio/Mac日記2022) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.