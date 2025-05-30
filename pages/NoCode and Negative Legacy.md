---
title: "NoCode and Negative Legacy"
---

What conditions are necessary for [[NoCode]] not to become [[negative legacy]]?

Twitter is hard to follow the discussion, so I summarized it, [[tokoroten]] for quotes without names, nishio for comments that are not quotes.
[https://twitter.com/tokoroten/status/1285265957208772610](https://twitter.com/tokoroten/status/1285265957208772610)
- > Excel VBA macros have become a negative legacy, I wonder what conditions are necessary for so-called NoCode and RPA to not become a negative legacy.
    - >  I think perhaps VBA has become a negative legacy because the logic is in a local file + deep in the back and not easily visible, but can we get around that by managing it on a server?
        - Even though it's better than VBA, just putting it on the server doesn't change the fact that it's placed "in the back".
        - Difficult to read and decipher even if you have access to the completed program
        - The "process by which it is made" needs to be shared, not the finished product.
- > In the first place, some of the projects that come to the SIer even at this point in time are in the form of hellish code developed by amateurs in VBA and Access, and the reality is that the person in charge has disappeared and there is nothing that can be done about it. I have a feeling that RPA and NoCode have not yet created that stage of spaghetti code.
    - > "Amateur development doesn't take handover into account, so there will be hell to pay when it's time to take over."
    - >  Neither RPA nor NoCode have manifested problems because the handover has not yet occurred.

- > NoCode and RPA platforms that can be maintained by a group of people would be one solution.
- >  If you add an advisor to this that you can consult with on a monthly basis, it's rather manageable.
- >  At least it's somewhat better than Excel VBA or Access VBA, which only work locally.
- > I wonder how well it can be integrated with communication tools to promote the part that can be maintained by a group.
- >  For example, when you say that BigQuery's WebConsole can be "collectively maintained", that's just hmmm.
- >  There must be a lead-in line as an extension of the usual workflow.
- > Then I think I see Cybozu's good positioning of kintone.
- >  Automation is placed next to the usual business line, that's a strong point.
    - With the current version of kintone, data can be communicated next to the data, updated, and automatically versioned, but ideally, the database schema and customized JavaScript should be able to be edited together as well. I think the ideal situation would be to be able to collaboratively edit the database schema and customized JavaScript as well.

> This is probably the same with regular programming languages, and the key to the future will be how to solve the problem of "you can't go look at the source code, test it, or deploy it without trying".
>  How to lower the skill hurdle here.

> I came up with the hypothesis that RPA and NoCode have less of a "naming" process than programming, so there is no reading of meaning.
>  So often code written by amateurs is also unreadable because the "naming" is corrupt, but RPA and NoCode are even more difficult to read for meaning because there is less "naming".
- You are right that naming lowers "future maintenance costs", and the same goes for comments and commit logs. But I don't see the value of those things at the beginning of use, so it's hard to design a system that requires them. kintone allows you to change the field IDs to human-understandable names, but I wonder how many users are using that.
- Therefore, it is necessary to have a mechanism to collect data for reading without explicit effort by the user, and "rewriting while communicating and the communication log is linked to the change differences" is one of the methods. But if there is only one person in the company who can do this, there will be no communication.
    - Providing a place for him to share his knowledge when there is only one person in the company to tinker with is being promoted in the form of "creating a development community," but it seems that the problem of having no one to take over when the only person in the company quits is not something that people outside the company can do anything about.... Is it about helping him build a following within the company?
    - > If I were in Cybozu's shoes, I would hold a kintone user study group or something like that, and have people interact with each other there, and then create an outlet outside the company where they can ask for advice, or take beginners inside the company out there, or get them hired through there because the company is in trouble if they are alone.
    - >  (Risk of being pulled out is likely to increase)
    - Well, it's a common pattern to have a user workshop hosted by a manufacturer company.
        - [kintone devCamp - connpass](https://kintonedevcamp.connpass.com/)
    - I'm not sure if they are reaching out to their clients to create opportunities to hire people who understand kintone (and not just DX), but considering the business continuity of their clients, this may be one way to provide value to their clients.
    - > I was wondering if there could be some kind of exchange program between companies via user groups.

> hrjn: Even if you can develop normally, if you don't write a design doc and leave the purpose and design of the code, you may not know what's in it, and even if you write documentation, you may not understand it well.
>  Since it is impossible to analogize intent or background from a combination of generic components, the question is how to keep recording and updating the context.
> The people who used to say "BDD, not TDD" understood this and knew that if they just wrote normal test code, it would make no sense. If you write a test that says, "If you enter 20, it returns 22," it doesn't make sense. So they would write something like, "If you put in 20, it returns 22.
>  I was reading and interpreting zapier's obit a while ago, and the main vexation was the same as the alternative to programming. Interpreting logic without comments is extremely difficult.
>  It's not possible to do step execution, print debugging, and if it's bad, it's more difficult than programming.

Functions to prevent negative legacy
- Memo for application administrator
    - > Make it easier to continuously improve the app by keeping a memo for the app manager on how the app was created, its purpose, key design and configuration points, notes, etc.
    - >  When there are multiple administrators of an application, make it easier for multiple people to work on the settings by keeping a memo of what you want to share among the administrators.
    - [https://jp.cybozu.help/k/ja/user/app_settings/notes_for_app_administrators.html](https://jp.cybozu.help/k/ja/user/app_settings/notes_for_app_administrators.html)

---
This page is auto-translated from [/nishio/NoCodeと負の遺産](https://scrapbox.io/nishio/NoCodeと負の遺産) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.