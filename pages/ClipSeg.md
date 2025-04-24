---
title: "ClipSeg"
---

[[Image Segmentation]] Using Text and Image Prompts
> Image segmentation is usually addressed by training a model for a fixed set of object classes. Incorporating additional classes or more complex queries later is expensive as it requires re-training the model on a dataset that encompasses these expressions. Here we propose a system that can generate image segmentations based on arbitrary prompts at test time. A prompt can be either a text or an image. This approach enables us to create a unified model (trained once) for three common segmentation tasks, which come with distinct challenges: referring expression segmentation, zero-shot segmentation and one-shot segmentation. We build upon the CLIP model as a backbone which we extend with a transformer-based decoder that enables dense prediction. After training on an extended version of the PhraseCut dataset, our system generates a binary segmentation map for an image based on a free-text prompt or on an additional image expressing the query. We analyze different variants of the latter image-based prompts in detail. This novel hybrid input allows for dynamic adaptation not only to the three segmentation tasks mentioned above, but to any binary segmentation task where a text or image query can be formulated. Finally, we find our system to adapt well to generalized queries involving affordances or properties.

[https://arxiv.org/abs/2112.10003](https://arxiv.org/abs/2112.10003)
[https://github.com/timojl/clipseg](https://github.com/timojl/clipseg)

[Image Segmentation According to Text with ClipSeg AI - TeDokology](https://www.12-technology.com/2022/10/clipseg-aiimage-segmentation.html)


---
This page is auto-translated from [/nishio/ClipSeg](https://scrapbox.io/nishio/ClipSeg) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.