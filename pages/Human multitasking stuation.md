---
title: "Human multitasking stuation"
---

Concurrency control story
When a long task collides with a short task, the longer task loses probabilistically, so
Only short tasks are done and long tasks are not executed for a long time.
The stuation that "I'm not going to be able to do it," happens,
That is to say,
In human task management, when I had small tasks and large tasks, I did only small tasks.
I thought it looked a lot like the problem of large tasks being left untouched.

The latter is not bumped and reverted.
The distortion of task selection timing to avoid large tasks rather than uniform randomness is the cause of the distortion.
So, I thought that if I could reverse the bias, I could solve the stavation problem.

    - Cases where [[multitasking]] is painful
    - The wording is ambiguous and contains multiple issues that need to be separated out.
        - I'm not going to talk about frequent interruptions (CS terminology) that require real-time reactions in this case.
- When there is a mix of large long-term tasks and small tasks, the problem is that the small tasks take up so much time that the large tasks do not get done.
    - The theory that there is a problem with the mechanism for determining which tasks to perform.
    - [Resource stuation - Wikipedia [https://ja.m.wikipedia.org/wiki/%E3%83%AA%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%B9%E3%82%BF%E3%83%99%E3%83%BC%E3%](https://ja.m.wikipedia.org/wiki/%E3%83%AA%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%B9%E3%82%BF%E3%83%99%E3%83%BC%E3%) 82%B7%E3%83%A7%E3%83%B3]
    - In the case of optimistic exclusion control, stavation is caused by the higher probability that a longer task will fail to verify and be rewound
    - But in the case of human multitasking, it's not a matter of rewinding due to failure to get a lock, there's another factor at play in the stuation.
- What are the factors?
    - It could be that the larger the task, the higher the cost of the context switch.
    - The cost of the context switch to start a task is so high that you need a yokel, and if you have a task lined up that doesn't require it, you'll do that one first.
    - The idea that a WBS can solve the problem of a large task does not work because it is based on a false premise. If the big task is a job, the work will be started even if it is just a slow day. Does the WBS solve the problem of having time and not being able to apply it when it is not work?
    - It is often said, "Break down large tasks." Unfortunately, the task of breakdown itself is a large context switch, and for the uninitiated, it is a large task for which it is difficult to estimate the time required. And for the uninitiated, it is a large task for which it is difficult to estimate the time required.
    - So at a minimum, it would be necessary to delimit the time for tasks.
    - The problem is that the task is too large, so splitting it up is the right direction.
    - We need to break up the task of dividing into more segments. Maybe we could start by writing down what comes to mind for five minutes.
    - I have a habit of drinking tea in the evening at work, so I could split up tasks over a cup of tea.
    - I think the work-as-life concept is a naming failure.
    - We can confine the stressful to the pomodoro, for example.

---
This page is auto-translated from [/nishio/人間マルチタスクのスタベーション](https://scrapbox.io/nishio/人間マルチタスクのスタベーション) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.