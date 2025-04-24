---
title: "Lessons from the French Government's Grand Débat"
---

Lessons from the French Government's Grand Débat: an AOI talk with [[Deger Turan]] - YouTube
[https://www.youtube.com/watch?v=MncBT0vU-6I](https://www.youtube.com/watch?v=MncBT0vU-6I)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>Summarize the presentation.
Intro:
- Presented by Deger, founder and CEO of Cerebra, which uses large-scale machine learning to show retailers how to adjust their businesses to market signals, primarily for retailers.
- In the past, we have experimented and applied similar ideas in the political and economic spheres. This talk will discuss what can be learned from that experience.

Deger's background:
- He worked with Andrew Venga and Dan Girovsky at Stanford University to develop a system for federal agencies to analyze and understand citizen feedback.
- The project aimed to improve accountability in both directions between government and citizens by utilizing natural language processing and event detection technologies to understand and visualize citizens' opinions.

Large-scale feedback collection:
- The origins of [[the massive feedback collection]] date back to the "[[grievance]] book" just before the French Revolution of 1789.
- On the initiative of the king [[Louis XVI]], a notebook was installed in the church for citizens to express their opinions. However, the most frequent opinion was for the removal of the dovecote.
- In order to understand what citizens really want, appropriate channels need to be established and feedback collected on an ongoing basis.

Three main pillars:
- Ensure transparency of data so that all participants can visualize their opinions and [[comparisons with]] others
- Establish a system of mutual accountability between central agencies and citizens
- Ensure that [[minority opinions]], which tend to be buried by random sampling, are also visualized and taken into account.

Technical structure:
- Multimodal system that integrates external and internal text sources and selective/behavioral feedback
- Create domain-specific ontologies to identify core themes for specific questions
- Vectors events from both text and action and compares relationships between events
- This identifies which events caused the conversation to rise or fall and predicts the conversation's progress

Demo:
- Introducing the [[Grand Débat]] demonstration, the French government's 2019 dialogue with citizens on a large scale.
- Analyzes 5 million text data with 2 million open-ended responses to visualize the distribution of opinions by category
- Noted that it would have been ideal to develop this into an ongoing dialogue platform rather than just a temporary data collection

What did the French Government do:
- The French government was ultimately content with collecting temporary feedback and only published a summary of the top opinions
- The project did not develop into [[a forum for ongoing dialogue with the public]] and ended up as a superficial PR response.

What did you do:
- To explore applicability in other areas, Reger looks to the retail industry
- Retailers have strong incentives to use data because they cannot ignore customer needs
- Developed a solution that integrates and analyzes review data and behavioral data to optimize inventory replenishment and sales promotion measures.

Where can we go from here:
- Large-scale citizen feedback could be used in various situations such as [[referendum]], [[citizen jury]], [[public debate]], etc.
- Five possible directions include: 1. feedback to regulators, 2. visualization of cognitive dissonance, 3. citizens exercising their rights as shareholders, 4. collective decision-making systems, and 5. direct linkage to the financial system.
- The greatest interest is in leveraging AI to increase [[transparency]], [[accountability]], and [[visibility]]. The technical barriers have been lowered, so the question is how to utilize it.

Abstractive clustering:
- For abstract clustering, statistical detection of frequent phrases and clustering by topic modeling
- It is technically possible to abstract and cluster the submitted opinions at the sentence level

Clustering:
- Clustering can be viewed as an iterative process. Clustering yields labels, classification learning is performed with those labels, and attention is paid to cases that could not be classified.
- Canned text and bot submissions can be detected in the early stages of clustering due to their high similarity
- Ultimately, adjust the clustering strategy accordingly, depending on the purpose of data utilization.

Sample Bias:
- Digital feedback collection is problematic because participants are prone to bias.
- Bias itself should be considered as important information, and it is important to systematically consider it in combination with other signals
- There is room for bias reduction depending on how feedback collection is disseminated to the public.

Transformer path:
- Transformer model classification accuracy is in the 90% range, but not 100%.
- It is essential to evaluate the performance of the classifier sequentially and use it while indicating the margin of error.

Where can we go from here:
- Specific use cases focus on mortgage and ownership issues
- Can we use data to make lending decisions that are win-win for both the bank and the borrower?
- We would like to explore an approach that uses data to match the needs of service providers and users, drawing on the knowledge of the retail industry.

The above is a summary of the main issues discussed in the presentation. The discussion focused on advances in technology for collecting and analyzing large-scale citizen feedback and the potential for using this information in various aspects of society. It can be said that the question is not so much how to solve real-world problems as it is about technical issues.
---
This page is auto-translated from [/nishio/Lessons from the French Government's Grand Débat](https://scrapbox.io/nishio/Lessons from the French Government's Grand Débat) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.