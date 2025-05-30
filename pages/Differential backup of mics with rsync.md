---
title: "Differential backup of mics with rsync"
---

Backing up by copying the entire file is inefficient because the same file is copied over and over again.
Hard link unmodified files with rsync
- The "--link-dest" option for differential backups with [rsync: Command Technica - ITmedia Enterprise [https://www.itmedia.co.jp/enterprise/articles/0804/25/news](https://www.itmedia.co.jp/enterprise/articles/0804/25/news) 034.html]

While normal backups copy all visited regions, this method saves space and speeds up the process by copying only the regions that have been updated.

2021-11-19
- Python.
- `--exclude-from=FILE     read exclude patterns from FILE`
- `$ du -d 3 . | sort -nr`

2021-10-25
bash

```
rsync -a --delete --link-dest=../`ls | grep "backup" | tail -n1` minecraft_server backup`TZ=Asia/Tokyo date +%Y%m%d_%H%M`
```


explanation
- backup`TZ=Asia/Tokyo date +%Y%m%d_%H%M`
    - Create a file name like `backup20211025_1624` based on the current time.
- `ls | grep "backup" | tail -n1`
    - Get the last filename containing BACKUP


Note on rsync options
:

```
-a, --archive               archive mode; equals -rlptgoD (no -H,-A,-X)
-r, --recursive             recurse into directories
-l, --links                 copy symlinks as symlinks
-p, --perms                 preserve permissions
-t, --times                 preserve modification times
-g, --group                 preserve group
-o, --owner                 preserve owner (super-user only)
-D                          same as --devices --specials
    --devices               preserve device files (super-user only)
    --specials              preserve special files
```


- [[Micra]]

Python script I was using before I made the difference
python

```
import shutil
from datetime import datetime 

IGNORE = """
.git
jdk*
*.jar
logs
block-backups
.archive-unpack
*.tar
""".strip().splitlines()

now = datetime.now().strftime("%Y%m%d_%H%M")

shutil.copytree(
    "minecraft_server", 
    f"backup{now}",
    ignore=shutil.ignore_patterns(*IGNORE),
)
```


---
This page is auto-translated from [/nishio/rsyncでマイクラを差分バックアップ](https://scrapbox.io/nishio/rsyncでマイクラを差分バックアップ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.