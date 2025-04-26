---
title: "Automated Unit Test Improvement using Large Language Models at Meta"
---

[https://arxiv.org/abs/2402.09171](https://arxiv.org/abs/2402.09171)
<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
## Summary of paper (super-summary)
TestGen-LLM], which Meta runs in-house, is a tool that uses LLMs to ### "improve"
 existing Kotlin unit tests.
The system automatically verifies "whether the generated tests really add value," and only those that pass are presented to the engineer as pull requests.

# Mechanism - Assured Offline LLMSE
.
1.### Candidate Generation
.
- Multiple prompts were thrown to two different in-house LLMs (referred to as LLM-1/LLM-2 in the paper) to generate a large number of test cases to be added to existing test classes.
2.### 3-stage filtering gives guarantee
.
    1. Builds → Pass through the compilation?
    - 2.Passes → 5 consecutive stable passes (flake prevention)
    - 3.Improves→ Has instruction coverage or branch coverage increased?
        - Only tests that pass are considered "improved" and a diff with documentation is automatically generated.
- 3.Human Review.
    - Diffs that pass through the filter are placed in normal code review, and only final approval is done by a human.

# introduction and evaluation results
.
- Internal Benchmarks (Instagram Reels & Stories)
    - 75% of generated tests pass build, 57% pass stable, 25% increase coverage
- Test-a-thon①（Instagram, 2023-11）
    - 16 of 17 diffs are in production. Median line coverage +2.5 lines/test.
- Test-a-thon②（Instagram+Facebook, 2023-12）
    - Improved 11.5% of applied classes. Engineers accepted 73 % of the proposals.

# what's new
- "improve" instead of "generate".
    - To add corner-cases to existing tests, so they can be easily merged into the actual product.
- LLM Halcination "engineered" containment.
    - Guaranteed code generation by dropping failures, flakes, and lack of coverage in stages.
- Reported adoption on an industrial scale.
    - Claimed to be the first public case of LLM generation testing being deployed in production to a large code base (Instagram/Facebook).

# technical and operational lessons learned
.
- In areas where there is no test oracle, the "if it fails, throw it away" strategy is effective.
    - Prioritizing regression prevention over bug detection, all first-time failure tests are discarded.
- Flake elimination is mandatory.
    - The simple check of five consecutive passes was also very effective, and CI stability was introduced without any disruption.
- LLM & prompt for "ensemble".
    - Even for the same LLM, temperature and system prompt differences are executed in parallel to ensure a variety of candidates.
- Translate coverage metrics into DevEx.
    - Review speed is improved when diff automatically attaches "how many lines increased" and "uncovered branches taken".

# Limitations and future challenges
.
- Expanding coverage of Oracle absenteeism.
    - Currently, it is assumed that "pass = correct". Specification-based assertion generation is a future theme.
- Deeper Semantic Assurance.
    - In addition to coverage, we would like to incorporate mutation scoring and property-based testing.
- other languages, mono-repo integration.
    - Verification of application to service layers other than Kotlin (Android) and multilingual environments such as C++ has not yet been started.

## Brief Impressions
The biggest contribution to the project was to demonstrate that the preconceived notion that "having LLMs write tests will break them" can be put into practice if a "guaranteed pipeline" is inserted.
In particular, the three-stage filter ### Build→Pass→Improve
 is a design pattern that can be easily applied to smaller projects.



relevance
- [try using cover-agent](https://zenn.dev/mizchi/scraps/2b68746cb38079#comment-60340d7fe6874b)
    - [[cover-agent]] / [[mizchi]]

---
This page is auto-translated from [/nishio/Automated Unit Test Improvement using Large Language Models at Meta](https://scrapbox.io/nishio/Automated Unit Test Improvement using Large Language Models at Meta) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.