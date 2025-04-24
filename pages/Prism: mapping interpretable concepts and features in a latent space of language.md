---
title: "Prism: mapping interpretable concepts and features in a latent space of language"
---

[Prism: mapping interpretable concepts and features in a latent space of language | thesephist.com](https://thesephist.com/posts/prism/)

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
This research proposes a method to visualize and manipulate the latent space of natural language models as a set of human-understandable "features. This reveals a new interface that enables more direct and precise semantic manipulation (conversion to a specific topic or style, emphasis or suppression of specific concepts) from the mere generation of text output.

In the future, these "latent direction" operations could become more intuitive and flexible editing features in writing support and knowledge exploration. For example, complex style elements and topic tendencies in a text might be controlled by a "knob"-like GUI, allowing the user to directly stretch and loosen "context" and "meaning. Also, the concept of information manipulation could be further extended to embedded spaces in other fields (images, audio, video), enabling creative media editing and advanced document management.

In short, this research opens new doors for humans to directly grasp and control the representations inside AI models, and could be the foundation for the next generation of interactive information manipulation and generation tools.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Explain the results and methods that have been achieved at this point in this paper.

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
The achievement of this paper is the automatic extraction of a large number of human-understandable "feature directions" (interpretive conceptual axes) within the latent space of large-scale language models (especially sentence embedding models), and their use to enable semantic and stylistic editing of texts. Specifically, the following methods and results are presented.

### Sparse Autoencoding ([[Sparse Autoencoder]]: SAE) application
:
Using sentence embedding as input, we have developed a method to extract a large number of features (directions) in the embedding space with a sparse representation. This method produces tens of thousands of human-interpretable features from an embedding space of approximately 512 to 2048 dimensions.

### Automatic feature labeling and confidence assignment
:
We show how to automatically describe and label feature directions extracted using GPT-4 based on text examples, and automatically score how accurately the description represents the feature. This enables reliability evaluation for a large number of features without human intervention.

### Text semantic editing function:
Semantic editing is achieved by using the obtained feature directions to control the style and content of the text by simple vector operations (addition to feature directions, etc.) in the embedding space, and then redecoding the result from the embedding to the text. The "feature gradients" method further improves the accuracy of the editing.

Overall, this research establishes a fundamental method for advanced visualization, interpretation, and editing of model internal representations by combining "sparse feature decomposition models" and "automatic explanation and evaluation using large-scale language models.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Suppose we are given a short list of about 10,000 free-texts. What would be possible by applying this method?

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
Applying this technique to a free-response short form of 10,000 responses would allow for the following

### Explicit potential features:
By vectorizing responses with an embedded model and analyzing them with a sparse autoencoder (SAE), a large number of human-understandable features (topics, writing style, expression patterns, specific keyword trends, etc.) can be automatically extracted and visualized.

### Highly accurate understanding and classification of text groups:
In the past, clustering was limited to finding vague "somewhat similar responses," but now that interpretable feature directions are available, it is possible to clarify why responses are similar to each other and which elements characterize the responses, enabling more precise categorization and extraction of important features.

### Editing and correction in specific direction:
Using the extracted feature directions, it will also be possible to make specific semantic modifications to the response text, such as "slightly more formal direction" or "question-like nuance. This is a new means of operation that allows fine-tuning and unification of semantic units while overlooking the entire response.

In summary, by using this method for the 10,000 open-ended responses, it will be possible to more precisely understand and analyze the group of responses and identify potential conceptual and stylistic features, while utilizing them to semantically organize and edit the text.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
> In the past, clustering was limited to finding vague "somewhat similar responses," but by obtaining interpretable feature directions, it is possible to clarify why responses are similar to each other and which elements characterize the responses, enabling more precise categorization and extraction of important features.
This place looks very interesting.
On the other hand, the real data is "almost a homogeneous high-dimensional mass" according to observations, with only 10% of the total data forming dense clusters. What do you think of that situation?

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>In such a "mostly homogeneous, with only some (about 10%) forming distinct clusters" situation, the following perspectives are possible.

### Homogeneity check by feature extraction:
- Even if feature extraction by sparse autoencoder is performed, it is highly likely that in the remaining 90% "homogeneous mass" portion, it is difficult to see a clear feature direction or only "general and commonplace" features with vague explanations are found. In other words, the fact that "no outstanding features are found" using this method is itself a proof of the homogeneity of the data.

### Focus on 10% cluster section:
- On the other hand, if we focus on the approximately 10% that form dense clusters, a relatively clear feature direction may emerge in that area. By analyzing those feature directions, we can obtain specific and interpretable explanations as to why they are clustered only there and what makes them different from the other 90%, and thus understand the cluster formation factors more precisely.

### Reexamination of the data/model side:
- Data that continue to have a homogeneous spread suggests that perhaps the original data collection method or representation model may not have picked up enough diversity. In this case, the feature extraction results provide an opportunity to consider collecting a data set that contains more diverse information or switching to a higher-performance embedding model.

In general, uniform data distributions may appear to remain uniform when this method is applied. However, that does not imply a failure of "unresolvability," but rather could be a means of reaffirming, from a feature direction perspective, that "this data does in fact have such homogeneity. And with respect to cluster areas that are even partially specialized, it would act as a clue to a deeper understanding than before.

---
This page is auto-translated from [/nishio/Prism: mapping interpretable concepts and features in a latent space of language](https://scrapbox.io/nishio/Prism: mapping interpretable concepts and features in a latent space of language) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.