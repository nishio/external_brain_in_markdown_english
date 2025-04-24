---
title: "TTTC:empty vocabulary"
---

Unresolved issues in [Talk to the City

I experienced this around 2024-09-11.
    - I was in the middle of trying [[Using TTTC with Azure OpenAI]] and rewriting the code, so I thought it was only happening in my environment.
2024-09-16
- There was a mention from [[blu3mo]] on 9/16 in [[proj-broadlistening]] ([link](https://cfj.slack.com/archives/C07JHK1M58A/p1726470787750939)) that it occurs in environments other than my own. [[link ]], and that it also occurs outside of my environment.
2024-09-28
    - [[TTTC: Morphological Analysis]]
    - I think this is a legitimate solution.
    - However, it is a mystery when it occurs in the first place.
2024-10-29
- As of 2024-10-29, the source code for the version [[Nittele NEWS x 2024 House of Representatives Election x Broad Listening]] is publicly available, so it's easier to use that.

Notes on what we know

> ValueError: empty vocabulary; perhaps the documents only contain stop words
Occurs here in clustering
:

```
    _, __ = topic_model.fit_transform(docs, embeddings=embeddings)
```


(9/11) This line itself is necessary although it appears that the return value is not used.
- > Talk to the City's "I thought you weren't using BERTopic? If you comment out `_, __ = topic_model.fit_transform(docs, embeddings=embeddings)`, you will see the following `result = topic_model.get_document_info Call 'fit' with appropriate arguments before using this estimator. `, so I found out that it is used, but only the internal state of the model is updated without using the return value (if it were, there would be no need to write `_, __ =`).

(9/11) I tried to follow it up with PDB, but gave up on the way.
:

```
409             else:
410                  # Extract topics by calculating c-TF-IDF
411  ->             self._extract_topics(documents, embeddings=embeddings)
```


:

```
(Pdb) self._c_tf_idf(documents_per_topic)
*** ValueError: empty vocabulary; perhaps the documents only contain stop words
```


:

```
3485            if partial_fit:
3486                X = self.vectorizer_model.partial_fit(documents).update_bow(documents)
3487 ->         elif fit:
3488                self.vectorizer_model.fit(documents)
3489                X = self.vectorizer_model.transform(documents)
3490            else:
3491                X = self.vectorizer_model.transform(documents)

(Pdb) self.vectorizer_model.fit(documents)
*** ValueError: empty vocabulary; perhaps the documents only contain stop words
```


Well, vectorizer_model is below, so I'm pretty sure CountVectorizer is giving an error.
- [CountVectorizer — scikit-learn 1.5.2 documentation](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.CountVectorizer.html)
clustering.py

```
   CountVectorizer = import_module(
       'sklearn.feature_extraction.text').CountVectorizer
   ...
   vectorizer_model = CountVectorizer(stop_words=stop)
   
   topic_model = BERTopic(
       umap_model=umap_model,
       hdbscan_model=hdbscan_model,
       vectorizer_model=vectorizer_model,
       verbose=True,
   )
```


The version of sklearn.__version__ on my end was 1.3.1

If you look at the features used in tokenizer.get_feature_names_out and so on, of course Japanese is not divided into words
- By default `CountVectorizer(... , token_pattern='(?u)\\b\\w\w\w+\w\b')`, so I think it's obvious.
- I rather don't know why they were working on this at the time of the Anno gubernatorial election.
    - In retrospect, my comment on 6/9:.
        - > In my experiment (partly because I wanted to show the results to the world), I extracted in English, clustered in English, and translated the results into Japanese, but there was a problem with the quality of the translation. Since the target population this time is Japanese, I think it would be better to extract in Japanese, cluster the results in Japanese, and do no translation. In that case, since the bag of words is done in the clustering part, morphological analysis or keyword extraction is necessary for Japanese.
        - After this, on 6/11, there was a report that "I tried it with a Japanese prompt and it worked", so I decided that if it works, that's good enough for me because I don't have much time.
        - 9/16 Comments
            - > The main processing part of TTTC was not implemented with Japanese in mind, and the stop word was in English, and morphological analysis was not done. I was told that either I need to translate the results into Japanese or add morphological analysis so that the Japanese language will be understood.
            - >  Behavior that matches my understanding better with the stuck status quo.
- Is there a mechanism in some versions to fall back to splitting by letter when word splitting is not possible?
    - Now (9/18)[CountVectorizer - scikit-learn 1.5.2 documentation [https://scikit-learn.org/stable/modules/generated/sklearn.](https://scikit-learn.org/stable/modules/generated/sklearn.) Feature_extraction.text.CountVectorizer.html#sklearn.feature_extraction.text.CountVectorizer.get_feature_names_out]. analyzer='word' to 'char', it seems to work.
        - Aside from the question of whether Bag of Chars is really a good idea.

Posted 9/16:.
- I thought it was Azure related when it happened on 9/11, so I gave up on a serious solution because I was too lazy to follow the library dependencies.
    - Instead, we modified the prompts to add English translations to the end of the extracted Japanese data for workaround.
        - > Please include a translation into English at the end.
    - I'm assuming that the fact that you can work around it that way means that it's probably a tokenization issue with the Japanese text.

9/18
- My current thought is that `analyzer='char'` would work? I think.
- Essentially, I think we should do a proper [[morphological analysis]].
    - CountVectorizer can be overridden by passing a function, so use that method.

---
This page is auto-translated from [/nishio/TTTC:empty vocabulary](https://scrapbox.io/nishio/TTTC:empty vocabulary) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.