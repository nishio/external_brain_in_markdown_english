---
title: "Amazon Transcribe"
---

way
- pretreatment
    - The audio file coming down from Zoom is aac, which is not acceptable.
        - `$ ffmpeg -i foo.aac foo.mp3`
- Upload audio file to [S3 Bucket
    - Note that it must be in the same region.

- Speaker Identification is turned on, the maximum number of people can be specified (I set it to 6).
- I set the transcription to show Alternative

![image](https://gyazo.com/39b089816a10746a0c979d1334fa2389/thumb/1000)
- An hour of audio takes about 40 minutes to complete.
    - 2019/11/28 16:07:33 / 2019/11/28 16:42:13

I have no idea what you are talking about.
> Speaker 2: Enjoy!
>  Speaker 2: Where
>  Speaker 1: I don't think it's fair to say that you don't disturb the people you eat with.
>  Speaker 1: Lots of
>  Speaker 1: This is the only way to reduce the number of places like this.
>  Speaker 0: No.
>  Speaker 0: I've never seen a company, even a large one, that would reduce the number of nights on the side, which in essence makes it a public competitor.
>  Speaker 1: Yes
>  Speaker 1: Ne
>  Speaker 1: I think you should start with the video information, sprinkle something on it.

The raw data looks like this
:

```
 {"jobName": "Test", "accountId": "736390490238", "results":{"transcripts":[{"transcripts": "You should aim for a recognition that you can wear as a minute, but if you try to eat something like that, you will see that the rainbow is the same or at that level. I don't think Comiket is good enough. Well, in that sense, the subculture market in Japan is not good enough... I don't know who it is, but this song is also in Japan, and I've been wondering what kind of methods they've been using, and I've been getting information that they're not young enough for classification problems, and I'm sure that here in Paris, they're talking about this.]
"speaker_labels":{"speakers":6,"segments":[{"start_time":"1.16","speaker_label":"spk_2","end_time":"2.15","items":[{"start_time":"1.16","speaker_label":"spk_2","end_time":"1.47"},{"start_time":"1.47","speaker_label":"spk_2","end_time":"1.7"},{"start_time":"1.71","speaker_label":"spk_2","end_time":"1.88"},{"start_time":"1.88","speaker_label":"spk_2","end_time":"2.15"}]},{"start_time":"3.47","speaker_label":"spk_2","end_time":"5.82","items":[{"start_time":"3.47","speaker_label":"spk_2","end_time":"3.89"},{"start_time":"3.89","speaker_label":"spk_2","end_time":"3.97"},{"start_time":"3.97","speaker_label":"spk_2","end_time":"4.24"},{"start_time":"4.24","speaker_label":"spk_2","end_time":"4.42"},{"start_time":"4.42","speaker_label":"spk_2","end_time":"4.5"},{"start_time":"4.5","speaker_label":"spk_2","end_time":"4.73"},{"start_time":"4.94","speaker_label":"spk_2",
```


:

```
For example, yes, actually, LENCE] It's like a thousand yen is not there. But the sixty-eight dimensions lie on top of each other, and it really depends on the parameters, but for example, LENCE] Well, well, I can't calculate the similarity of these vectors, because of the edge, and what this means is that I can't calculate the similarity of this vector, so there's no reason to go against it or anything, you know, there's something special at the beginning of a sentence, and this guy that comes up at times like this, he's this guy. LENCE] If you say that this guy has a feature for this whole document, well, you know, there's not even a person from the whole text, which explains the different identification study, right? But the other pages are also available in a vector of several hundred and sixty-eight dimensions, which means that you can do a video about the web page, so let's go there.
```

I know slightly what this is talking about.
Mysterious [[LENCE]]" token

---
This page is auto-translated from [/nishio/Amazon Transcribe](https://scrapbox.io/nishio/Amazon Transcribe) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.