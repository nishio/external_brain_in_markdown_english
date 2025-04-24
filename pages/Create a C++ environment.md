---
title: "Create a C++ environment"
---

`$ sudo docker pull ubuntu`
`$ sudo docker run -ti ubuntu /bin/bash`

`$ apt update`
`$ apt install lsb-core`
`$ apt install clang`
`$ clang --version`
`Ubuntu clang version 14.0.0-1ubuntu1`

`$ docker ps`
:

```
CONTAINER ID   IMAGE     COMMAND       CREATED         STATUS         PORTS     NAMES
3d28022df2a3   ubuntu    "/bin/bash"   3 minutes ago   Up 3 minutes             adoring_roentgen
```

`$ docker commit -p ubuntu lang2`
- `Error response from daemon: No such container: ubuntu`
- Use container id instead of image name
`$ docker commit -p 3d28022df2a3 lang2`

`$ sudo docker run -ti -v ~/langbook2/sample_codes:/data ubuntu /bin/bash`

---
This page is auto-translated from [/nishio/C++の環境を作る](https://scrapbox.io/nishio/C++の環境を作る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.