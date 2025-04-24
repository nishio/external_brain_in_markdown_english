---
title: "InstaChord Diary"
---

# 2023-01-09
from [/villagepump/2023/01/09](https://scrapbox.io/villagepump/2023/01/09)
<img src='https://scrapbox.io/api/pages/villagepump/基素/icon' alt='/villagepump/基素.icon' height="19.5"/>
- I'm trying to understand scales and modifiers (?) by tapping on the keyboard. I'm trying to understand add9, dim, sus4, etc.)
- InstaChord's ~ seems to be the keyboard equivalent of raising or lowering the second note by a semitone (in the case of a triad).
    - +1<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
        - Another one further up the major in sus4<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- I call it "modifier" on its own, but I don't know the correct term> modifier (? add9, dim, sus4, etc.)]
- InstaChord kitteh!
    - 👏<img src='https://scrapbox.io/api/pages/villagepump/issac/icon' alt='/villagepump/issac.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/villagepump/基素/icon' alt='/villagepump/基素.icon' height="19.5"/>
- Button on the string part, pressing it does not produce sound, only when you play it.
    - There are several modes for this, so you can try different ones.<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
        - Strum
        - Hit
            - Surprisingly, it is also possible to play in this mode like a Taisho harp.
        - Push

> [@nishio](https://twitter.com/nishio/status/1612331518726406144?s=20&t=aopuGaMlnD4IJdkVNCUVUw): InstaChord has arrived!
> (Otsuka Ai "Cherry" chord + whistle)
[https://youtube.com/shorts/KjNkvf89C-A?feature=share](https://youtube.com/shorts/KjNkvf89C-A?feature=share)
> The "storytelling" part of playing is whistling, so it's "playing and blowing," but you wouldn't get the message if I told you that.

<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- If you don't keep the button on the cord pressed, the sound decays quickly.
    - Is EZ mode the only exception?<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
    - If you're playing a chord for a long time, thinking the one that extends the note is normal, you'll get confused because it doesn't extend when you swap in.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - What I have read and understood from the description
        - The design behavior is that a note-off is sent when the button on the cord is released.
        - So "press and hold for as long as you want it to ring" is the expected behavior of the user.
        - Funny how I "press 3, then release and press swap".
        - If you hold down 3 and press swap, the sound will extend properly.
- If you press and play 1 and then press 2 without releasing 1, the notes will not mix.
    - So, except for the same finger pattern like 3 and 6, you can prepare the next finger right after the note-on of the previous note.
    - This is also true for the modifier keys, so once you have a note on, you can immediately release it and hold down the modifier after the next one.
- Mystic will use 7b all the time (exaggeration).
- [[3~7]] Too difficult problem
    - I thought about taking a video of the swallowtail butterfly for social media, but it's nighttime and I don't want to whistle.
    - 3 is pressed with the middle finger and ~7 with the ring finger.<img src='https://scrapbox.io/api/pages/villagepump/issac/icon' alt='/villagepump/issac.icon' height="19.5"/>
        - Great.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
        - I'm ready to play!
    - 3 is pressed with ring finger and ~7 with pinky<img src='https://scrapbox.io/api/pages/villagepump/基素/icon' alt='/villagepump/基素.icon' height="19.5"/>
        - When I did that and tried to put my pinky to sleep, my ring finger would also go to sleep and press 6!<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- The one that converts to ICN and mysteriously has a lot of modulation, but I suspect it's not necessary, or the output of [[Chord AI]], or the feeling that I wonder what knowledge I need to understand and play a score that only has chords written in it.
    - [[toICN]]は出現頻度見てキーを推定してるだけですね<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
        - [https://github.com/inajob/toICN/issues/21#issuecomment-912926012](https://github.com/inajob/toICN/issues/21#issuecomment-912926012)
        - Automatic determination of modulation has not yet been implemented, but it seems to be possible only to check the frequency of each part in a similar way, and if it is too different from the others, determine that it is modulation.
        - You're estimating by frequency~.<img src='https://scrapbox.io/api/pages/villagepump/基素/icon' alt='/villagepump/基素.icon' height="19.5"/>
        - I feel that if the head of the track can be inferred from lyrics, etc., then a little more accuracy can be achieved.<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
            - If we analyze the existing score, there is no good way to know the A-melody and B-melody separations...
- The actual machine can now show what sound each button is making by setting the Display Note Number.
    - ![image](https://gyazo.com/883d3d5f260378a24e3ed0b61680dcaa/thumb/1000)
        - The chords, there are only five, and not even a subset of the string notes.
            - Chords (left) are guitar, strings (right) are piano? Matching instruments[[voicing]] になっていますね<img src='https://scrapbox.io/api/pages/villagepump/shoya140/icon' alt='/villagepump/shoya140.icon' height="19.5"/>
        - I can't believe I can display something like this!<img src='https://scrapbox.io/api/pages/villagepump/基素/icon' alt='/villagepump/基素.icon' height="19.5"/>
            - Setup. This makes [[arpeggio]] practice easier!
- Bass note(?) mode, the sound is played when the chord button is pressed, so it is necessarily necessary to press the modifier key and then the key of the scale
    - Should I usually get used to that order as well?
    - The only pattern that changes the bass note seems to be ♭.<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
    - No, I mean these modes.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
        - ![image](https://gyazo.com/60ae02f799edf72652494ecd2ea94af7/thumb/1000)
        - It's a recently added feature (I don't know).<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
        - Chords sound when the left button is pressed, no need to operate the right string button.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
            - Easy on the hands in studying chord progressions because it can be done without manipulation to play.
            - and press Am and then swap, Am will sound, so swap must be first.
        - Okay, then I agree that I'd like to get used to that.<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
- Today's Reminders
    - Why not just use 9 instead of having to painstakingly press 7b?
        - 9~?

from [/villagepump/2023/01/09](https://scrapbox.io/villagepump/2023/01/09)
<img src='https://scrapbox.io/api/pages/villagepump/shoya140/icon' alt='/villagepump/shoya140.icon' height="19.5"/>
- [[InstaChord]] arrived!
    - That's no different from me living in Japan!<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - Somehow it arrived 10 days earlier than the estimated delivery date.<img src='https://scrapbox.io/api/pages/villagepump/shoya140/icon' alt='/villagepump/shoya140.icon' height="19.5"/>
    - ![image](https://gyazo.com/a8f2c6b15fbbf3e2f5a8ee3a4b325895/thumb/1000)
    - I like the fact that I can update firmware with [[web browser]].
    - [InstaChord Updates - InstaChord/InstaChord](https://instachord.com/instruction/howto_update/)
    - No need to develop/install a dedicated [native application
    - [[WebUSB API]], perhaps.
    - I thought I could already use it practically.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>

# 2023-01-10

from [/villagepump/2023/01/10](https://scrapbox.io/villagepump/2023/01/10)
<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
- I want to shoot [[swallowtail butterfly (esp. the citrus swallowtail butterfly, Papilio xuthus)]] during my lunch break.
- done
> [@nishio](https://twitter.com/nishio/status/1612669445201358848?s=20&t=aopuGaMlnD4IJdkVNCUVUw): 2nd day of InstaChord! It's Porno Graffiti "Swallowtail Butterfly" chord + whistle.
> I thought it would be difficult, but the progression just before the rustication is very mushy, and the rustication itself is only difficult in the swap of 3, surprisingly. It is interesting to come to understand such things.
[https://youtu.be/Yhm_WPABM98](https://youtu.be/Yhm_WPABM98)
> The monitor looks a lot different compared to yesterday's post. This time he's playing in his chair with the camera in front of him.

> [@nishio](https://twitter.com/nishio/status/1612675309920477184?s=20&t=F7hFOkOWnwx8vFwAJ35q6g): here's a version of "Cherry" with a better view of the screen
[https://youtube.com/shorts/3dYQCnwihfY](https://youtube.com/shorts/3dYQCnwihfY)
> [@nishio](https://twitter.com/nishio/status/1612676252045053952?s=20&t=F7hFOkOWnwx8vFwAJ35q6g): the score is this much information
> ![image](https://pbs.twimg.com/media/FmFggHDakAAn3eZ.jpg)



from [/villagepump/2023/01/10](https://scrapbox.io/villagepump/2023/01/10)
<img src='https://scrapbox.io/api/pages/villagepump/shoya140/icon' alt='/villagepump/shoya140.icon' height="19.5"/>
- InstaChord and curiosity-driven music theory, you've finally reached [[the Pentateuch]]!
    - I don't know from here either.
    - It's funny how everyone is going on and on about how they don't know what's going on.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>

<img src='https://scrapbox.io/api/pages/villagepump/基素/icon' alt='/villagepump/基素.icon' height="19.5"/>
- It's interesting how the same progression can produce completely different songs.

# 2023-01-11

> [@nishio](https://twitter.com/nishio/status/1613047416147832832?s=20&t=aopuGaMlnD4IJdkVNCUVUw): 3rd day of InstaChord. Today is "Thesis of the Cruel Angel". From one phrase before the chorus.
> The rust section is easy except for the end, which is a repeated 6251 circular chord. This time, the 3~ connecting from the previous phrase was a personal challenge.
[https://youtube.com/shorts/tdzhXkdHdJk](https://youtube.com/shorts/tdzhXkdHdJk)
> [@nishio](https://twitter.com/nishio/status/1613049682795859971?s=20&t=kQFMGpF5Pfo2fz3tckQXAA): One more time, One more chance / Masayoshi Yamazaki
[https://youtube.com/shorts/Lkpli-D2XDo](https://youtube.com/shorts/Lkpli-D2XDo)
> I've chosen all three songs so far as easy ones that I can play without pushing too many buttons, but I simply can't make a video that I can post because I fail at the harder ones. This is the one I managed to play.
> [@nishio](https://twitter.com/nishio/status/1613052119971692544?s=20&t=kQFMGpF5Pfo2fz3tckQXAA): here's the score for today
> ![image](https://pbs.twimg.com/media/FmK2WYeakAALmet.jpg)

# 2023-01-12
> [@nishio](https://twitter.com/nishio/status/1613389754313379840?s=20&t=e4-qmbywy8mSyK_fNpFtXQ): InstaChord Day 4 Diary Sheena Ringo "Queen of Kabukicho"
> I used 7th locks for the first time because most of the chords are 7ths.


from [/villagepump/five-degree-zone](https://scrapbox.io/villagepump/five-degree-zone).
    - [[(in gagaku) scale similar to Mixolydian mode on E]] 以外にジャンプするのは、やめた方が良いみたいな感じなのかなと思っている<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
- Are you sure?<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - Moving next door in a five-degree circle means +/- 5 in InstaChord, right?
    - Aren't there a few songs that do that kind of modulation?
- [https://soundquest.jp/quest/chord/chord-mv4/modulation-in-pops-1/](https://soundquest.jp/quest/chord/chord-mv4/modulation-in-pops-1/)が参考になりそう<img src='https://scrapbox.io/api/pages/villagepump/teyoda7/icon' alt='/villagepump/teyoda7.icon' height="19.5"/>
    - > The [[generic tone]] and the [[subordinate tone]] are on the left and right of the principal tone on the fifth degree circle....
    - > This modulation is standard in classical music, but it is not used that frequently in pop music because of the theoretical technique required.
    - I see<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
        - You haven't seen any classical chord progressions yet, so you're thinking, "I haven't seen many people move next to each other in the fifth-degree circle.

# 2023-01-13

from [/villagepump/3~ likes](https://scrapbox.io/villagepump/3~ likes)
- <img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>2023-01-07
    - I found that I like 3~.
- <img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/> 2023-01-13
    - What he had initially said, "I like something 3~" for no apparent reason, turned out to be "I like [[Harmonic Miner Scale]]".

    - [[History of tonal temperament]]
    - [[Comparison of temperaments]]

from [/villagepump/kinship tone](https://scrapbox.io/villagepump/kinship tone).
- [[generic tone]] dominant key
- Tone with the dominant as the dominant
- C→G
- So you're keeping the majors and minors, but adding one more sharp.<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
    - What does it mean to increase the sharpening? is easy to understand on the key signature, but what kind of operation is it? It seems a little more intuitive to me.<img src='https://scrapbox.io/api/pages/villagepump/inajob/icon' alt='/villagepump/inajob.icon' height="19.5"/>
    - Isn't that "five degrees up"?<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
        - ![image](https://gyazo.com/2bc8b781daa78c74ef5c0c450b43137b/thumb/1000)
        - I wonder which is the more essential expression, "rise five degrees" or "increase sharpness."
            - Is "processing to increase frequency by 1.5 times" the essence?
                - [[History of tonal temperament]]

# 2023-01-14
- from [/villagepump/2023/01/14](https://scrapbox.io/villagepump/2023/01/14)
- <img src='https://scrapbox.io/api/pages/villagepump/shoya140/icon' alt='/villagepump/shoya140.icon' height="19.5"/>
        - I now understand more about [[changing key (during piece)]] with [[diatonic chord]] and [[the Pentateuch]] in [[minor scale]].
    - [/villagepump/I have a better understanding of diatonic chords in the minor scale and transposition in the fifth degree range](https://scrapbox.io/villagepump/I have a better understanding of diatonic chords in the minor scale and transposition in the fifth degree range).

- [/villagepump/InstaChord+GarageBand](https://scrapbox.io/villagepump/InstaChord+GarageBand)

# 2023-01-15
- [/villagepump/Backspace.fm New Year's Eve Ultra Year-End Party SUPER Live 2022](https://scrapbox.io/villagepump/Backspace.fm New Year's Eve Ultra Year-End Party SUPER Live 2022).
- I learned the concept of upstroke.

# 2023-01-16
> [@nishio](https://twitter.com/nishio/status/1614854920892710912): InstaChord Diary
> I have no experience with guitar or anything like that, so I didn't know this, but it seems that when you raise your right hand, you also pluck the strings. I heard it's called upstroke.
- [/villagepump/strokepattern](https://scrapbox.io/villagepump/strokepattern).
    - [[clang, clang, clang]]
    - I could do "[[janga-janga]]" in practice, but not with the camera rolling, so I made it one step easier.
- I watched [/villagepump/everyone-understands-chord-progression-course](https://scrapbox.io/villagepump/everyone-understands-chord-progression-course) to 10 in the bath.

# 2023-01-23
[/villagepump/2023/01/23](https://scrapbox.io/villagepump/2023/01/23)
- I'm not sure about the concepts of [/villagepump/InstaChord and curiosity-driven music theory](https://scrapbox.io/villagepump/InstaChord and curiosity-driven music theory) and [/villagepump/secondary-dominant](https://scrapbox.io/villagepump/secondary-dominant) (and throw a fluffer).
- After all, useful abstract concepts cannot be mastered in the abstract.
    - I found a video that gives specific examples of all kinds of modulations, and it occurred to me when I was writing the chord progression of "specific modulations" that
    - [/villagepump/all transposition patterns](https://scrapbox.io/villagepump/all transposition patterns).
- Perhaps the concept of secondary dominance, which I just learned about, is not yet well scaffolded enough to understand
- I just finished watching the first video of the entire transposition pattern.

# 2023-01-25
[/villagepump/2023/01/25 snow](https://scrapbox.io/villagepump/2023/01/25 snow)
- I just realized that 13 in [[Chord progression course that anyone can understand]] is talking about [[secondary dominant]].
- Watch the explanation of the secondary dominant and then watch the transposition video!

[/villagepump/all transposition patterns](https://scrapbox.io/villagepump/all transposition patterns).
- `Key:F# 2~ 3~ 1# Key:B 4 5`
    - Hmmm, the first half isn't easy to pull off at all, instacode-wise, is it?<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - G# and A# both in the major...Eb.
    - (Commentator Eb's story)
    - I feel that I have made progress in my music theory knowledge, which allowed me to get a little ahead of the commentator's explanations in terms of ease of playing with insta-chords!<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

[/villagepump/2023/01/25 snow](https://scrapbox.io/villagepump/2023/01/25 snow)
- Better understanding of modulation.
    - The smoothness of the modulation seems to be more important than whether it's in a close key or not, like the dominant motion.

# 2023-01-26
- [/villagepump/new door opened](https://scrapbox.io/villagepump/new door opened) added

---
This page is auto-translated from [/nishio/InstaChord日記](https://scrapbox.io/nishio/InstaChord日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.