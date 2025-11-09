---
title: "Coordinating perceptually grounded categories through language: A case study for colour"
---

<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
The BBS target paper Steels & Belpaeme (2005) "Coordinating perceptually grounded categories through language: a case study for colour "The main points of the paper are compactly summarized in the following order: design (model), experiment, indicators, results, and implications.
- BBS (Behavioral and Brain Sciences) "target papers" are the central papers that are the "target" of Open Peer Commentary. Papers on highly important and controversial topics are selected, and a series of short comments from experts (approximately 20 to 40 comments) are published, followed by the author's overall reply at the end.

What is the paper about?
- Using color as the subject matter, we examine "how perceptual categories possessed by individuals are sufficiently shared in a group to be communicated in language. Computational models are created for each candidate position (innate/empiricist/culturalist) and compared to see which one is sufficient for sharing. Published in Behavioral and Brain Sciences 28(4), pp. 469-489 (with open peer commentary). ([PubMed](https://pubmed.ncbi.nlm.nih.gov/16209771/?utm_source=chatgpt.com), [Cambridge University Press & Assessment [https://www.](https://www.) cambridge.org/core/journals/behavioral-and-brain-sciences/article/coordinating-perceptually-grounded-categories-through-language-a -case-study-for-colour/423FB60CE8E6BFB0ADC23FFD48FBD4F0?utm_source=chatgpt.com])

Model design (3 systems)
- [Nativism: Genetic evolutionary model. Examines whether individuals with color categories (prototype groups) as "color genes" converge to sharing through generational change. ([langev.com](https://langev.com/pdf/steels_BBS_color.pdf))
    - [[empiricism]] (Empiricism): individual learning model, where inputs in CIE L*a*b* space are clustered (prototype + fuzzy boundary) in an adaptive network of RBF systems, each of which independently acquires categories. ([langev.com](https://langev.com/pdf/steels_BBS_color.pdf))
- [Culturalism: [[Language Games]] combine category formation and word adoption in a bidirectional manner (reinforcing successfully transferred categories and words). This allows for simultaneous intra-individual learning and word alignment. ([langev.com](https://langev.com/pdf/steels_BBS_color.pdf))

Experimental Tasks and Data
- Discrimination game: The listener identifies the object to which the speaker refers in the presentation set.
- Language game (naming): communicated using category ↔ word correspondence. Weight update with success/failure. ([langev.com](https://langev.com/pdf/steels_BBS_color.pdf))
- Environment:
    1. Munsell 1269 color spectral reflection (380-800nm) → XYZ → L*a*b* conversion (reflects human color vision model).
    2. "Realistic statistical distribution" data sampled from 25,000 pixels each from natural and urban landscapes, random Munsell for comparison.([rangev.com](https://langev.com/pdf/steels_BBS_color.pdf))

indicator
- Discriminative success
- Communicative success
- Consistency is quantified by category variance (category variance; the deviation of categories among individuals) and inter-population variance (inter-population variance). ([langev.com](https://langev.com/pdf/steels_BBS_color.pdf))

Main Results (Conclusions)
1. individual learning alone "makes each individual better, but sharing is not enough"
    - Discrimination success reaches almost 100%, but categories are not aligned among individuals (category variance remains). = Solutions are not uniquely determined for the same environment and the same physiology. ([langev.com](https://langev.com/pdf/steels_BBS_color.pdf))
    - Individual learning alone does not generate a common language system.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
2. genetic evolution aligns within a population, but "slowly"
    - Over generations, categories become more consistent (dispersal → low) within the population. However, timescales for adaptation are long (multi-generational). ([langev.com](https://langev.com/pdf/steels_BBS_color.pdf))
3. fast and highly accurate alignment when there is cultural interaction through language
    - When category formation and word adoption are combined in a language game, discrimination and transfer success increases simultaneously (transfer success goes up to ≈90%). = Causal influence of language on category acquisition. ([langev.com](https://langev.com/pdf/steels_BBS_color.pdf))
4. environmental statistics alone are not enough to share
    - Actual nature/urban statistics tend to increase the degree of sharing, but they do not lead to sufficient consistency by themselves. = Three factors are needed: physical (physiology) x environmental statistics x language negotiation. ([langev.com](https://langev.com/pdf/steels_BBS_color.pdf))

Implications (symbolic foundations/universal vs. relative)
- For the chicken-and-egg problem (category first or word first), we present a dynamic explanation that bi-directional binding (category ⇄ word) drives alignment. ([langev.com](https://langev.com/pdf/steels_BBS_color.pdf))
- Although universalism (physiological and environmental constraints) alone produces certain trends, linguistic interaction decisively boosts the degree of sharing. However, color is a special domain, and BBS commenters have presented criticisms such as "overemphasizing the influence of language" (e.g., Wachtler et al., Harnad). ([Artificial Intelligence Lab Brussels](https://ai.vub.ac.be/sites/default/files/steels-05e.pdf?utm_source=chatgpt.com), [eprints.soton. ac.uk](https://eprints.soton.ac.uk/260503/?utm_source=chatgpt.com))

Summary (one line)
- Social sharing of perceptual categories is made not only by body and environmental statistics, but also by the dynamics of linguistic interactions (cultural negotiation) -- a paper that shows this computationally and experimentally in the color case. ([langev.com](https://langev.com/pdf/steels_BBS_color.pdf))

What does "language games interactively combine category formation and word adoption" mean?<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
In short** "category learning" and "vocabulary learning" are to be updated simultaneously with the success or failure of the same interaction (language game).
Instead of one-way (category -> word pasting only), the way a word is used pushes category boundaries, and at the same time the way the category is held determines the selection and invention of words**--this mutual traction is called "two-way coupling " is called "two-way coupling.

1) What happens in one language game (minimum steps)
1. situational presentation: multiple color chips (context) + speaker chooses one "topic".
2. conceptualization (category side → word):
    - The speaker selects a discriminative category from his/her perceptual category group (if not, the category is split/adjusted to create one).
    - If there is an existing word in the category, select it. If not, invent a word and assign it.
3. interpretation (word → category side):
    - The listener explores the word → (his/her) candidate category, and then applies and points to what can be discriminated in context.
    - If it fails, adjust/new your own category, and word-category merging is also updated by adopting/weakening it.
4. update (bidirectional):
    - Success: strengthens the union of its word ⇄ category, suppresses competing words and categories (side suppression). Category center and spread are also fine-tuned.
    - Failure:
        - Repair on the lexical side: adopt new words, weaken/remove erroneous word-category combinations.
        - Repair on the category side: boundary transfer, division/annexation, updating the prototype (to make it discriminable).
The key point is to update both "word combination weights" and "category forms (prototypes and boundaries)" with the same error signal of success or failure.

2) What is "bidirectional" (direction of causation)?
- Language → Category: The pressure to get the word through successfully pushes (subdivides and moves) category boundaries to the necessary granularity.
- Category → Language: the category structure at hand determines which words are chosen / new words are invented.

3) Formal image (simplified)
- Strength of lexical binding $\sigma(w,c)$:
    - Success: $\sigma \leftarrow \sigma + \alpha(1-\sigma)$ (enhanced)
    - Failure: $\sigma \leftarrow (1-\beta)\sigma$ (weakened)
- Category prototype $p_c$ and spread $\tau_c$:
    - On success, fine-tuning toward the topic sample; on failure, firing repairs such as splitting/shifting boundaries, etc.
(*Specific expressions vary by implementation, but both are driven by the same success/failure.)

4) Why it works (Consequences)
- Because discrimination (category-side objective) and transfer success (lexical-side objective) are simultaneously optimized in a single iterative game,
    - Within individuals, words and categories mesh,
    - Within a group, vocabulary and boundaries converge (convention formation) through interaction.

5) Mini Example
- Initial: "red" is too wide and fails to pick up the neighboring vermilion color as well.
- The listener dichotomizes the category (red/red) and the speaker invents "vermillion" OR narrows the range of "red".
- Subsequent successes strengthen and stabilize "red" ⇄ red and "vermillion" ⇄ vermillion.
In short, the design updates both sides of a word⇄category with the success or failure of a single exchange - this is "binding in both directions".


---
This page is auto-translated from [/nishio/Coordinating perceptually grounded categories through language: A case study for colour](https://scrapbox.io/nishio/Coordinating perceptually grounded categories through language: A case study for colour) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.