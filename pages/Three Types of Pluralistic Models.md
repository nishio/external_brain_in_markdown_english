---
title: "Three Types of Pluralistic Models"
---

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
Overton multiway model
- Definition: A model that presents all reasonably plausible answers (within the Overton window) to a query.
- Objective: To enable users to look over and ponder multiple views.
- Example implementation:.
    - Diversity promotion prompt + multiple sampling to create a set of responses and return a summary.
    - Prepare a list of unreasonable responses and automatically determine what not to include.
- Main applications: advice generation, evidence enumeration, multi-method presentation of mathematical proofs, etc.
- Challenges: Drawing the line for the Overton window is subjective/high cost, and the risk that both sides of the argument will create a false balance.

Steerable multiway model
- Definition: Prompts and settings can be "steered" to a predefined attribute or perspective a (culture, philosophy, personal profile, etc.) and generate responses consistent with that perspective.
- Objective: To provide flexible and high-fidelity simulation of personalization and different positions.
- Example implementation:.
    - Conditional input of user-embedded/value-view tokens.
    - Added a module to mimic specific group responses in Few-shot.
- Main applications: writing assistance, creative ideation, dialogue therapy, social simulation.
- Challenges: setting boundaries for acceptable attributes, stereotyping when attributes are too coarse, handling of intersecting attributes (intersectionality).

Distributional Multiple Model / [[Distributive Multiplicity]].
- Definition: A model designed so that the distribution of responses in a population G matches (is calibrated to) the distribution of responses in the model.
- Purpose: To reproduce "how a group would respond" probabilities in opinion polls and cultural studies for use in simulation and analysis.
- Example implementation:.
    - Additional pre-training with target population data to evaluate distributional consistency with KL/Jensen-Shannon distance, etc.
    - Fine-tuning using survey response data as a teacher signal.
- Primary applications: agent swarm simulation, survey design pilots, cultural comparison studies.
- Challenges: reference population selection and data collection, amplification of frequent but harmful opinions, balancing distributive pluralism and Overton/Steerable.

---
This page is auto-translated from [/nishio/多元的モデルの3類型](https://scrapbox.io/nishio/多元的モデルの3類型) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.