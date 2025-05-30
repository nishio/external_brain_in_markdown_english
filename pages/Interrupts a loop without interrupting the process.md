---
title: "Interrupts a loop without interrupting the process"
---

When a single process is heavy and it is done in a double loop, there are cases where you want to interrupt the loop without interrupting the process

For example, "trying to generate an image from text by AI for various texts while changing the random seed" is a heavy process in a double loop.
- Suppose we have a "loop about text" inside a "loop about seed."
- Read the target text from a file at the beginning of each seed process, so the process does not need to be restarted each time a target is added or removed
- By the way, let's say you have a text that you want to know the result of as soon as possible.
    - Even if it is written at the top of the list to be processed, it will not be read until the "loop for the text currently being executed" is completed.
    - So, I want to break the loop that is currently executing.
        - But if you interrupt the process, you have to start from loading the model.

Use user-defined signals to resolve this situation
test.py

```
from time import sleep
import signal

class SignalRecieved(Exception):
    pass

def break_loop(signum, frame):
    raise SignalRecieved

signal.signal(signal.SIGUSR1, break_loop)
for i in range(10):
    try:
        for j in range(10):
            print(i, j)
            sleep(0.5)
        print("after for j")
    except SignalRecieved:
        print("except")
    print("after try")
```


Operation (Japanese words beginning with # are added comments)
:

```
$ python test.py
0 0
0 1
0 2
# Suspend a running process (SIGTSTP)
^Z
[1]+  Stopped                 python test.py
# Process is paused, job number is 1
# Send user-defined signal (SIGUSR1) to job 1
$ kill -s USR1 %1
[1]+  Stopped                 python test.py
# Resume a paused process in the foreground
$ fg
python test.py
except
after try
1 0
1 1
1 2
# You can see I left the inner loop and started the next loop.
# By the way, the well-known Ctrl+C is an interruption signal (SIGINT)
^C
Traceback (most recent call last):
  File "/home/nishio/mysd/stable-diffusion/scripts/test.py", line 15, in <module>
    sleep(0.5)
KeyboardInterrupt
```



---
This page is auto-translated from [/nishio/プロセスを中断せずにループを中断する](https://scrapbox.io/nishio/プロセスを中断せずにループを中断する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.