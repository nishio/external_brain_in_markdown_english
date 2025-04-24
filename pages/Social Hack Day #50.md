---
title: "Social Hack Day #50"
---

2023-05-27 Participated as a first step in the [[MintRally UX Upgrade Sprint]].
    - [[Public-Private Co-Creation HUB]]

> [@codeforjapan](https://twitter.com/codeforjapan/status/1662362592822837248): In today's memorable 50th #socialhackday, 6 projects, online + offline! 30+ of you joined us 🙌 Progress report & petite get-together at 5pm 💃.
> ![image](https://pbs.twimg.com/media/FxHlh_raYAAorMS.jpg)

> [@hal_sk](https://twitter.com/hal_sk/status/1662287811620519936?s=20): 50th Social Hack Day, underway.
> Today is a hybrid event and lots of onsite participation! Thank you 🙌
> Today, gussuri (sleep records), Open Data Package manager, Nagareyama Make our City, HackDays (web3), Moripo (decarbonization), and After Pill Search are registered projects.
> #socialhackday
> ![image](https://pbs.twimg.com/media/FxGh87cacAAKHrZ.jpg)

> [@nishio](https://twitter.com/nishio/status/1662378408721154049?s=20): I attended Social Hack Day `#50`!
>  [https://opensea.io/ja/assets/matic/0x7d895ca96caa5344ec0b732c6e1defa560671e14/442](https://opensea.io/ja/assets/matic/0x7d895ca96caa5344ec0b732c6e1defa560671e14/442)
- ![image](https://gyazo.com/d68b0457b8780640055fe9f667805995/thumb/1000)

[[MintRally]] is a service that issues "Certificate of Participation NFTs" as described above.
- The "certificate" issued is NFT, so it is not closed within the MintRally service.
- In fact, the above Tweet shows NFTs issued on MintRally on the world's largest NFT trading platform [OpenSea
- > [@nishio](https://twitter.com/nishio/status/1662311155069779968): I was told that I could see/show the NFT of the proof I attended Plurality Tokyo on OpenSea! It's just hidden by default, I just had to unhide it!
- >  [https://opensea.io/assets/matic/0x7d895ca96caa5344ec0b732c6e1defa560671e14/375](https://opensea.io/assets/matic/0x7d895ca96caa5344ec0b732c6e1defa560671e14/375)
    - ![image](https://gyazo.com/1b36ba74e71bddb2a280725fc0fcddf7/thumb/1000)

whole
- Even if you come to the physical venue, enter Zoom first.
    - Chat is a great way to share URLs.
- Code for Japan
    - [[administrative co-creation]].
        - Not [[dependence on government]].
- I do online-only and hybrid every other month.
- Inspired by [[jonthon]] of [g0v
- self-introduction
    - Use Notion as a place to share information
    - Get Notion access and add your own records to the table
        - > Code for Japan utilizes Slack and Notion for community management. These two workplaces of Code for Japan are open to anyone who is interested in civic tech.
            - [Community | Activities | Code for Japan](https://www.code4japan.org/activity/community)
        - I was new to this, so I joined Slack and Notion on the spot.
    - I made the mistake of editing the title of Home in an attempt to find the page for this event, mistaking it for a search. w
        - I put it right back in, so it's safe.
        - This time I went to the URL of the Zoom chat.
        - The search field is not prominently displayed, so I guess the expected flow is to follow the tree view in the sidebar.
            - Is there a way to see "recently updated pages?"
        - [Social Hack Day #50](https://www.notion.so/code4japan-community/Social-Hack-Day-50-84fd842a943c4ab4800011298cc41f55)
            - Introduce yourself by writing three key words
            - A good mechanism for introducing yourself when time is limited.
            - I can see what people around me are writing about while I'm writing.
            - Three keywords can prevent long-winded conversations, and avoid the risk of a chain of people who introduce themselves with zero information, such as "I'm Nishio, nice to meet you," creating such an atmosphere and ruining the usefulness of the self-introduction forum itself.
            - It's a good onboarding design to give newcomers a real-time co-editing experience at this time.
                - This could be a good reference even when using Scrapbox
- Introduction of each project and presentation of what we will do today
    - They all sound interesting in their own way.
    - Talk about how things are going and what you plan to do today.
    - A sort of "[[morning meeting]]" of sorts.

Divided into individual project teams
MintRally

(Not a time log, but reconstructed by adding what I researched and thought about later.)

Has it recently become possible for people without an Ethereum address to receive it?
- Use MAGICLINK?
    - [https://magic.link](https://magic.link)
- [[non-custodial]]？custodial？
    - I understood that the MAGIC side has an Ethereum address and provides access to it with an email address.

What is network switching?
- Ethereum's Main Net
    - This is expensive.
- There is another net called Polygon.
    - This is a cheap way to write to Ethereum.
    - Why?
        - Because transactions are written in batches.
        - I see, in a computer, the cost of memory fetching is high, so you put a faster cache memory in between.
        - If you're writing in batches, I'm assuming the delay until the buffer is actually written to Ethereum will increase by the buffer, but by how much?
    - Is this kind of thing called L2 protocol?
        - Polygon hashes written to Ethereum?

What are you doing with your private key?
- I keep it in my password manager.
- If there's a lot of money in there, the recommendation is to print it out and put it in a safe.
- In the end, a trade-off between risk and convenience
    - If there's not a lot of money in it, the risk is small enough to make it messy.
- The name "wallet" is a mismatch for some use cases.
    - So, on this page, we read "address" exclusively.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

Published NFTs are not visible on MetaMask
- Did I get it right? I wonder if I got it right.
- This is simply a matter of MetaMask's UI design
    - The MetaMask side is just not checking to see if the address has been given a new NFT and displaying it.
    - If you want to display it, you need to tell them there's a new one.
        - import
- ![image](https://gyazo.com/e4bf9b8250f21290e8b10b738c40c481/thumb/1000)![image](https://gyazo.com/9889a634940ed50de7c2d9c7d9c62dd9/thumb/1000)
- Can be identified by contract address and ID.
- No need to give MintRally's URL or anything, this is the fun part.
    - In other words, for the common stamp issuing services, the stamp information is only in that service, so if you want to share the information with other services, you have to use a URL or something like that.
    - On the other hand, NFTs issued by MintRally are written to a "shared memory" called the blockchain, so all you have to do is pass the address of where they are written.
    - The recipient does not need to know about MintRally.

Can it be imported into OpenSea?
- OpenSea goes in automatically without the need to import.
- [https://opensea.io/assets/matic/0x7d895ca96caa5344ec0b732c6e1defa560671e14/375](https://opensea.io/assets/matic/0x7d895ca96caa5344ec0b732c6e1defa560671e14/375)
    - ![image](https://gyazo.com/4428eba06a17f1d4d18f37b4a8b19a1b/thumb/1000)
    - There were!
- It's just hidden.
    - ![image](https://gyazo.com/5f16c77b6166955ca184313d58383540/thumb/1000)
- Displayed when unhide
    - In the Japanese UI, it's "redisplay".
- > [@nishio](https://twitter.com/nishio/status/1662311155069779968): I was told that I could see/show the NFT of the proof I attended Plurality Tokyo on OpenSea! It's just hidden by default, I just had to unhide it!
- >  [https://opensea.io/assets/matic/0x7d895ca96caa5344ec0b732c6e1defa560671e14/375](https://opensea.io/assets/matic/0x7d895ca96caa5344ec0b732c6e1defa560671e14/375)
    - ![image](https://gyazo.com/1b36ba74e71bddb2a280725fc0fcddf7/thumb/1000)
    - OpenSea is giving us Twitter badges and more.
- You can also find more information at OpenSea.
    - ![image](https://gyazo.com/25a60f338bbec888e713461845676305/thumb/1000)
    - Click on this contract address for more information.

[[Polygonscan]]
- Is there a way to see specific raw data?
- Polygonscan
- [https://polygonscan.com/address/0x7d895ca96caa5344ec0b732c6e1defa560671e14](https://polygonscan.com/address/0x7d895ca96caa5344ec0b732c6e1defa560671e14)
- ![image](https://gyazo.com/68257d2cd089618c173de2dd79cc494b/thumb/1000)
    - Transactions for that contract are visible.
- ![image](https://gyazo.com/ae8a82b7eb3880607586c02a5d1b0b2e/thumb/1000)
    - I can also see the code for the contraption.
        - I thought it was compiled into bytecode, but I can see the original code of [[Solidity]].
        - Is this being submitted to Polygonscan by the MintRally side?
            - [[fairness]] For appeal?
- There was a bytecode display and a decompile button.
    - In other words, if the source code is not submitted, only the bytecode is shared, so the person who wants to read it needs to decompile it.
    - ![image](https://gyazo.com/e9caf664bcde022769488f4e68f0adca/thumb/1000)
- [https://polygonscan.com/token/0x7d895ca96caa5344ec0b732c6e1defa560671e14?a=442](https://polygonscan.com/token/0x7d895ca96caa5344ec0b732c6e1defa560671e14?a=442)
    - Token with id=442
    - This is the NFT I received
    - ![image](https://gyazo.com/92e99d66c049ac08ed2dd6e5372a1d3c/thumb/1000)
    - From is null because I got it first.

Etherscan
- Ethereum
- [NFT I sold [https://opensea.io/ja/assets/ethereum/0x495f947276749ce646f68ac8c248420045cb7b5e/9636412166362994439967834994412630451440](https://opensea.io/ja/assets/ethereum/0x495f947276749ce646f68ac8c248420045cb7b5e/9636412166362994439967834994412630451440) 29043757878240150623063082905167200257][transaction [https://etherscan.io/tx/0x3470a91e915879cfb9d0a0f02d7e24f657b5861f43e31d4305e3d](https://etherscan.io/tx/0x3470a91e915879cfb9d0a0f02d7e24f657b5861f43e31d4305e3d) 4228cb3338b]
- ![image](https://gyazo.com/13b57ea13ed15edc41cd0bda17b8db20/thumb/1000)
- Whoa, I guess you can see the fluctuation in the amount of money in the wallets of the two people who bought and sold.
    - It's not surprising, considering how the ledger is shared with the whole world, but if you think of a wallet as a purse, there's a gap.
    - Surely if you put a million yen in here, it's like walking around with a wad of cash in your hand.
        - I'm gonna get snatched.

These are called [Block Explorer

Q: How long will it take to actually do the issuing side?
- There are two ways for participants to receive the GAS: free of charge and participants pay the GAS fee.
    - GAS fee = cost of computing resources
    - The [[beneficiary]] (= in this case, the person receiving the NFT) generally pays
    - But mismatch with the purpose of the service, which is to hand out certificates of participation to event attendees.
        - Because the recipient must have MATIC in the wallet.
- MintRally can do both.
    - As the number of participants increases, so does the cost.
    - Roughly how much per person?
        - About 5 to 10 yen

Try the Publisher with Testnet!
- Polygon's Testnet is called Mumbai
- Testnet, I thought it was something you could run locally yourself, but apparently not.
- What's the difference?
- Currency has no monetary value.
    - In that case, no one will pay for the gas to execute the transaction on the testnet...
    - I'm sure it's included in the main net GAS cost, some sort of freemium.
    - If that's the case, then what can be done on the test net must be more restricted than on the main net.

What is the use of the Certificate of Participation NFT?
- It is up to the design to determine what [[effect]] ([[Utility]]) to give the NFT.
    - This question and answer may not be nuanced enough for non-engineers.
    - I see that magnets stick to steel! What do you use this for?" "It's up to you what you use it for, but..." kind of thing.
- [[POAP]] is publishing a case study.
    - [https://poap.directory/](https://poap.directory/)
    - For example, a Zoom link that only allows people with certain tokens to join.
            - [[token gate]]
    - [[Proof of Humanity]]
        - [[SoulBound Token]]
            - This is an approach to create a non-transferable token, but [[Vitalik]] apparently said, "There is no need to create a new mechanism since all the transfer records are on the blockchain."
                - We can dig the blockchain.
                    - →[[Block Explorer]]
            - It should be an application layer, not a protocol layer
            - It is just a difference of view, whether to show the first owner or the last owner
    - POAPs do not evolve, MintRally's superiority lies in its ability to evolve based on the number of times you participate.
        - This makes it possible to "serve regulars who have visited many times.

Create an event with Testnet
- Stick to Miro where you stumbled upon it.
- Why does the MATIC gas bill show 1000000?
- If Testnet's MATIC has no currency value, doesn't a means of acquiring it exist apart from the purchase?
    - Polygon Faucet

Dune
- Services to create a Dashboard

Develop
- [https://github.com/hackdays-io/mint-rally](https://github.com/hackdays-io/mint-rally)

[[Hardhat]]
- Running the blockchain at your fingertips
- No need to include Solidity in this project since it will not be developed this time.

MintRally does not have its own data.
- It's just a chain.
- It's amazing that you can create a web app like this without having any data of your own.

Callback
- Show them another page and notify them when you're done.
- (Too common a noun to find in a search.)

[[Pinata]]
- IPFS
- Maybe media data goes here.

In the meantime, I'll try to reverse order the event groups as an easy place to start.
- fork, push, pullreq (normal flow)
    - [https://github.com/hackdays-io/mint-rally/pull/250](https://github.com/hackdays-io/mint-rally/pull/250)
- There's no such thing as running test cases on hand beforehand.
- Sometimes the title of the issue is in English and the content is in Japanese.

[[DeWork]]
- Something like Trello.
- What's the difference?

- [[HACK Token]]
- You have to give MetaMask the HACK token information first.
- ![image](https://gyazo.com/70dc4e21f0e983a84a4c16e19992503f/thumb/1000)
- I was able to do it!
    - [[Contribution tokens visualize gratitude]]

There was a shuffle time (to see other projects) in the middle of the day, but I didn't bring a headset and had difficulty hearing the conversation between the person in front of me and the person on the other side of Zoom (if you take it out of the speakers, this person's voice is doubled, if you stop the speakers, you miss the beginning of the other person's speech).

Finally, share the progress of the project and share what was good.
- I'm glad I was able to get to the point where I could send the pulls.

---
This page is auto-translated from [/nishio/Social Hack Day #50](https://scrapbox.io/nishio/Social Hack Day #50) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.