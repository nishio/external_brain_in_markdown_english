---
title: "Labor Time Efficiency"
---

> The relationship between "work style" and "wealth". As a famous thought experiment, the catch of a fisherman who works for a week is in the order of C > A > B, where A = 8 hours every day, B = target number of hours every day, and C = work a lot on days when the catch is good and rest the rest of the time. The worst is to "set a quota and work hard," while the next best is to "work a fixed number of hours. The way of working in a corporate organization is said to be unproductive to begin with.
- [https://twitter.com/shu_yamaguchi/status/1136756720980520960](https://twitter.com/shu_yamaguchi/status/1136756720980520960)

Suppose the yield per fixed time is 1-7.
- (A) If you work 25 credit hours daily
    - Harvest totals 700
    - Total hours worked: 175
    - Harvest efficiency per unit time is 4.0
- (b) If you work with a daily quota of 100 harvests
    - Working hours for each day (rounded up to the nearest unit)
        - `array([100.,  50.,  34.,  25.,  20.,  17.,  15.])`
    - Total hours worked: 261
    - Harvest totals 700
        - No different from (A)
    - Harvest efficiency per unit time is 2.68
        - (A) > (B)
- (c) Work a lot when you can catch it.
    - Assume in (B) that the same hours are worked on the best efficiency day because the maximum of 100 credit hours are worked
    - Working hours for each day (rounded up to the nearest unit)
        - `array([0.,  0.,  0.,  0.,  0.,  0.,  100.])`
    - Total working hours: 100
    - Harvest totals 700
        - (A)(B) No different from (A)(B)
    - Harvest efficiency per unit time is 7.0
        - (C) > (A) > (B)
- (C2) Work a lot when you can catch it, Part 2
    - Assuming the opinion, "But you can't work only at your best efficiency!"
    - Work 20 credit hours daily and extend to 30 hours if you're in good shape.
        - The "25 units of work" is the image of a 10-hour workday.
        - The "work 20 credits and if you are in good shape, work 30 credits" is like "work 8 hours and if you are in good shape, work 4 hours of overtime".
        - Good shape" is defined as "yield per unit time greater than 4." It can be verified over the course of 20 working credits.
    - 20 credit hour harvest
        - `array([ 20,  40,  60,  80, 100, 120, 140])`
        - Total 560
    - Harvesting Overtime
        - `array([ 0,  0,  0,  0, 50, 60, 70])`
        - Total 180
    - Total harvest 740
    - Total working hours: 170
    - Harvest efficiency is 4.35
        - (C) > (C2) > (A) > (B)
- (C3) Work a lot when you can catch it, Part 3
    - Try to have more variation in working hours.
        - Image: "Try working two hours in the morning, and if you don't feel well, take a half day off.
        - Work 5 credit hours every day, and if you're in good shape, work 25 hours.
    - 5 credit hour harvest
        - `array([ 5, 10, 15, 20, 25, 30, 35])`
        - Total 140
    - Harvesting an additional 20 hours on a good day
        - `array([  0,   0,   0,   0, 100, 120, 140])`
        - Total 360
    - Total harvest 500
    - Total working hours 95
    - Harvest efficiency 5.26
        - (C) > (C3) > (C2) > (A) > (B)

summary
- Situations where the yield per unit time fluctuates
- Yield per unit work hour depends on how you work.
    - (C) > (C3) > (C2) > (A) > (B)
    - (b) "Work until a certain yield is reached" is the worst.
        - Because you'll be working intensively when the yield per unit of time is low.
    - (a) "working a certain number of hours" is the next worst
    - (c) "Concentrate work when yield per unit time is high" is the most efficient.
        - However, many may question whether this is realistically possible.
    - (C2) "Working overtime when I'm doing well and going home on time on a bad day" is better than (A)
    - (C3) "Take a half afternoon off when you are not feeling well and work overtime when you are feeling well" is the next best thing to (C)

- Inverse pattern of [dollar cost averaging

---
This page is auto-translated from [/nishio/労働時間効率](https://scrapbox.io/nishio/労働時間効率) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.