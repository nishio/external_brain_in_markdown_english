---
title: "NFT is only a rewriting authority for global variables"
---


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>As a follow-up sentence, he is about to write, "The fraud of assigning this global variable and describing oneself as having rewriting authority as 'NFT ownership' has led to an overvaluation of value." Fact Check.

<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
Summary: The purpose is close, but the wording could be slightly adjusted to be more accurate.
- Ethereum is a "world computer" in which all nodes agree on a "global/singleton state" and EVM determines the state transitions. This metaphor is apt. ([ethereum.org](https://ethereum.org/en/developers/docs/intro-to-ethereum/?utm_source=chatgpt.com), [Alchemy [https://www.alchemy.com/](https://www.alchemy.com/) docs/what-is-ethereum?utm_source=chatgpt.com])
- The NFT is recorded in the ERC-721 as an entry such as "tokenId → owner address" and is designed to be "authorized" so that only the owner or an authorized operator can perform the transfer (i.e., the status is not rewritten arbitrarily but is updated via the contract logic). The state is updated via the contract's logic). ([Ethereum Improvement Proposals](https://eips.ethereum.org/EIPS/eip-721?utm_source=chatgpt.com), [OpenZeppelin Docs [https://docs.](https://docs.) openzeppelin.com/contracts/4.x/api/token/ERC721?utm_source=chatgpt.com])
- Note that metadata is often designed to allow the issuing party to update it (e.g., ERC-4906). It is not "owner = any rewrite rights." ([Ethereum Improvement Proposals](https://eips.ethereum.org/EIPS/eip-4906?utm_source=chatgpt.com))
- On the market side, there is widespread evidence of price fixing, including wash trades. The latest crypto-crime report also organizes market manipulation, including NFTs. ([Chainalysis](https://www.chainalysis.com/blog/crypto-market-manipulation-wash-trading-pump-and-dump-2025/?utm_source=chatgpt.com))
- There have been several cases (Mutant Ape Planet and others) that have resulted in convictions and prosecutions for ragpicking and other fraud. ([Department of Justice [https://www.justice.gov/usao-edny/pr/nonfungible-token-nft-developer-pleads-guilty-international-scheme-defraud-nft?utm_](https://www.justice.gov/usao-edny/pr/nonfungible-token-nft-developer-pleads-guilty-international-scheme-defraud-nft?utm_) source=chatgpt.com])
- In addition, cases have been pointed out where the purchase of NFTs does not = the acquisition of legal rights such as copyrights, but misleading explanations of this point lead to an overestimation of value (Market Covenants and Legal Literature). ([OpenSea](https://opensea.io/tos?utm_source=chatgpt.com), [Oxford Academic [https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/](https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/) eaae018/7746479?utm_source=chatgpt.com])

How to write a recommendation (example)
In this "worldwide shared state," NFTs are represented by the entry tokenId→owner, and the owner (or approver) can approve the transfer. On the other hand, there have been a series of scams that overstate the value through manipulations such as misleading explanations of rights content over substance and wash trades." ([Ethereum Improvement Proposals](https://eips.ethereum.org/EIPS/eip-721?utm_source=chatgpt.com), [Chainalysis [https://www.chainalysis.](https://www.chainalysis.) com/blog/crypto-market-manipulation-wash-trading-pump-and-dump-2025/?utm_source=chatgpt.com], [OpenSea [https://opensea.io/tos?utm_](https://opensea.io/tos?utm_) source=chatgpt.com])
Point:
- The term "rewriting authority" is accurate to the extent of "authority to approve transfers."
- Showing that "fraud" is broken down into **specific modus operandi (wash trade/rag pull/misguided entitlement)** is factual while avoiding over-generalization. ([Chainalysis](https://www.chainalysis.com/blog/crypto-market-manipulation-wash-trading-pump-and-dump-2025/?utm_source=chatgpt.com), [Department of Justice [https://www.justice.gov/usao-edny/pr/nonfungible-token-nft-developer-pleads-guilty-international-scheme-defraud-nft?utm_source](https://www.justice.gov/usao-edny/pr/nonfungible-token-nft-developer-pleads-guilty-international-scheme-defraud-nft?utm_source) =chatgpt.com], [OpenSea](https://opensea.io/tos?utm_source=chatgpt.com))
This tone can clarify the criticism without overstepping the technical or legal bounds.


---
This page is auto-translated from [/nishio/NFTはグローバル変数の書き換え権限に過ぎない](https://scrapbox.io/nishio/NFTはグローバル変数の書き換え権限に過ぎない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.