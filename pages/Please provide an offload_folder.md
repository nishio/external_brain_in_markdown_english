---
title: "Please provide an offload_folder"
---

I was running [[LLM]] in [[Google Colaboratory]] and got the following error.

`model = AutoModelForCausalLM.from_pretrained(MODEL_NAME, device_map='auto')`
> ValueError: The current `device_map` had weights offloaded to the disk. Please provide an `offload_folder` for them. Alternatively, make sure you have `safetensors` installed if the model you are using offers the weights in this format.

It says "Please provide an offload_folder" (please specify an offload_folder), but there is a trap that this is not appropriate in the case of "It worked fine earlier, but it stopped working after some trial-and-error.

This is a situation where the GPU and memory are insufficient, so the disk is used to force the system to run, even though it is slow. This is the state of "I don't have enough GPU and memory.
- > The current `device_map` had weights offloaded to the disk.
- And yet no offload destination is specified, so I'm asked, "Where do I put the file?" I'm asked.
    - The auto device_map has led to a state contrary to the user's intention.
- Once it is running without specifying offload_folder, there is usually enough GPU memory and no need to offload it.
    - So, the root cause of the problem is that "models loaded in the past while you are doing various things are not erased, but remain and are squeezing memory".
- In that case, the quick fix is to "restart the runtime.

Silent offloading to memory is occurring before this error occurs.
- Counter(model.hf_device_map.values())` is `Counter({0: 28, 'cpu': 15})` when it should be `Counter({'cpu': 41, 0: 2})`. This is hard to notice.
- I didn't notice it either until yesterday, and finally understood it after a lot of observation with the help of `hf_device_map`.
- In this case, garbage remains in the GPU and is packed into the GPU just in time for model loading, so when there are many input tokens in subsequent processing, `model.generate` may fail with `OutOfMemoryError: CUDA out of memory.` or `model.generate` may fail with `OutOfMemoryError: CUDA out of memory.`. in `model.generate`.
    - Some people get into this a lot too.
    - It's pretty much a waste of time as it moves and dies in the process.
    - In the [[Matsuo Lab LLM Summer School Competition]] I was participating in this time, there is a big input after the 100th of the test data, so I saw people running up to it and dying.
- Even if you're lucky enough to move all the way to the end, it's still a waste of time.


Why does this happen when Python has GC?
- In the case of `model = AutoModelForCausalLM.from_pretrained(MODEL_NAME, device_map='auto')`
    - First, the right-hand side object is generated
    - The new object is then assigned a name.
    - GC runs when the reference to that old object becomes invalid.
- So the setting "auto-determines resource allocation by looking at the resource status" at the time of object creation on the right side determines offloading to disk by looking at the current memory consumption before the old one is released by the GC.
- In addition, it seems that even if GC is done on the Python side, the cache may remain on the CUDA side, so it is easiest to restart the runtime since it is a pain in the ass.

- [[Matsuo Lab Summer School 2023 Large-Scale Language Models]]

Trying this now.
py

```
model = None
tokenizer = None
torch.cuda.empty_cache()
tokenizer = AutoTokenizer.from_pretrained(MODEL_NAME, use_fast=False)
model = AutoModelForCausalLM.from_pretrained(MODEL_NAME, device_map='auto')
```


---
This page is auto-translated from [/nishio/Please provide an offload_folder](https://scrapbox.io/nishio/Please provide an offload_folder) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.