---
title: "Polis discussion with Dr. Okumura"
---

> [nishio](https://x.com/nishio/status/1954213468170760499) It's a common reaction that people leave Polis halfway through because they have too many questions, but Polis is designed with the expectation that people will leave halfway through, so not all questions However, Polis is designed in such a way that it is not necessary to answer all the questions, nor do we think it is a problem that some people do not answer all the questions. In fact, one could argue that it is better for people to leave the site.
>  >nishio: The algorithm is designed to display the most informative first, with the expectation that some people will leave during the process. I think the data will reveal if it can be summarized in that one question. You can also post that opinion and see how others respond.

> [nishio](https://x.com/nishio/status/1954214377290170715) The idea is that people who leave are leaving because they are not interested in seeing other people's opinions on this topic, so we should not force them to participate in the discussion.

> [h_okumura](https://x.com/h_okumura/status/1954343124886835587) So the order of presentation is not random? If so, those who answer until later are a particular group, and the result is likely to be biased. Also, was the withdrawal supposed to be distinguished from no answer and subtracted from N?

> [nishio](https://x.com/nishio/status/1954347063669571728) It is not random random, but it is not fixed either. Each person is in a different order. So I don't think there is any bias towards questions posted later in the order.

> [nishio](https://x.com/nishio/status/1954347370264842668) Disengagement and neutral responses are distinguished, with disengagement shown in white in the detailed report and neutral responses in gray. Withdrawals are excluded from the denominator of the percentage display.
>  During the matrix calculation, missing values are filled with the average of the responses of other respondents.

> [h_okumura](https://x.com/h_okumura/status/1954350362825224652) Thank you. So it's not random, so there will be bias, but it's not completely fixed, so there is less bias. It's subtle to fill in with the average of the other responses (which would be closer to the center).

> [nishio](https://x.com/nishio/status/1954426786638668242) To be more precise, I think I was correcting each person's vector around the square root of the number of responses N for each person.

> [h_okumura](https://x.com/h_okumura/status/1954428325889233111) I see, I guess I can find out by reading [https://compdemocracy.org/algorithms/](https://compdemocracy.org/algorithms/) (quite tedious)

> [nishio](https://x.com/nishio/status/1954487732325253219) The code was written in Clojure and was quite cumbersome, here's what I had AI explain
>   [[Polis question presentation order mechanism]]
>  I didn't understand how to calculate Extremity from this explanation alone.
>
>  Here's one in the form of a paper
>
>  [https://www.e-revistes.uji.es/index.php/recerca/article/view/5516](https://www.e-revistes.uji.es/index.php/recerca/article/view/5516)
>
>  This one doesn't go into the details of the algorithm.



[h_okumura](https://x.com/h_okumura/status/1954343124886835587)
The presentation order isn’t random. In that case, the people who keep answering all the way to the later items would be a particular subset, so the results could end up biased. Also, was it the case that you distinguish dropouts from non-responses and subtract dropouts from N?

[nishio](https://x.com/nishio/status/1954347063669571728)
It’s not purely random, but it’s not fixed either. Each person sees a different order. So I don’t think the items that appear later suffer from position-based bias.
Dropouts are distinguished from neutral responses. In the detailed report, dropouts are shown in white and neutral responses in gray. Dropouts are excluded from the denominator when percentages are displayed. In the matrix computations, missing values are imputed with the average of other respondents’ responses.

[h_okumura](https://x.com/h_okumura/status/1954350362825224652)
Thanks. So there is some bias because it isn’t random, but since it isn’t completely fixed the bias is small—got it? Imputing with the mean of other responses is a bit questionable (it pulls things toward the center).

[nishio](https://x.com/nishio/status/1954426786638668242)
More precisely, I recall that each person’s vector is adjusted by the square root of their number of answers N.

[h_okumura](https://x.com/h_okumura/status/1954428325889233111)
I see. Maybe it’s explained if I read [https://compdemocracy.org/algorithms/](https://compdemocracy.org/algorithms/) (though that looks like a slog).

[nishio](https://x.com/nishio/status/1954487732325253219)
The code is written in Clojure, which made it pretty painful. Here’s an explanation I asked an AI to write:
[https://gist.github.com/nishio/3278475028844af3a896d86dddcdd9a1](https://gist.github.com/nishio/3278475028844af3a896d86dddcdd9a1)
Even with that, I still couldn’t quite figure out how “Extremity” is calculated.

Here’s a paper-style write-up:
[https://www.e-revistes.uji.es/index.php/recerca/article/view/5516](https://www.e-revistes.uji.es/index.php/recerca/article/view/5516)
This one doesn’t go into the algorithmic details.
---
This page is auto-translated from [/nishio/奥村先生とのPolisの議論](https://scrapbox.io/nishio/奥村先生とのPolisの議論) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.