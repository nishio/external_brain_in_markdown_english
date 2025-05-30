---
title: "Application installation or account creation is required to participate in Zoom since 4/4 (fixed)."
---

(4/9 update) With the 4/4 modification of Zoom, "people who participate only with a browser without installing an app" who could participate only by knowing the URL were unable to participate without logging in with a Zoom account. The setting is now available.

> April 6, 2020 [src](https://support.zoom.us/hc/en-us/articles/204758419-New-Updates-for-Web)
- >  New and enhanced features
    - >  Admin features
        - >  Added setting “Only authenticated users can join meetings from Web client”
        - >  By default, users will now need to sign in to their Zoom account or create a Zoom account when joining a meeting with the web client. This setting is available at the account, group, and user level and can be locked at the account or group level.

![image](https://gyazo.com/13d1a6ef8f9121173dba17c3db34878d/thumb/1000)
- Unchecking this option allows users without an account to participate
- Of course, eliminating the need to log in increases risk, but security and convenience are a trade-off.
- The feature has just been added and has not been translated in time. It may be translated and look different in the future.



--- logs below

> In accordance with Zoom's 4/4 modification, with regard to "people who participate only with a browser without installing an app," what used to be possible only by knowing the URL has been changed so that people can participate only by logging in with their Zoom account.
>
> This in itself has the effect of preventing undesirable participants from re-entering the room in the unlikely event that they enter and are kicked out.
> But if you are not aware of this change in specifications and are thinking "let's do it the same way as before," you may be flabbergasted on the day of the event, so here's a reminder.
[I wrote in the Facebook information sharing group](https://www.facebook.com/groups/146940180042907/permalink/150895796314012?sfns=mo), which is reprinted here

primary source
[https://support.zoom.us/hc/en-us/articles/204758419-New-Updates-for-Web](https://support.zoom.us/hc/en-us/articles/204758419-New-Updates-for-Web)
> April 4, 2020
- > Changes to existing features
    - > New join flow for the web client
        - >  Users will now need to sign in to their Zoom account or create a Zoom account when joining a meeting with the web client.

---
From this point forward, we are talking about cases where SSO is contracted on an organizational basis.

As of 4/7, the following problems exist

When a guest tries to join a meeting room created by an account that is subscribed and SSO'd by an organizational unit from a browser without installing the application, the guest is asked to log in as well. However, there is a glitch where that login screen becomes the SSO screen for that organization, and if a guest from outside the organization is trying to join in that way, they cannot log in and therefore cannot join the meeting.

In such a case, the organization name is "foobar" and the conference room URL is as follows
[https://foobar.zoom.us/j/88888888888?pwd=xxxxxxxxx](https://foobar.zoom.us/j/88888888888?pwd=xxxxxxxxx)
Rewrite this as follows to create a non-SSO login
[https://zoom.us/j/88888888888?pwd=xxxxxxxxx](https://zoom.us/j/88888888888?pwd=xxxxxxxxx)
Users who meet the conditions should rewrite the above when sharing the meeting room URL

---
This page is auto-translated from [/nishio/4/4以降Zoom参加にはアプリインストールかアカウント作成が必須(修正済み)](https://scrapbox.io/nishio/4/4以降Zoom参加にはアプリインストールかアカウント作成が必須(修正済み)) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.