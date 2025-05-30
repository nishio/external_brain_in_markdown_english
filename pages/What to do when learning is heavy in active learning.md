---
title: "What to do when learning is heavy in active learning"
---

- I thought that the correct and LESS confident one was not selected in [[interactive active learning]].

In a case where the initial value of downsampling is set to 100 (1 per case) in order to work with large files, when the number of targets is drastically reduced by [[✅Allow specifying the logs to be trained for motion extraction]], there are not enough candidates to be properly selected. You can't choose the right one.

Even in such cases, automatic adjustment should work after the second time, but as for after a certain amount of data has been gathered, "relearning with the latest data" becomes heavy, and the impact of this down-sampling becomes smaller.

If you find that the reason for poor selection of training targets is due to [Down sampling is too hard.
Also, I changed the "adjust sampling rate so that the waiting time is 1 second" to "5 seconds" this time and confirmed that it is adjusted properly without changing the initial value.
But this is not an essential solution, since it will eventually occur again as the time required for the learning part gradually increases.

If learning is fast enough, learning each time prevents answering similar questions over and over again.
On the other hand, if the learning becomes too heavy, I don't want to learn every time. What to do. For example, split the original conversation log and pick only one question from each group?

If the priority is not to keep humans waiting, is it better to train asynchronously in the background as soon as new training data comes in? Replace the model when the training is completed and create a new model from the next question creation. Since it is likely that new training data has already arrived at the time of training completion, further new training will be started.

I guess we copy the training data, start a child process that reads the copy and outputs the model, checks periodically and if the model file is output (or if the process terminates), loads it.
I want it to be done quietly while waiting for user input. Since it blocks while waiting for user input, should we make a mechanism to load the model in a thread?

It's a pretty big deal, and at this point we're not in a position where we need that yet, so I'll just make a note of it.

---
This page is auto-translated from [/nishio/能動学習で学習が重くなったらやること](https://scrapbox.io/nishio/能動学習で学習が重くなったらやること) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.