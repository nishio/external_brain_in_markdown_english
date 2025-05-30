---
title: "Docker for Mac"
---

Using Chainer on a Mac is not supported, and I decided to use Docker because of the hassle of porting it when I want to run it on a server after I've created something.

`$ brew install docker`
`$ brew cask install docker`
`$ docker run -p 8888:8888 --name ml -it asashiho/ml-jupyter-python3`
- [Docker is useful when studying machine learning - Asa's Alone](http://dr-asa.hatenablog.com/entry/2017/08/21/185301)
- [https://hub.docker.com/r/asashiho/ml-jupyter-python3/~/dockerfile/](https://hub.docker.com/r/asashiho/ml-jupyter-python3/~/dockerfile/)
- When executed, Jupyter Notebook starts up.
- After Ctrl-C, the container does not disappear, but is stopped.
    - `$ docker start /ml`
    - `$ docker exec /ml pwd`
    - /notebooks

If you want to access data files, results files, etc. from the outside, Bind mounts instead of Volumes seems to be the way to go.
- [https://docs.docker.com/storage/#choose-the-right-type-of-mount](https://docs.docker.com/storage/#choose-the-right-type-of-mount)

`$ docker run -p 8888:8888 --name ml -it --mount type=bind,source=/Users/nishio,target=/notebooks/home asashiho/ml-jupyter-python3`

memo
- Chainer is not included.
- pip is old
    - You should consider upgrading via the 'pip install --upgrade pip' command.
    - # pip install --upgrade pip
- I'll be about 30% slower.

---
This page is auto-translated from [/nishio/Docker for Mac](https://scrapbox.io/nishio/Docker for Mac) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.