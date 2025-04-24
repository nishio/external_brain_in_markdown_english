---
title: "Reflection on the use of Whisper"
---

2024-03-22
With regard to transcription in [[Whisper]], the starting cost of doing a new application was high because we had done it in the past and forgot what we had done.
This is not a good idea, so make the look back first.

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- December 2022
    - Transcription of the Q&A portion of the KJ method study session review study session using Whisper. --- [[Weekly note 2022-12-18]].
        - Just before 2022-12-19, I'm installing Whisper from Git and splitting with ffmpeg --- [[Whisper]].
        - I was able to transcribe Japanese without any problems.
        - A warning that FP16 is not supported by the CPU was displayed.
            - --device mps option.
        - Transcription took a long time (over 11 hours).
- March 1, 2023
    - OpenAI releases ChatGPT API and Whisper API.
        - The open-sourced Whisper model will be available as an API in September 2022.
        - It uses the large-v2 model and is priced at $0.006 per minute.
        - Faster than other services due to optimized serving stacks.
        - Provides transcriptions endpoint (transcription of audio) and translations endpoint (translation into English).
- April 2023
    - [SYSTRAN/faster-whisper: Faster Whisper transcription with CTranslate2](https://github.com/SYSTRAN/faster-whisper)
- April 30, 2023
    - English conversation school recordings transcribed by Whisper and summarized by GPT-4. --- [[Diary 2023-04-30]] / [[English conversation → Whisper → GPT4]]
    - The entire 40-minute English conversation is too long to be given to GPT-4, so it must be divided into appropriate lengths.
    - Summaries of sufficient quality were obtained to recall the content of the English conversation.
- May 3, 2023 --- [[Diary 2023-05-03]].
    - Transcription of English conversation recording files using Whisper.
    - It took over three hours to transcribe the text.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Summarize the highest accuracy method for transcribing Japanese using Whisper as of 2024.
<img src='https://scrapbox.io/api/pages/nishio-en/pplx/icon' alt='pplx.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/nishio-en/Claude/icon' alt='Claude.icon' height="19.5"/>
The best way to transcribe Japanese audio with the highest accuracy using Whisper as of 2024 is summarized below.
1. use the API version of the whisper-1 model
    - Whisper has a free GitHub version and a paid API version (whisper-1)
    - API version is based on the large model of the GitHub version, but faster and more accurate
    - Pay-as-you-go system at approximately 0.86 yen per voice minute
2. prepare high quality audio data
    - Record clear, noise-free audio
    - Ensure a quiet environment of less than 55 dB for recording as a guide.
    - Audio formats supported: mp3, mp4, mpeg, mpga, m4a, wav, webm
3. split into audio files of 25 MB or less
    - Current Whisper can only handle audio files up to 25MB
    - Longer audio files should be split into files of 25 MB or less
    - Split files should be numbered in chronological order
- Visualize the process with the verbose=True option
    - Added verbose=True to transcribe options to show the process
    - Language detection status and hourly transcription results can be checked.
5. manually correct errors in proper nouns and terminology
    - Even Whisper has difficulty identifying homonyms, etc.
    - Errors that are obvious in context are sure to be corrected manually after transcription.

These are the key points for transcribing Japanese speech with high accuracy using Whisper.
We actually tried transcription with the API version of the whisper-1 model and found it to be almost perfectly accurate.
However, errors in proper nouns do occur, so a final human check is essential.
It is best to look at the balance between cost and labor and choose the best method for your application.


---
This page is auto-translated from [/nishio/Whisperの活用振り返り](https://scrapbox.io/nishio/Whisperの活用振り返り) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.