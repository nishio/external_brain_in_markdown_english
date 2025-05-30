---
title: "About CookiePomodoro's design policy"
---

- Design Policy for [CookiePomodoro
    - Don't make the achievements you can make without thinking about them.
        - For example, "I did 10 pomodoros in a day" induces the behavior of turning the timer just to acquire pomodoros without doing the job properly.
            - The amount of pomodoro to do should not be dictated by this game, but by the real work you want to do.
        - Do not use consecutive days as an achievement.
            - Because just one day of failure is a hurdle to achieving it.
        - No situation should be created in which it is better not to initiate the pomodoro, especially
        - Achievements gained over time without doing anything are probably not good enough.
        - I'm wondering if we should introduce a stochastic event.
            - I guess it is [[Intermittent reinforcement]] if you get something with a probability after completing the pomodoro, but on the other hand it spoils the fun as an optimization puzzle.
            - Random changes in the production of certain facilities, etc.?
- Even if you make hidden achievements, they'll be written up on the strategy site anyway.
- I don't want to play a game where I have to follow a strategy written on a strategy site without thinking for myself.
    - The best solution depends on the individual's situation.
    - Frequent parameter changes make the information on the strategy site outdated.
- Don't include a feature that gives you the advantage of doing something while the Pomodoro timer is running.
    - We should focus on the task.


- developmental nerf
    - Burning coal to increase cookie production is a powerful play.
    - Weakening it is easy, just put a usage limit on it.
    - But daring to use it and introducing a new "Air Pollution".
    - The rise has reduced mana production.
    - I also placed some permanent results.
    - In other words, "I'll come up with an idea or look at a strategy site and do it once, and once I get the achievement, I'll want to try other options and reset.

- Something should happen once every 1-2 pomodoros.
- 40 times shall be considered as one round.

- [https://twitter.com/nishio/status/1364986632051458052](https://twitter.com/nishio/status/1364986632051458052) with a score-like Total Amount of Resources
    - The play style of collecting mana is too strong, let's do a developmental nerf. Proposal "Mana will be condensed and cut in half if you collect more than 100 (record the number of times condensed and remove the achievement)"
    - "It's not fun that magic consumes 100 mana so it's better not to use it, lower the cost more" and "Mining enhancement magic because it's not fun that mining and mana don't go well together."
    - However, I'm wondering what magic changes what with the pickaxe, since the design raises mining production with pickaxe and lowers mining costs with electric power.

- [tw](https://twitter.com/nishio/status/1368568916679610372)
    - Backups are now made at the same time as saves, keyed to date and time. Deploying it now along with the soft reset feature.
    - A few thoughts on the soft reset: If you have 8 pomodoros per day, you will reach 40 pomodoros in 5 days. The total amount of resources at that point is recorded in terms of high score. The soft reset is done in order to "get the achievements that you didn't get" or "maybe you can update your high score if you do it again".
    - I'm thinking maybe a soft reset on a 1-2 week cycle. Not now, but if, for example, magic-based achievements and scores are introduced, it will motivate people to try different playstyles, since coal-burning play is a disadvantage.

- [tw](https://twitter.com/nishio/status/1365347014830006278)
    - We implemented recipes, achievements, and mining bonuses for up to 4 steel pickaxes. What's the point of having a desk just for making steel pickaxes, we made it possible for one converter to have multiple recipes.
    - I also made it so that burning all the coal would cause air pollution and lower mana production.

- [tw](https://twitter.com/nishio/status/1368790930715643905)
    - It was surprisingly easy to get notifications via Notification API (I'm using it on my phone, so I'm going to test it to see if it works when the screen is locked).
    - Turn on notifications with "Grant Notification Permission" at the end of the page.
    - I tried it on my iPhone and got an error, so only PC for now.

---
This page is auto-translated from [/nishio/CookiePomodoroの設計方針について](https://scrapbox.io/nishio/CookiePomodoroの設計方針について) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.