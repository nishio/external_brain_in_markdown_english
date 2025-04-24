---
title: "I want to try Gov4Git."
---

2024-02-09
[[gov4git]]
- I'm in the PluralityBook community as a non-admin general participant, but I knew I needed to experience the admin position.
- But I didn't know how to install it even though I looked at the Web site.
- [https://github.com/gov4git/gov4git](https://github.com/gov4git/gov4git)
- > [gov4git](https://twitter.com/gov4git/status/1755663386682269769) Today we released a new website. Take a peek for an updated intro to our product and market stance [https://gov4git.org](https://gov4git.org) #AI_Alignment #AI_Policy #Community_Managementgov4git.org
- >  gov4git: Decentralized governance for git communities

- First of all, it is for small practice, not for the real thing.
    - [https://github.com/nishio/otameshi_gov4git](https://github.com/nishio/otameshi_gov4git)

- [https://github.com/gov4git/gov4git/blob/v2/doc/USER.md](https://github.com/gov4git/gov4git/blob/v2/doc/USER.md)
- >  member / organizer
    - said to be
    - >  General Participants / I still need to experience the manager's position.
- [https://github.com/gov4git/gov4git/blob/v2/doc/ORGANIZE.md](https://github.com/gov4git/gov4git/blob/v2/doc/ORGANIZE.md)
    - > The first responsibility of the organizer is to deploy the governance system. This task is documented in the Deployment Guide.
    - >  Once the governance system is up and running, the organizer is responsible for governing the day-to-day function of the community, as described in the Governance Guide.

- [https://github.com/gov4git/gov4git/blob/v2/doc/DEPLOY.md](https://github.com/gov4git/gov4git/blob/v2/doc/DEPLOY.md)
    - Go install / add to PATH / clone repos
    - `$ go get github.com/gov4git/gov4git/gov4git@latest`
:

```
...
go: added github.com/gov4git/gov4git v1.1.15
% gov4git version
zsh: command not found: gov4git
```

- Where was it installed?

> [hnakamur2](https://twitter.com/hnakamur2/status/1755949197889847436) `go install ... `and then...
>  ~/go/bin/gov4git
>  installed on the
> [hnakamur2](https://twitter.com/hnakamur2/status/1755949588727697584) Since Go 1.17 go install is required to install the executable.
>  [Deprecation of 'go get' for installing executables - The Go Programming Language](https://go.dev/doc/go-get-install-deprecation)
> [nishio](https://twitter.com/nishio/status/1755950378724557241) Thank you! It's done!

:

```
% ~/go/bin/gov4git version
{
   "version": "v1.1.15",
   "revision": "",
   "last_commit": "0001-01-01T00:00:00Z",
   "dirty_build": true
}
```


> The governance automation — invoked by the GitHub action — executes on behalf of a dedicated GitHub user, which represents the governance system itself. You must create a new GitHub user, designated as the governance automation user — and name it appropriately, as it will speak to the community users via GitHub comments.
>  For instance, the Plurality Book Project — @pluralitybook on GitHub — uses a dedicated user called Plurality Book DAO — @pluralitybook-dao on GitHub — to operate the governance system.
account
- otameshi-dao

>  Invite the automation user to your organization with Owner privileges.
organization
![image](https://gyazo.com/eb46ebc97c5fd13f168839613bd38e29/thumb/1000)

![image](https://gyazo.com/8b0970baf8aa9fcc5af9396214a84d92/thumb/1000)

![image](https://gyazo.com/eca9ce2444e81f104052ec27a4ce8886/thumb/1000)
- This?

![image](https://gyazo.com/a45488271383ed291d0f34f9fdb2f687/thumb/1000)
- Oh, this one.

![image](https://gyazo.com/6820102f5ea21c2464e85cb7b5e9fb5d/thumb/1000)

> Under "Organization permissions" make the following choices:
- I can't find this.

> Deploy governance for your project repository
>  You are now ready to deploy governance on your project repository. This can be accomplished with a single command:

$GOV4GIT_RELEASE
v2.1.3


> 403 You need admin access to the organization before adding a repository to it.

![image](https://gyazo.com/96b028c8341f556ebb33f9eee5f17fcb/thumb/1000)

---
Make repos first?
[https://github.com/otameshi-gov4git-org/first-test-repos](https://github.com/otameshi-gov4git-org/first-test-repos)
I made it.
> 403 You need admin access to the organization before adding a repository to it.
seemingly unrelated

---
This page is auto-translated from [/nishio/Gov4Gitを試したい](https://scrapbox.io/nishio/Gov4Gitを試したい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.