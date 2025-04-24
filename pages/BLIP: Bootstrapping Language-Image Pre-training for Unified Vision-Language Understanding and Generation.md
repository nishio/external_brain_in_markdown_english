---
title: "BLIP: Bootstrapping Language-Image Pre-training for Unified Vision-Language Understanding and Generation"
---

> Vision-Language Pre-training ([[VLP]]) has advanced the performance for many vision-language tasks. However, most existing pre-trained models only excel in either understanding-based tasks or generation-based tasks. Furthermore, performance improvement has been largely achieved by scaling up the dataset with noisy image-text pairs collected from the web, which is a suboptimal source of supervision. In this paper, we propose BLIP, a new VLP framework which transfers flexibly to both vision-language understanding and generation tasks. BLIP effectively utilizes the noisy web data by bootstrapping the captions, where a captioner generates synthetic captions and a filter removes the noisy ones. We achieve state-of-the-art results on a wide range of vision-language tasks, such as image-text retrieval (+2.7% in average recall@1), image captioning (+2.8% in CIDEr), and VQA (+1.6% in VQA score). BLIP also demonstrates strong generalization ability when directly transferred to video-language tasks in a zero-shot manner. Code, models, and datasets are released at this https URL.
[https://arxiv.org/abs/2201.12086](https://arxiv.org/abs/2201.12086)

roughly speaking
- The approach of "collecting pairs of images on the Internet and their descriptions and using them for training data" is noisy because the descriptions are often not appropriate.
- The proposed method improves the training data by first creating a description from images, comparing it with the description on the Web, and selecting the better one.
    - ![image](https://gyazo.com/e177a0b5e05690359ace08067bd2b328/thumb/1000)

- Q: How do I create a description?
- Q: How do you determine if it is a "better description"?

github: [https://github.com/salesforce/BLIP](https://github.com/salesforce/BLIP)

[[BLIP]]
---
This page is auto-translated from [/nishio/BLIP: Bootstrapping Language-Image Pre-training for Unified Vision-Language Understanding and Generation](https://scrapbox.io/nishio/BLIP: Bootstrapping Language-Image Pre-training for Unified Vision-Language Understanding and Generation) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.