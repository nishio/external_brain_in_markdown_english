---
title: "GPU Instance"
---

ubuntu based.

- tensorflow
    - [https://www.tensorflow.org/install/install_linux](https://www.tensorflow.org/install/install_linux)
    - `pip install --upgrade tensorflow-gpu` `Could not find any downloads that satisfy the requirement tensorflow-gpu`.
    - I was able to install it by specifying the URL as described.
    - 1.1.0

- scikit-learn
    - sudo pip install scikit-learn

- keras
    - sudo pip install keras


- I don't want to lose intermediate results when a spot instance dies.
    - Only one instance is mounted at a time.
        - If you keep the EBS mounted, that's not going away.
    - If you want to mount it on multiple instances
        - EFS (but it does not work in the Tokyo Region)
        - Set up your own NFS server -> easy if you enter a VPC
        - monit+rsync
        - Watch for termination notices: [spot/termination-time](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html)
        - [http://qiita.com/iogi/items/62f84e0ebfdc7afd9539](http://qiita.com/iogi/items/62f84e0ebfdc7afd9539)
        - [Dropbox](http://tm.root-n.com/server:dropbox:etc:dropbox_on_linux)
            - CLI does not go in well -> give up or stand up X and VNC


[New Amazon EC2 P2 instances are now available in the Tokyo Region ｜ Developers.IO](http://dev.classmethod.jp/cloud/aws/ec2-p2-now-available-in-tokyo/)




Running Chainer on an EC2 GPU instance with 5 lines of Chainer and 4 lines of Chainer - If you make it the Lord everywhere, it will be true everywhere.
[http://sla.hatenablog.com/entry/chainer_on_ec2](http://sla.hatenablog.com/entry/chainer_on_ec2)
Quickly use Chainer with AWS
[https://orientalrobotics.blogspot.jp/2015/07/awschainer.html](https://orientalrobotics.blogspot.jp/2015/07/awschainer.html)
Chainer on EC2 spot instance environment with AWS Lambda - Qiita
[http://qiita.com/pyr_revs/items/bf483b96cca6b01a9110](http://qiita.com/pyr_revs/items/bf483b96cca6b01a9110)
How to stop an EC2 instance when a script that takes a long time to process finishes - Masteries
[http://papix.hatenablog.com/entry/2016/06/02/131754](http://papix.hatenablog.com/entry/2016/06/02/131754)
---
This page is auto-translated from [/nishio/GPUインスタンス](https://scrapbox.io/nishio/GPUインスタンス) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.