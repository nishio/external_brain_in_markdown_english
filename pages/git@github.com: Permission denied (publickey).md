---
title: "git@github.com: Permission denied (publickey)"
---

VSCode
> Error: Unable to Fetch from Remote(s)
>  git@github.com: Permission denied (publickey).
>  fatal: Could not read from remote repository.
>  Please make sure you have the correct access rights
>  and the repository exists.
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What do you mean?
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
This error means that SSH authentication failed when accessing the GitHub repository. The following are possible causes
2. the SSH agent is not reading the key
- If an SSH key is not added to the agent, access to GitHub will be denied.
- Launch agent:.
    - `$ eval "$(ssh-agent -s)"`
- Add key:.
    - `$ ssh-add ~/.ssh/id_rsa`

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What about recurrence prevention?

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
3. for Mac: macOS-specific settings
On macOS, if you register an SSH key in your keychain, it will be loaded automatically when you log in.
Register SSH key to keychain:
- `$ ssh-add --apple-use-keychain ~/.ssh/id_rsa`
Add the following to ~/.ssh/config
:

```
Host *
   UseKeychain yes
   AddKeysToAgent yes
   IdentityFile ~/.ssh/id_rsa
```



---<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
I guess it's because [[ssh-agent]] wasn't started automatically since [[~/.ssh/config]] already said this.
:

```
Host github
  AddKeysToAgent yes
  UseKeychain yes
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa
```


---
This page is auto-translated from [/nishio/git@github.com: Permission denied (publickey)](https://scrapbox.io/nishio/git@github.com: Permission denied (publickey)) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.