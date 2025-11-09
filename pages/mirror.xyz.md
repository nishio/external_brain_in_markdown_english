---
title: "mirror.xyz"
---

[https://mirror.xyz](https://mirror.xyz)
<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>It is sold on a fully decentralized architecture - log in via wallet connection, content is permanently stored in [[Arweave]], and metadata is written on [[Ethereum]].

---
Try to connect Metamask
I guess it's like logging in on the [[Polygon]] network.
![image](https://gyazo.com/96fcb254a0d549db03c942491a89b77c/thumb/1000)
![image](https://gyazo.com/34669c5fa2fa319b74f7caf122288dd8/thumb/1000)
![image](https://gyazo.com/e2c7ae6de2702c61439105c192536341/thumb/1000)
[Protocol Rewards](https://support.mirror.xyz/hc/en-us/articles/21917161046804-Protocol-rewards)
- [https://chatgpt.com/s/t_688e0094bea481918fc388beb37b8e92](https://chatgpt.com/s/t_688e0094bea481918fc388beb37b8e92)

Entry published
- [https://mirror.xyz/0xd50c28f7Cda33859DFD34Bbab518cD50AcD5d610/eGyAROov06sZI2ZiqiHE-cOZZP9S7NTxeAfXNhChvZ0](https://mirror.xyz/0xd50c28f7Cda33859DFD34Bbab518cD50AcD5d610/eGyAROov06sZI2ZiqiHE-cOZZP9S7NTxeAfXNhChvZ0)

Profile page
- [https://mirror.xyz/0xd50c28f7Cda33859DFD34Bbab518cD50AcD5d610](https://mirror.xyz/0xd50c28f7Cda33859DFD34Bbab518cD50AcD5d610)

I thought I might get paid where I posted, but I didn't.
Where will the cost of preserving the content come from?

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
First, a conclusion -- the reason you don't have to pay gas or storage fees when submitting articles to Mirror is that Mirror "pays" the Arweave fee on the back end through the Bundlr Network. Authors can publish for free, and the permanent storage costs are covered later by readers collecting NFTs and Mirror's platform fees compensating the network.

1-1. the submission itself is "gasless"
- Mirror introduced the Writing NFT in 2022 with a "authors can mint/publish for free" design.
- The official guide also clearly states that "Writing NFT is deployment free, all that is required is gas for the reader to collect.
- The actual upload to Arweave is done via [[Bundlr]], with meta-transactions on L2 such as Optimism and Polygon to bring gas close to 0.

2. what is happening on the back end
- 2-1. [[Bundlr Network]]
    - Bundlr is a scaling layer that uses Arweave's bundling standard [[ANS-104]] to bundle multiple data and send them to Arweave L1.
    - Users and dApps can prepay storage fees with tokens of their choice, such as ETH/MATIC/SOL, and the Bundlr node will automatically convert the payment into AR.
    - Mirror periodically charges funds to this Bundlr wallet and only deducts a few tens or hundreds of wei from the balance at the time of submission, so it is not visible to the user.
- 2-2. real cost per article
    - With Arweave, you can prepay for 200 years of storage for about 0.000002 AR (a few tens of dollars) for about 10 KB of text.
    - Bundled processing by Bundlr further compresses this to 1/100, making it profitable even if Mirror bears the cost.


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What makes the people who [[Mint]] and Collect happy?

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>For authors, the main motivation is "permanent preservation + monetization + community building"; for collectors, "ownership + privilege access + cultural/economic return.
[https://chatgpt.com/s/t_688e0afd14cc81919f67c68dbec39c1e](https://chatgpt.com/s/t_688e0afd14cc81919f67c68dbec39c1e)

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Are authors permanently stored at the time they write? Or when someone [[Lazy Mints]] and collects?

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>The moment the "Publish" button is pressed in Mirror, the full text of the article is uploaded to Arweave via Bundlr and is instantly and permanently stored without the author having to pay a penny; the Writing NFT is a proof of ownership token for the article, and the NFT contract itself is a Lazy The NFT contract itself is deployed and minted only when the first Collect user comes up, and that person pays for the gas. Thus, there are two steps: preservation is done at the time of the author's publication, and NFT conversion is done at the time of the first Collect.
[https://chatgpt.com/s/t_688e1143ecfc8191b29f62372f0cc4e0](https://chatgpt.com/s/t_688e1143ecfc8191b29f62372f0cc4e0)

-----
Not much of a disadvantage on the author's side,

---
This page is auto-translated from [/nishio/mirror.xyz](https://scrapbox.io/nishio/mirror.xyz) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.