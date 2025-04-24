---
title: "Re-voteable but not viewable."
---

A system that does not allow election authorities to see the results of a particular individual's vote and [[allows for]] re-voting.
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>A mechanism to meet that requirement is certainly an interesting and important issue. We will discuss some ideas and existing methods on how to preserve the integrity of elections, protect voter privacy, and allow for re-voting:
- Using [[quasi-homomorphic ciphers]]:.
    - Votes are submitted and tabulated in encrypted form
    - Election authorities can tabulate votes in encrypted form without seeing individual ballots
    - In case of re-voting, logic can be implemented to make only the latest vote valid
- [[Zero Knowledge Proof]]:.
    - Voters can prove the legitimacy of their vote, but will not reveal the details of their vote.
    - Provides proof of invalidation of previous ballot at the time of re-voting
- [[blind signature]]:.
    - Election officials certify voter eligibility without looking at the ballot content.
    - New signatures are issued and old signatures are invalidated when re-voting.
- [[MIX NETWORK]]:.
    - Shuffle votes across multiple servers so that the original order is lost
    - When re-voting, new ballots are put into the system and old ballots are excluded
- [[secret-distribution]] method:.
    - Split the ballot into several fragments and keep them with different authorities
    - Reconstruction requires the cooperation of several authorities, which alone cannot know the details of the vote
    - [[blockchain]] Technology:.
    - Votes are encrypted and recorded on the blockchain
    - When re-voting, the new transaction nullifies the old vote.

Implementation issues:.
- Mechanisms to ensure that old ballots are invalidated and new ballots are reflected in the re-vote process
- How to detect re-voting by the same person while preserving the anonymity of the vote
- Design an interface that reduces overall system complexity and is easy for voters and election administrators to understand and use.

By combining these technologies, it may be possible to create a system that allows election authorities to vote again without having to see individual ballots. However, it is important to strike a balance between system complexity, security, and ease of use. Legal and ethical considerations would also need to be taken into account.

relevance
- [[Survey on Remote Electronic Voting]]

---
This page is auto-translated from [/nishio/再投票可能だが見ることはできない](https://scrapbox.io/nishio/再投票可能だが見ることはできない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.