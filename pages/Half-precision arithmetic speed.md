---
title: "Half-precision arithmetic speed"
---


Benchmarks for [A6000
- [GPU Server Expansion and A6000 Benchmarks | ALBERT Official Blog](https://blog.albert2005.co.jp/2021/09/27/a6000_8gpu/)
- [[BFLOAT16]] and others are looking into it.
- FP32
    - > Peak performance 38.7 TFlops
    - > M=640, N=480, K=320 on FP32 10TFlops, but the matrix size is also small, so it is still far from peak performance.
- FP16
    - > cudaTensorCoreGemm (FP16 Tensor)
    - > A6000：TFLOPS: 77.85
    - > M=4096, N=4096, K=4096 matrix product operations, so-called mixed precision. Matrices A and B are half (FP16), and the sum of products is received as a float (FP32) of matrix C. It is used not only for inference but also for learning as it is effective enough.
- It could be 2 to 7 times faster using semi-precision.

History
Very slow on 2016 GeForce GTX 1080 Ti.
- [NVIDIA GPU Specs for Machine Learning - Qiita](https://qiita.com/yukoba/items/10d0ba3fb1d19a6ab6a5)
    - FP32: 11.340 TFLOPS vs. FP16: 0.177 TFLOPS

2017
- [What will change with Huawei's new Kirin 970 processor?　The Mate 10 is also revealed: IFA 2017 - ITmedia Mobile](https://www.itmedia.co.jp/mobile/articles/1709/05/news097.html)
    - So this [[Kirin 970]] is [" 1.92TFLOPS of FP16 - 3x Faster Than Previous-Gen
        - [Huawei Reveals Kirin 970: Cat. LTE 18 With 1,200Mbps DL Speed and NPU Rated at 1.92TFLOPS of FP16 - 3x Faster Than Previous-Gen](https://wccftech.com/huawei-kirin-970-unannounced-specs-features-more/)

2019
- Huawei Sanctions
    - > In 19 years, the U.S. government imposed sanctions on Huawei for its involvement in activities that could pose a threat to national security.
        - [Huawei responds to U.S. government sanctions with new technology | Bloomberg | Toyo Keizai Online | Economic News for a Better Society](https://toyokeizai.net/articles/-/585108)
            - > Huawei's R&D expenditures have almost doubled over the past five years to $22.1 billion in 2021, more than any other company in the world except the US.
    - [See and understand "U.S.-China Tech Friction" Why Huawei Sanctions? : Nikkei](https://www.nikkei.com/article/DGXMZO63687730Q0A910C2000000/)
        - > August 2018 Law passed in the U.S. prohibiting U.S. government agencies from procuring products from Huawei and other companies.
        - > May 2019 U.S. Department of Commerce adds Huawei to export controls
        - The American reason is supposed to be "security concerns."
        - The Chinese, of course, protested, saying that they were using safety as an excuse.

- > Huawei announced its [[Ascend 910]] AI computing chip in August 2019, claiming it is twice as powerful as rival Nvidia's Tesla v100. Based on the company's announcement, it delivers 256 teraflops in half-precision floating-point arithmetic (FP16).
    - [https://www.axion.zone/hisilicon/amp/](https://www.axion.zone/hisilicon/amp/)
    - I see, the high need for half-precision arithmetic for edge computing is causing a technology competition between the U.S. and China.
    - Image recognition at the edge, it's going to affect the quality of operations with small unmanned aircraft that were mentioned in [[the War on Intelligence]], and China doesn't want to be dependent on American companies.


2020: NVIDIA RTX A6000 released

2022
- > Huawei, which has been suffering a significant decline in business due to sanctions from the US government that have prevented it from doing business with US companies including Google and Qualcomm, as well as from purchasing chips from TSMC, which uses semiconductor equipment made by US companies, will begin producing Kirin chips in Wuhan, China, as early as 2022, according to Taiwanese media DigiTimes. The Taiwanese media outlet DigiTimes reported that Huawei will start Kirin chip production in Wuhan, China, as early as 2022.
    - [Huawei plans to establish Kirin chip production facility in Wuhan, production to begin in 2022](https://iphone-mania.jp/news-378707/)

---
This page is auto-translated from [/nishio/半精度演算の速度](https://scrapbox.io/nishio/半精度演算の速度) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.