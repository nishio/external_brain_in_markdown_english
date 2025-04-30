---
title: "Test Driven in the AI Agent Era"
---

from  [[Diary 2025-04-28]]
Test Driven in the AI Agent Era

- [[Digital Democracy 2030]]  [Slack](https://w1740803485-clv347541.slack.com/archives/C08F7JZPD63/p1745738002699639)
NISHIO Hirokazu
I let my own service with E2E testing tinker around to use my Devin's soon-to-expire credits, but it was amazing to see him accomplish things that people don't want to do, like updating Firebase and React (small scale).
I have a growing feeling that it is still important to maintain tests so that I can easily throw tasks to AI, and I want to start with small tests and put them into CI.
I think it would be better to position the test not as a way to reduce speed and improve quality, but as a way to quickly notice mistakes when speed is increased, and make it a rule that the test results can be merged without checking them.
So, it's like there are high-quality tests maintained by humans and AI-generated tests based on them.
I wonder if it would be possible to notify Slack which tests are failing often or when a high quality test fails.

Takahiro Yasuno
Using AI generated tests to make Go/NoGo decisions is a totally different paradigm from conventional testing, maximizing return on investment without aiming for all green.

> [takahiroanno](https://x.com/takahiroanno/status/1916436848639119742) Evaluating high quality human-written tests, AI-generated tests, [[LLM E2E test]] signals by [[Browser-use]], etc., while mixing them. Evaluating mixed signals, without aiming for All Green (LLM E2E test is probabilistic to begin with), there could be a more risk-taking and cost-effective flow to make a Go/NoGo decision...?
- [[Generation test]]
- [[Probabilistic test]]

> [nishio](https://x.com/nishio/status/1916666642475745540) I think there is going to be a shift from the traditional concept of test-driven AI agents in the age of AI agents, where all tests are expected to succeed, to [[ensemble]] a bunch of [[probabilistic discriminators]] to make them stronger. I think there is going to be a shift equivalent to the paradigm shift from rule-based to machine learning with if statements.
    - [[From if statements to machine learning]]



relevance
- [[Automated Unit Test Improvement using Large Language Models at Meta]]
- <img src='https://scrapbox.io/api/pages/nishio-en/DR/icon' alt='DR.icon' height="19.5"/>[https://chatgpt.com/share/68102ec2-7724-8011-8137-ad28d0f67b61](https://chatgpt.com/share/68102ec2-7724-8011-8137-ad28d0f67b61)

---
This page is auto-translated from [/nishio/AIエージェント時代のテストドリブン](https://scrapbox.io/nishio/AIエージェント時代のテストドリブン) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.