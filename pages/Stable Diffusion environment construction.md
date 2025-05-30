---
title: "Stable Diffusion environment construction"
---

[[Stable Diffusion]]


2022-09-22
- [[SSH to WSL2 from a Mac]]

I have two pieces of code checked out of stable diffusion, A and B. After creating a conda environment in A, I tried to experiment with B.
- You can think of it as an operational and experimental environment.
- I edited the source in the experimental environment, but for some reason it won't read.

answer volume
- `$ conda env create -f environment.yaml`
- In this, `pip -e . A is in the library path and import is done from A because of `pip -e .
- I created a conda environment with a different name for the experimental environment.



--- old log 1
All-in-one rar for Windows
- [https://grisk.itch.io/stable-diffusion-gui](https://grisk.itch.io/stable-diffusion-gui)
- Just unzip and run the exe to use it in the GUI.
- I put this in my gaming PC last night anyway.
    - Each piece can be made in about 40 seconds.
        - [[Diary 2022-08-25]]

Gaming PCs do not include a development environment.
- Start by Googling "how to use WSL"...
- I took the "just put Ubuntu from the store" thing in stride, and it stopped in the folded display, warning me that "wsl is not turned on."
    - I didn't realize it was taking so long until I turned on the detail view.
- I did wsl --install from a command prompt with administrator privileges and the installation started straight away.
- [https://github.com/CompVis/stable-diffusion](https://github.com/CompVis/stable-diffusion)
    - It says the GPU needs 10GB of VRAM, but I don't know if I meet the requirements first.
    - Find out how to check
        - Win-R [[dxdiag]]
            - ![image](https://gyazo.com/7dc99a5760ace58f1c0d2205d6cf59ca/thumb/1000)
            - Looks like only 8GB to me...w
    - Install Anaconda for Linux and
        - `$ conda env create -f environment.yaml`
        - `$ conda activate ldm`
        - LDM: [[latent diffusion model]]
    - Download sd-v1-4.ckpt from [Hugging Face
        - [https://huggingface.co/CompVis/stable-diffusion-v-1-4-original](https://huggingface.co/CompVis/stable-diffusion-v-1-4-original)
    - `$ python scripts/txt2img.py --prompt "cat" --plms --ckpt sd-v1-4.ckpt`
        - `RuntimeError: No CUDA GPUs are available`
        - 🤔

Troubleshooting

:

```
$ nvidia-smi
Fri Aug 26 21:21:14 2022
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 495.47       Driver Version: 496.76       CUDA Version: 11.5     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|                               |                      |               MIG M. |
|===============================+======================+======================|
|   0  NVIDIA GeForce ...  On   | 00000000:01:00.0 Off |                  N/A |
| N/A   52C    P8     6W /  N/A |    111MiB /  8192MiB |     N/A      Default |
|                               |                      |                  N/A |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                                  |
|  GPU   GI   CI        PID   Type   Process name                  GPU Memory |
|        ID   ID                                                   Usage      |
|=============================================================================|
|  No running processes found                                                 |
+-----------------------------------------------------------------------------+
```

WSL environment is GPU hardware aware

::

```
Python 3.8.5 (default, Sep  4 2020, 07:30:14)
[GCC 7.3.0] :: Anaconda, Inc. on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import torch
>>> torch.version.cuda
'11.3'
>>> torch.cuda.is_available()
False
```

Torch does not recognize CUDA capable GPUs

[https://zenn.dev/utahka/articles/ed881a568246f4](https://zenn.dev/utahka/articles/ed881a568246f4)
- > The wheel file in PyTorch includes CUDA, so you don't actually need the part in WSL that puts CUDA and cudnn into Ubuntu.
- Installing NVIDIA Drivers in Windows
    - [https://developer.nvidia.com/cuda/wsl](https://developer.nvidia.com/cuda/wsl)

:

```
$ nvidia-smi
Fri Aug 26 22:32:57 2022
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 515.65.01    Driver Version: 516.94       CUDA Version: 11.7     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|                               |                      |               MIG M. |
|===============================+======================+======================|
|   0  NVIDIA GeForce ...  On   | 00000000:01:00.0 Off |                  N/A |
| N/A   51C    P8    10W /  N/A |      0MiB /  8192MiB |      0%      Default |
|                               |                      |                  N/A |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                                  |
|  GPU   GI   CI        PID   Type   Process name                  GPU Memory |
|        ID   ID                                                   Usage      |
|=============================================================================|
|  No running processes found                                                 |
+-----------------------------------------------------------------------------+
```

`CUDA Version: 11.7`
- 11.5→11.7
- This seems to be the maximum version supported by the driver

CUDA Toolkit
:

```
(ldm) nishio@DESKTOP-0ET2LJF:/mnt/c/WINDOWS/system32$ nvcc -V
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2019 NVIDIA Corporation
Built on Sun_Jul_28_19:07:16_PDT_2019
Cuda compilation tools, release 10.1, V10.1.243
```

Torch expects CUDA to be 11.3 when in fact it is 10.1?

Install CUDA Toolkit on WSL (Ubuntu)
- [https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0&target_type=deb_local](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0&target_type=deb_local)
: 	

```
 wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-wsl-ubuntu.pin
 sudo mv cuda-wsl-ubuntu.pin /etc/apt/preferences.d/cuda-repository-pin-600
 wget https://developer.download.nvidia.com/compute/cuda/11.7.1/local_installers/cuda-repo-wsl-ubuntu-11-7-local_11.7.1-1_amd64.deb
 sudo dpkg -i cuda-repo-wsl-ubuntu-11-7-local_11.7.1-1_amd64.deb
 sudo cp /var/cuda-repo-wsl-ubuntu-11-7-local/cuda-*-keyring.gpg /usr/share/keyrings/
 sudo apt-get update
 sudo apt-get -y install cuda 
```


:

```
$ nvcc -V
...
Cuda compilation tools, release 10.1, V10.1.243
```

Still on 10.1.

:

```
(ldm) $ sudo update-alternatives --config cuda
There is only one alternative in link group cuda (providing /usr/local/cuda): /usr/local/cuda-11.7
Nothing to configure.
conda install pytorch torchvision -c pytorch
```

Uh, CUDA is only supposed to have 11.7 installed, right?
- Do I need to install 11.3?
    - Opinion that PyTorch should work with 11.7

:

```
(ldm) nishio@DESKTOP-0ET2LJF:~/stable-diffusion$ lspci
27fa:00:00.0 3D controller: Microsoft Corporation Device 008e
9e5b:00:00.0 3D controller: Microsoft Corporation Device 008e
```

Is it strange that I can't see it in lspci?
- It seems that's how it is in a WSL environment if you can't see it in lspci.
    - [https://qiita.com/ksasaki/items/ee864abd74f95fea1efa](https://qiita.com/ksasaki/items/ee864abd74f95fea1efa)

:

```
$ sudo apt-get remove nvidia-cuda-toolkit
...
The following packages will be REMOVED:
  nvidia-cuda-toolkit
0 upgraded, 0 newly installed, 1 to remove and 2 not upgraded.
...

$ nvcc -V

Command 'nvcc' not found, but can be installed with:

sudo apt install nvidia-cuda-toolkit

$ sudo apt-get install cuda
Reading package lists... Done
Building dependency tree
Reading state information... Done
cuda is already the newest version (11.7.1-1).
```


Hmm, nvcc is tied to nvidia-cuda-toolkit, version 10.1
I installed 1.17 of the CUDA Toolkit, but it won't turn that way.
Uninstall both, autoremove and remove all packages with dependencies, and then just apt-get install cuda.

I'm getting `Command 'nvcc' not found`.

Oh, it just doesn't pass.
:

```
$ /usr/local/cuda/bin/nvcc -V
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2022 NVIDIA Corporation
Built on Wed_Jun__8_16:49:14_PDT_2022
Cuda compilation tools, release 11.7, V11.7.99
Build cuda_11.7.r11.7/compiler.31442593_0
```


Delete and recreate the conda environment.
:

```
(ldm) $ python
>>> import torch
>>> torch.cuda.is_available()
True
```

Finally cuda available!

:

```
$ python scripts/txt2img.py --prompt "cat" --plms --ckpt sd-v1-4.ckpt
...
   attn = sim.softmax(dim=-1)
RuntimeError: CUDA error: unknown error
```

Yeah, yeah, yeah.

`$ python scripts/txt2img.py --prompt "cat" --plms --ckpt sd-v1-4.ckpt --n_samples 1 --W 256 --H 256`
- I was able to do it!

- [/motoso/Stable diffusion img2img with GTX1070 (8GB VRAM) #6307bc45774b170000b7fa8a](https://scrapbox.io/motoso/Stable diffusion img2img with GTX1070 (8GB VRAM) #6307bc45774b170000b7fa8a)
    - It seemed surprisingly easy to make it semi-precise.
- I was able to do it!
    - I can now run the Python script side and get the same thing instead of the exe version.
    - When multiple prompts are thrown from a file, a folder is created for each prompt, and each is created in iter specified number of copies.
        - I can do a "make 50 of this and 50 of that" before I go to bed.
    - In addition, JSON with parameter information is output like the exe version.

- Fine Tuning Tried and True Information
    - [https://birdmanikioishota.blog.fc2.com/blog-entry-8.html](https://birdmanikioishota.blog.fc2.com/blog-entry-8.html)
    - > This time we used COLAB, 16 images and about 3 hours of learning.
        - It could teach new concepts in a realistic way.

- [https://github.com/basujindal/stable-diffusion](https://github.com/basujindal/stable-diffusion)
    - A version that forks and sends the image to the GPU separately, and that can work with less VRAM, and even those who are running now can create larger images (I haven't tried it yet).


`$ python scripts/my.py --from-file prompts.txt --n_iter 100 --seed 130`
`$ python scripts/my.py --prompt "black cats" --n_iter 100 --seed 130`

---
This page is auto-translated from [/nishio/Stable Diffusion 環境構築](https://scrapbox.io/nishio/Stable Diffusion 環境構築) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.