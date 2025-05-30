---
title: "Automatic sorter with adjustable number of storagesdraft"
---

from  [[Automatic sorter that can adjust the number of items stored by type]]


- [[Automatic sorter with adjustable number of storagesdraft]] TODO
- Make a two-tier one with a V-shaped clock and introduce it.
- How many steps are accessible?
![image](https://gyazo.com/49caddf7cd38d4cca69806cdf0954ed0/thumb/1000)



![image](https://gyazo.com/61a1a375a5ff026ebf34c27ccbd77a19/thumb/1000)

![image](https://gyazo.com/1d607e06cd963039e58d6d935b82de11/thumb/1000)

![image](https://gyazo.com/5c3fb275dc3f8f9968f42fcf027cdd9d/thumb/1000)



[https://scrapbox.io/files/61336659a08d2f001d611fa1.mp4](https://scrapbox.io/files/61336659a08d2f001d611fa1.mp4)


[https://scrapbox.io/files/613368354ee7a4001d9e3fde.mp4](https://scrapbox.io/files/613368354ee7a4001d9e3fde.mp4)


[https://scrapbox.io/files/613367e8574b8500231b91f0.mp4](https://scrapbox.io/files/613367e8574b8500231b91f0.mp4)




- [[Repeat customers and how they are communicated to]]

- [[Why is a 4T delay not acceptable and a 5T delay is OK?]]
Second half of Chapter II
- Item Elevator

9/5
[https://n5v.net/dropper-item-elevator/](https://n5v.net/dropper-item-elevator/)
- I've read in other people's articles that when hoppers and droppers are involved, "the math says they don't make it in time, but somehow they do," so I guess the difference is apparently due to the order of processing in a single tick.
- I tried to experiment with this, but I got different values depending on Kamikyo.
    - > Q1 : If the signal reaches the dropper at time T0, how many ticks later will the item be ejected?
    - > Q2: Suppose there is a hopper Y above hopper X that is not connected to anywhere. If an item reaches Y at time T0, how many ticks later will it reach X?
    - > Now the expectation is that both 1.
- Using programmatic clairvoyance to observe, the hopper should have an array of newly added items separate from the inventory. Because if you add them directly, the hopper that can suck them up will process them as "there's an item, let's suck it up", resulting in a lot of movement in one tick.
- In addition, there is a variable that holds the "number of ticks since the item was added. When sending out an item, it is checked to see if this value is 4 or more to prevent the situation where "every tick of an item placed in the hopper is sent out".
- This counter is reset when an item is placed in the hopper by the dropper. And since the "process of resetting the counter by placing an item in the hopper" is done before the "send out if the counter is 4 or more" decision is made within one tick, items that entered more than 4 ticks ago are not sent out.
- If this interpretation is correct, items would not be sent out of the hopper where items are inserted from the dropper at intervals shorter than 4 ticks. We could experiment by using two droppers and alternating shots.
- I was able to reproduce it with one dropper because the condition was "less than 4 ticks" instead of "less than 4 ticks."
        - [[If you put things in the hopper with a dropper at 4 tick intervals, it won't feed.]]
    - ![image](https://gyazo.com/9d1eea625387681a947104436db1f9ca/thumb/1000)

- [[Both the dropper and hopper run on one tick.]]

I was going to do a 6-drawer chest of survival with this.
- It's quite large at 6 deep, so the only good place to put it is where I have the previous version.
- You have to adjust for misalignment on top of the clock, not at the base of it, but it's a tall job and it's built tight, so there's not a lot of room for maneuvering.
- I didn't think there was any point in going through it because it changes case by case, but if you put the elevator lift in a chest and suck it from there, the shape can be fixed.
    - I thought, but the timing of the item elevator to the chest is not synchronized with the timing of the item elevator to the chest...
    - However, it would be better to not synchronize this for greater flexibility in handling.
    - If you suck what you put in the chest with the hopper, put it in the dropper, and then inject it again, the phases will be aligned.
- Item elevator, periodic 4, just the way it feels.
    - An example of clocking with a comparator is given below, but the result is that if more than one enters the hopper, it breaks, or it's too subtle.
    - If you judge at the bottom, you'd have an excess of items at the top. How about a wired OR with powder drawn from the top and bottom?
- How does the length of the hopper change the proper adjustment?
    - Check with Creative


Chapter Three.

Other
- The button sends out a pulse 15 ticks long.
- Repeaters can lock outputs when signaled from the side with a repeater or comparator.

---
Automatic sorter with adjustable number of storagesdraft
- Verified environment BE1.17.11, Realm, changed to Survival Creative
- I once made an "automatic sorter that can adjust the number of items stored per item" that worked roughly by imitation, but I broke it.
- I was going to check the article again, but I couldn't see it anymore.
- [https://b.hatena.ne.jp/entry/s/mitancraft.com/アイテムごとに収納数を調整できる柔軟だけど堅/2022/](https://b.hatena.ne.jp/entry/s/mitancraft.com/アイテムごとに収納数を調整できる柔軟だけど堅/2022/)
- We have no choice but to reinvent the wheel.



memo
- Should I write an explanation of the case for simply stopping first?
- 27 stacks, 64 pieces per stack, 0.8 seconds per piece, 1382.4 seconds, roughly 23 minutes, or 2 Mike's lunches



Now, use this signal to turn the upper and lower hoppers on and off alternately. The hoppers are difficult to see on/off visually, so first check their behavior with a torch.


[https://scrapbox.io/files/6130f74cdae669001dc03c63.mp4](https://scrapbox.io/files/6130f74cdae669001dc03c63.mp4)


[https://scrapbox.io/files/6131068bf7dd2500207f5f26.mp4](https://scrapbox.io/files/6131068bf7dd2500207f5f26.mp4)

Q: What happens if you put things in the top chest in this condition?
- Answer: into the lower hopper
- reason
    - T1: Top hopper turns on and sucks one
    - T2: Lower hopper turns on and sucks contents of upper hopper
- This doesn't allow things to fit in the chest next to it, what should I do?
    - Do you want to do it this way?
        - T1: Dropper puts one in the upper hopper
        - T2: If the top hopper is on and you can put it in the chest, put it in.
        - T3: Lower hopper turns on and sucks out what is left in the upper hopper

Droppers, why?
- They need to be one at a time.
- The hopper above should not suck items directly from the chest.
    - In a situation where an item always sucks, it will also suck on the last tick that is on, and even if it is something that goes into the chest, it will be sucked into the hopper below.
        - With additions
- What happens if the upper hopper is simply on for both T1 and T2?
    - The top hopper sucks one up and the bottom sucks one up before the next step sends it out.
- Instead of having the top hopper suck stuff up, why not have another hopper feed it?
    - If that hopper is not signal controlled, stuff gets fed in while the top hopper is off.
- The dropper's "if there are two ticks of time on, only one will be sent out" behavior is just fine, given the following
    - In addition, send it out at the second tick, not at the time of rising
- PS
    - The hopper only moves every 8 ticks, which prevents "sucking on the last tick".

Oh, and the hopper only works every 8 ticks to begin with.
- Not with a fast clock signal.

Need to create an 8-tick clock signal.
- If you have a comparator, you can put one of the things in the hopper across from you and check for its presence in the comparator.
- If no, overlap repeater max delay 4 ticks?
    - [[Logic Analyzer @ Micra]] made and confirmed, V clock delay should be 3

[https://scrapbox.io/files/613257c5c69368001dd7a578.mp4](https://scrapbox.io/files/613257c5c69368001dd7a578.mp4)
Hmmm, it's not working right. It's all down the line.
Assumed operation
- 4 on 4 off or longer signal comes (video is 5)
- Dropper and lower hopper turn on at T0 (hopper on means operation stopped)
- T2? items go from the dropper to the hopper above.
- The bottom hopper is stopped and the top hopper is moving, so stuff goes into the chest on the right (expected behavior).
    - Actual behavior: in the chest below.

continue

If the hopper sucks up every 8 ticks, you could let the upper hopper suck up the hopper.
- Hmmm, with 5 on, it's split 50/50, and with 4 on, it goes to all the underlings.

I wanted to create a pulse with a length of 6, so I created [[Pulse generator with adjustable length]].

If the width of the pulse on is 4, it goes into all the lower chests, if it is 5, it goes halfway, 6, it goes into the upper only.
- I don't know why that happens, but I've found that it's important to signal on6off6.
- the reason this happens is probably that the hopper doesn't move the moment it is turned on, but rather it moves two ticks later.
Oh, no, it's not... even with a length of 6, it's split 50/50. I guess this is to check the behavior of the hopper first...

- [[Verify behavior of hoppers side by side]]
So let me get this straight.
- Minimum of 5 ticks required to feed from hopper
- Sucking also occurs at the 5th tick (probably before feeding).
    - →That's why, in a case with a pulse of length 5, when the bottom hopper turned on at the 6th tick, the top hopper was still sucking up what it had sucked up just before, and it sucked it up, resulting in the "split in half" behavior.
- Need to restrict flow with a dropper.

It's done, it's done, the "if you can put it in the chest, put it in, if you can't, pass it to the hopper below" unit worked properly. Now we have an automatic sorter that can control the stockpile limit.
- [https://scrapbox.io/files/61331f53461a9b00230368ec.mp4](https://scrapbox.io/files/61331f53461a9b00230368ec.mp4)
- I feel like I've already done it...

Is there any way to make a "pulse of length 5" without a comparator?
- I'm using a loop with a delay of 10 and a pulse length of 5 with [[Pulse generator with adjustable length]].
- [https://scrapbox.io/files/613309c07a57ee001d58a994.mp4](https://scrapbox.io/files/613309c07a57ee001d58a994.mp4)
- If we could do it without using the comparator, since that is the only part of the whole machine that uses a comparator, we could say, "This is an automatic sorter that doesn't need a comparator..."
- Oh, I'll just use a V-shaped clock with maximum delay, solved!


---
This page is auto-translated from [/nishio/収納数を調整できる自動仕分け機draft](https://scrapbox.io/nishio/収納数を調整できる自動仕分け機draft) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.