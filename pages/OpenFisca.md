---
title: "OpenFisca"
---

[Write rules as code - OpenFisca](https://openfisca.org/en/)

[About OpenFisca | OpenFisca-Japan Docs](https://project-inclusive.github.io/OpenFisca-Japan/about_openfisca.html)
> OpenFisca is a French OSS that allows you to describe social systems as software code (Rule as Code).

[/tkgshn/OpenFisca](https://scrapbox.io/tkgshn/OpenFisca)

[What is OpenFisca? | Salsa Digital](https://salsa.digital/insights/what-is-openfisca)
- case studies of various countries

## LexImpact
- [/tkgshn/LaxImpact](https://scrapbox.io/tkgshn/LaxImpact)
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>summary
[[LexImpact]] is a social and fiscal simulator operated by the French National Assembly that calculates and visualizes the impact of policy changes based on OpenFisca. Citizens and legislators can enter scenarios to simulate the impact of changes in various parameters of the tax and social security systems (e.g. minimum wage, various social insurance premiums, etc.).
- [Using AI to update OpenFisca parameters – update_openfisca_with_ai](https://documentation.leximpact.dev/ia/explication-en.html)

### Key Features
.
- Simulation function.
    - The effects of policy changes (e.g., wage revisions or tax rate changes) are quickly calculated and the results presented graphically. This assists in policy discussions and decision-making within Congress.

- Parameter management and automatic updates.
    - OpenFisca handles a large number of fiscal parameters, and LexImpact has introduced a mechanism to update these based on the latest legal amendments. Specifically, for each parameter, information such as "value," "start date of application," and "legal basis" is recorded, streamlining mass updates that would be difficult to perform manually.

- AI (large scale language models).
    - LexImpact introduces a system that automatically extracts the necessary numerical values, dates, and legal reference information from the legal text using LLM (Large Language Model).
    - Guided LLM approach: Combine the legal text with parameter descriptions and ask the LLM to extract accurate information.
    - Intelligent Agent Approach: LLMs use web search and text retrieval tools to supplement missing reference information.

### Significance and background
.
- Expediting policy evaluation.
    - The ability to simulate the impact of system changes prior to their actual implementation streamlines the policy-making and parliamentary verification process.
- Concrete example of [[Rules as Code]]
    - As an example of an OpenFisca implementation that encodes laws and regulations, LexImpact works with AI technology and represents a step away from traditional manual updating to automation.

As described above, LexImpact plays an important role in policy simulation and automatic parameter updating as an advanced tool that realizes OpenFisca's "code the law" concept.
---
This page is auto-translated from [/nishio/OpenFisca](https://scrapbox.io/nishio/OpenFisca) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.