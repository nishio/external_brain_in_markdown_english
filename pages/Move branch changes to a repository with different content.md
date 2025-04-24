---
title: "Move branch changes to a repository with different content"
---

Method 1 is [[PATCH]].
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
Method 2: Move the entire branch with [bundle
- Create bundle file
    - Create a bundle for the branch to be migrated in the original repository
    - `$ git bundle create branch.bundle branch name`
- Import bundles in the destination repository
    - Execute the following command in the destination repository
    - `$ git pull /path/to/branch.bundle branch name`

*History is also imported as is, so if it does not match the base to which it is being migrated, adjustments must be made.

---

`% git pull ../branch.bundle main`
fatal: couldn't find remote ref main

---

<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
Check which branches are included in the bundle file. You can list the references with the following command
`$ git bundle list-heads ../branch.bundle`
Based on the branch name displayed, pull with the correct branch name. For example, if there is "mybranch" in the output,
`$ git pull ../branch.bundle mybranch`
and execute it.

---

`% git bundle list-heads ../branch.bundle`
5893d651bcf82e38c96f45d2ba87b1209ab604b2 refs/heads/devin/1741278569-fix-script

`% git pull ../branch.bundle refs/heads/devin/1741278569-fix-script`
Receiving objects: 100% (23/23), 9.02 KiB | 9.02 MiB/s, done.
Resolving deltas: 100% (6/6), done.
From ../branch.bundle
- * branch            devin/1741278569-fix-script -> FETCH_HEAD
hint: You have divergent branches and need to specify how to reconcile them. ...

---

`pull --rebase` or

![image](https://gyazo.com/0fc1fe140763d13d083a745b0d5cc65b/thumb/1000)

It's done.
- I was able to cut out what devin committed to private repo and port it to another repo.

Let's take the challenge further!
![image](https://gyazo.com/43f7d54ed0f2993018e0b0ea98ebd6ad/thumb/1000)

In this state git pull -rebase main.
`% git merge main `
Then, of course, it will be CONFLICTED. Then, of course, it will be conflict.
![image](https://gyazo.com/52c26f4de783657cfada79bb3f0ac36e/thumb/1000)
Oh, no, this one will stay in the history.

`$ git rebase -i --root`
![image](https://gyazo.com/5bc6015a74609c5676b1e0a95f852721/thumb/1000)
effect

![image](https://gyazo.com/1d9afcafac3a8edde1739f2521e21922/thumb/1000)
Chopped from first commit.
Delete the edit-readme branch
Now it's clean.


---
This page is auto-translated from [/nishio/異なる内容のリポジトリへブランチの変更を移す](https://scrapbox.io/nishio/異なる内容のリポジトリへブランチの変更を移す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.