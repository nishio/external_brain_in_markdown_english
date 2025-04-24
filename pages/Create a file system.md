---
title: "Create a file system"
---

I accidentally [[Disk Full]] on [[EC2]], so I attached the [[EBS]] volume.
Create a file system for use from Linux

:

```
$ sudo file -s /dev/nvme1n1 
/dev/nvme1n1: data
```

No [[file system]] yet

make up (one's face, etc.)
:

```
$ sudo mkfs -t ext4 /dev/nvme1n1 
...
```


:

```
$ sudo file -s /dev/nvme1n1 
/dev/nvme1n1: Linux rev 1.0 ext4 filesystem data, UUID=8597b873-d6ea-40c7-9acb-176082ddd381 (extents) (large files) (huge files)
```

The file system is ready.

Extra: Mounting
:

```
$ sudo mkdir /mnt/data
$ sudo mount /dev/nvme1n1 /mnt/data/
$ df -h
Filesystem      Size  Used Avail Use% Mounted on
...
/dev/nvme0n1p1   97G   97G  1.5M 100% /
/dev/nvme1n1     99G   60M   94G   1% /mnt/data 
$ sudo chown ubuntu:ubuntu /mnt/data
```

---
This page is auto-translated from [/nishio/ファイルシステムを作る](https://scrapbox.io/nishio/ファイルシステムを作る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.