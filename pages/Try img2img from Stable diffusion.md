---
title: "Try img2img from Stable diffusion"
---

2022-08-31
![image](https://gyazo.com/4ea391f01508c5f5f73d164b1aec92de/thumb/1000)

2022-08-28
![image](https://gyazo.com/e76266a8138d0717a6039e53bb5c1738/thumb/1000)

[[Stable diffusion]]
Try the image prompt
The original data is a 256x256 image with just the text written on it, and "black cats" is specified as the text prompt
![image](https://gyazo.com/38038b8c1cf81a82e6d5799b305b7aa5/thumb/1000)![image](https://gyazo.com/70699291bccc316efe9b33529d72e282/thumb/1000)![image](https://gyazo.com/b64c8cc7d5410e0c73344a72eae763fe/thumb/1000)

![image](https://gyazo.com/b8d0ced46a33b6f4c42ecb660fc8d9c9/thumb/1000)![image](https://gyazo.com/90ca2bb5feb9909b5ce976fecb87c0b7/thumb/1000)![image](https://gyazo.com/b324a565a259ae5a796de08444ef00bf/thumb/1000)

strength=0.75(default)
![image](https://gyazo.com/87fdcce45fe08018d45ea09755fc949c/thumb/1000)

0.5
![image](https://gyazo.com/7da632e106e9b2508cba0f52dce15ea9/thumb/1000)

0.2
![image](https://gyazo.com/731852e4a071c032f6a6ee2f72126918/thumb/1000)
Oh, this is the strength of the text prompt side, I misunderstood.

0.99
![image](https://gyazo.com/8a29cc92f223e4373aa397228d88d1d8/thumb/1000)

0.9
![image](https://gyazo.com/2c38deb2dc020a0860fb95dba1ae8657/thumb/1000)
0.8
![image](https://gyazo.com/8b3c0df94756153475ea5e21644528f8/thumb/1000)
0.85
![image](https://gyazo.com/8facf5b03d4c9ab94b1a193f98632720/thumb/1000)

0.88
![image](https://gyazo.com/8010383d425ac86f77f80a22f82345f4/thumb/1000)

0.87
![image](https://gyazo.com/c0d3c55919457ec1763d6063108fc7ee/thumb/1000)

`$ time python scripts/img2img.py --prompt "black cats" --init-img c.png --ckpt sd-v1-4.ckpt --strength 0.87 --n_sample=1`
real    0m32.746s
user    0m24.091s
sys     0m5.784s

`$ for i in {1..10} ; do python scripts/img2img.py --prompt "black cats" --init-img c.png --ckpt sd-v1-4.ckpt --strength 0.87 --n_sample=1 --seed ${i}; done`
![image](https://gyazo.com/7e6d2117f929c3f3ebb1c105dbce7368/thumb/1000)![image](https://gyazo.com/543f27f9f64be666654ffc7e0dc390a3/thumb/1000)![image](https://gyazo.com/31b25ad3c438b042235a2bdbbb290c18/thumb/1000)![image](https://gyazo.com/4eb64bff3d01fae23032c833ae9c25d4/thumb/1000)![image](https://gyazo.com/08f51c060a5d2158e8b509d18754ae52/thumb/1000)![image](https://gyazo.com/b8d0ced46a33b6f4c42ecb660fc8d9c9/thumb/1000)![image](https://gyazo.com/b19f3ec3a56595b63bb118bb5630aedd/thumb/1000)![image](https://gyazo.com/858ea84f31c71b1c99f47b62bea29b80/thumb/1000)![image](https://gyazo.com/e065601364106e97cd2bf5a316980ad5/thumb/1000)![image](https://gyazo.com/7ab14e44bbfe22ac0fb3b57f662c667e/thumb/1000)

If I had to choose one, this would be the one, but it's not quite what I was expecting...
![image](https://gyazo.com/b8d0ced46a33b6f4c42ecb660fc8d9c9/thumb/1000)


![image](https://gyazo.com/1a5c1d12a40c8ef02fd510e84ff7f59b/thumb/1000)![image](https://gyazo.com/efdad40c234e4fd1cfff58715bd38340/thumb/1000)![image](https://gyazo.com/9692a1530b613cbba1ac9cc1f7cd351a/thumb/1000)![image](https://gyazo.com/319180b0133231f2398f425c9fb5c830/thumb/1000)![image](https://gyazo.com/69152a50eafccf0be94e7a31ec8d75d2/thumb/1000)![image](https://gyazo.com/ebb3c36750116a099be2d6a0b8d8986c/thumb/1000)![image](https://gyazo.com/d795f120f923e7ec0edd5b3509b5438d/thumb/1000)![image](https://gyazo.com/29dfb96faf0c0c9744f6faeb807aa605/thumb/1000)![image](https://gyazo.com/c71db17383817400d316e9767e5a486f/thumb/1000)![image](https://gyazo.com/90ca2bb5feb9909b5ce976fecb87c0b7/thumb/1000)

![image](https://gyazo.com/6c7c9b857318ca92e21020ec2f0cbce3/thumb/1000)![image](https://gyazo.com/eefd3b1ccb6f85c01415b868f2e2f350/thumb/1000)![image](https://gyazo.com/da528f76c046b2d975f2358dc0bf0472/thumb/1000)![image](https://gyazo.com/327943f3b0e04e5f74bfb6cf53f30521/thumb/1000)![image](https://gyazo.com/00673b4e31fd4f0ce0d4442b6ca08a91/thumb/1000)![image](https://gyazo.com/2e4bf7c7cc6b612966010c82824f0ea4/thumb/1000)![image](https://gyazo.com/a9ac05fffdcfbf35068b5117dd9e4b54/thumb/1000)![image](https://gyazo.com/6f25834004a470d6a36fad55af641f71/thumb/1000)![image](https://gyazo.com/b324a565a259ae5a796de08444ef00bf/thumb/1000)![image](https://gyazo.com/e1045ed33644d6ca69ae938ff7959b29/thumb/1000)

Draw rough instructions.
![image](https://gyazo.com/d345d8eada864d092230d368653c8173/thumb/1000)

![image](https://gyazo.com/b2a7b480446cac3690b8ea633d6cd2e3/thumb/1000)![image](https://gyazo.com/ecae1dd28ac3d368c2b6c29bb58ad088/thumb/1000)![image](https://gyazo.com/df1c0a8b16d5265aeea51b8184816fcd/thumb/1000)![image](https://gyazo.com/2de437320d63d049d5b8f7398a747ef0/thumb/1000)![image](https://gyazo.com/e92221a96b0b022cc0419e8ce2c673e4/thumb/1000)
Is it getting worse?
![image](https://gyazo.com/4783bd815bd13acf18805497bcfc6f89/thumb/1000)![image](https://gyazo.com/187ee6e29ecd1874bc8baa1328c29329/thumb/1000)![image](https://gyazo.com/65768bb6b90e97a1f1b73708c14e8016/thumb/1000)
![image](https://gyazo.com/ae2ad732a7f09a13892e1dfa9909052c/thumb/1000)![image](https://gyazo.com/67e3977d63aa77afacf1e1d4a818e017/thumb/1000)![image](https://gyazo.com/709aa960d8fd9aec94033f68c694f87e/thumb/1000)
Hmmm, this probably doesn't understand my rough instructions as "instructions for the placement of the cat", but something like "it's kind of a mess and this area is black".

2022-08-31
<img src='https://scrapbox.io/api/pages/villagepump/yuyasurarin/icon' alt='/villagepump/yuyasurarin.icon' height="19.5"/> from [/villagepump/2022/08/28](https://scrapbox.io/villagepump/2022/08/28)
- Maybe "black cats" is not enough of a cat element.
- Do you want to try to specify more poses or something?
    - If you have two of them, you could specify that too.
- And smudge? I don't think it should be a pen, just the hardest one you can find.

Redrawn!
![image](https://gyazo.com/5cf71e4c096265f10d983eac17e66f53/thumb/1000)

(I'm changing several conditions at the same time.) I set the image size to 512.
    - I saw that [[Effect of Image Size on Stable Diffusion]] is large.
- --prompt "black cats" --strength 0.88

![image](https://gyazo.com/c7817ea3772e0a6c693eae9e783b1739/thumb/1000)![image](https://gyazo.com/274288c037d847e36ce5d26cbe3b71d2/thumb/1000)![image](https://gyazo.com/6de59fc1d85f13cc092fa7fd1c7d92e1/thumb/1000)

![image](https://gyazo.com/b87ff6ec862993d33b501a95307f242b/thumb/1000)![image](https://gyazo.com/eee517f4561af8a946fb5da66031e6bd/thumb/1000)![image](https://gyazo.com/c3c6919e20226ea7f2338c7a472c3eae/thumb/1000)
That's good!

I'm going to revise the rough draft because it didn't convey the intent a bit.

![image](https://gyazo.com/7965b83238feb10891a56853da6bff91/thumb/1000)![image](https://gyazo.com/6a6c691c51bcf94f493d15d354bcb0f0/thumb/1000)
Er, why. You're making a lot of assumptions, W.

Let's change the seed and reroll in such a case.
![image](https://gyazo.com/3a006dd686357fd9dadccd1cbf8584a6/thumb/1000)![image](https://gyazo.com/4298c663a68545a8adacf62d6ab0e66d/thumb/1000)![image](https://gyazo.com/15c5ac1328189dfc65e89af0b3918a64/thumb/1000)
![image](https://gyazo.com/aa966aadc714cf6f7380082763e9e729/thumb/1000)![image](https://gyazo.com/1aca55ae6d3b33a90408736d7f3a540f/thumb/1000)![image](https://gyazo.com/169111d054e20695bbf9dd4df20c9283/thumb/1000)
The third one, I see. I changed the color of the cat's body to a ball or something, but the AI interpreted it as "the light blue thing by the cat must be a fish". That's good. I'll add "fish" to the prompt.
![image](https://gyazo.com/169111d054e20695bbf9dd4df20c9283/thumb/1000)![image](https://gyazo.com/423ef2479b291aabbc99fc99cb32d3ef/thumb/1000)![image](https://gyazo.com/c0eec61b440463f09eca54c8eba15c00/thumb/1000)
![image](https://gyazo.com/70965d5e320cbb04c3df147a16e77554/thumb/1000)![image](https://gyazo.com/b33f92c3ab3fa99d5cf8481d226689cd/thumb/1000)![image](https://gyazo.com/0caaea5e5c94f8850992fd506a6be1c1/thumb/1000)


Like 20 seconds for initialization and 30 seconds per piece for processing.

![image](https://gyazo.com/c7817ea3772e0a6c693eae9e783b1739/thumb/1000)![image](https://gyazo.com/7965b83238feb10891a56853da6bff91/thumb/1000)![image](https://gyazo.com/6de59fc1d85f13cc092fa7fd1c7d92e1/thumb/1000)

![image](https://gyazo.com/b87ff6ec862993d33b501a95307f242b/thumb/1000)![image](https://gyazo.com/c0eec61b440463f09eca54c8eba15c00/thumb/1000)![image](https://gyazo.com/c3c6919e20226ea7f2338c7a472c3eae/thumb/1000)

Try again with this image prompt of 512, which I thought was "worse" last time.
![image](https://gyazo.com/dbd1dfc892b0810d1de6a8c4303f4bf6/thumb/1000)

Much better results than last time.
It appears that the problem is caused by the small image size, not the fill of the image or the fullness of the prompts.
![image](https://gyazo.com/f381d93fbe8294416a244df74eeaeddf/thumb/1000)![image](https://gyazo.com/256abab50005f68b9c433937b172cca7/thumb/1000)![image](https://gyazo.com/2cd9c31f555477a31a9d519f05eac33c/thumb/1000)
![image](https://gyazo.com/89f0d09c5c0db597328e347699a0700e/thumb/1000)![image](https://gyazo.com/53fd3df0d4692662e8fe1ecf84a15148/thumb/1000)![image](https://gyazo.com/5d61d6d6218deef455f38044c98bf455/thumb/1000)

Experiments to mask and regenerate a portion of an image once generated

![image](https://gyazo.com/36580f245fe757e05ce3a32e126d8d91/thumb/1000)
0.8
![image](https://gyazo.com/68dba13ff6f0061f7a0921001666bb5d/thumb/1000)![image](https://gyazo.com/1ff42e3018b8d22a5d469e1d57e54be9/thumb/1000)
0.9
![image](https://gyazo.com/85171e9c36439d69f7e580949383b35f/thumb/1000)![image](https://gyazo.com/1a2717b5c93623f8fc63e5e64d7e3ae8/thumb/1000)
0.5 This would leave a noise mask.
![image](https://gyazo.com/5c75796213abf2a1f40231f87024f4b5/thumb/1000)![image](https://gyazo.com/04e821f9e80163772a1977b70db60dc2/thumb/1000)
0.7
![image](https://gyazo.com/2eb141f2d2ced8721a007fd1062e80e2/thumb/1000)![image](https://gyazo.com/7a12333db61822a0547b4ad8f2d777b9/thumb/1000)

Experiment with changing the prompt for img2img
We were talking about putting in the input on the left and getting the output on the right, and I said, "You specified the cat, didn't you?" He asked.
- To be precise, in addition to the image, we specify the prompt "black cat", a random seed, and a value for how much of the text and image should be mixed together
![image](https://gyazo.com/c7817ea3772e0a6c693eae9e783b1739/thumb/1000)![image](https://gyazo.com/b87ff6ec862993d33b501a95307f242b/thumb/1000)

Experiment with changing the prompt to something else.

black dog
![image](https://gyazo.com/b55351aa0f208d1207cff9d4a2cdcf6a/thumb/1000)![image](https://gyazo.com/0738314eba6f889688b2b9c66a865e17/thumb/1000)![image](https://gyazo.com/cc5446585d861ecf33b4f4818821a9b4/thumb/1000)

black rabbit
![image](https://gyazo.com/e2d2099209d3a739fdd6c94a0b1c938f/thumb/1000)![image](https://gyazo.com/31f9412a64994d1755e211c93ad6494e/thumb/1000)![image](https://gyazo.com/af08c1ff055307af25ca23ab148bd3dc/thumb/1000)

Example of trying to give a reckless instruction
bicolor cat (only the tip of one tail is white)
![image](https://gyazo.com/21958c4402abfb75b7bda7f3b2362ad3/thumb/1000)![image](https://gyazo.com/5f21e516bb2225264dc4135a6cfc0916/thumb/1000)![image](https://gyazo.com/cd3f07325fe321cf605be868da7152da/thumb/1000)
tabby cat. Only the tip of the tail has stripes.
![image](https://gyazo.com/95fbc48e3570404e730f5efd412b5b85/thumb/1000)![image](https://gyazo.com/0a543144926bb15bfa9850380298d6b3/thumb/1000)![image](https://gyazo.com/80fee87e839ab9d76c1bd0c85f332bd5/thumb/1000)

---
This page is auto-translated from [/nishio/Stable diffusionのimg2imgを試す](https://scrapbox.io/nishio/Stable diffusionのimg2imgを試す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.