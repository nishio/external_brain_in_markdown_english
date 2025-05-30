---
title: "Sharing files between repositories"
---

Suppose there is a file x in a git repository A
Suppose you want to use this x in another repository B

Solution 1 Hard link
- `$ cd B`
- `$ ln ../A/x`
Both A/x and B/x refer to the same entity. If you edit one, it will be shown as modified in the other repository.

Solution 2 git submodule
First move x from repository A to subdirectory C, then delete x from repository A
- `$ cd A`
- `$ mkdir C`
- `$ mv x C`
- `$ git status`
    - deleted:    x
    - Untracked files:
        - C/
- `$ git rm x`
    - rm 'x'
- `$ git commit -m "rm x"`

Create a bare repository bareC somewhere (here we are creating it locally, but of course it can be on github)
`$ cd ..`
`$ git init --bare bareC`

C to git repository and push to bareC
`$ cd A/C`
`$ git init`
`$ git add x`
`$ git commit -m "add x"`
`$ git remote add origin ../../bareC/`
`$ git push --set-upstream origin master`

Move to repository B where you wanted to use x in A and add bareC as a submodule. Now the file you want comes to B/C/x.
`$ cd ../../B`
`$ git submodule add ../bareC/ C`
`$ git commit -m "add submodule"`

Do the same on A's side.
`$ cd ../A`
`$ rm -rf C`
`$ git submodule add ../bareC/ C`
`$ git commit -m "add submodule"`

After editing B/x, git status shows this
:

```
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)
  (commit or discard the untracked or modified content in submodules)

	modified:   C (modified content)
```


When you go into C, you can see that x has been modified.
:

```
$ cd C/
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   x

no changes added to commit (use "git add" and/or "git commit -a")
```


Add, commit, push B/C/x. If you only commit and forget to push, you will not get the latest commit on the A side.
`$ git add x`
`$ git commit -m "update x"`
`$ git push`

By the way, B is in this situation now.
`$ cd ../B`
:

```
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   C (new commits)
```


git status on A does not show that C has been changed. submodule update...
`$ cd ../A`
`$ git submodule update`
Hey, A/C/x has not been updated.

If I move to C and pull, the change diff came down. Huh? Is this how you do it?
`$ cd C`
:

```
$ git pull
...
From .../bareC
   0e8c0b0..751f6b4  master     -> origin/master
Updating 0e8c0b0..751f6b4
Fast-forward
 x | 1 +
 1 file changed, 1 insertion(+)
Current branch master is up to date.
```



---
This page is auto-translated from [/nishio/リポジトリ間のファイルの共有](https://scrapbox.io/nishio/リポジトリ間のファイルの共有) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.