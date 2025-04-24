---
title: "Talk to the City UI Japanese language"
---

[[Talk to the City]] has a basic UI in English, and as for the other languages, they are translated in GPT 3.5 along with the content.
This is what it looks like in the source code, look at the language specification in the configuration file and translate it.
translation.py

```
UI_copy = ["Argument", "Original comment", "Representative arguments",
           "Open full-screen map", "Back to report", "Hide labels", "Show labels",
           "Show filters", "Hide filters", "Min. votes", "Consensus",
           "Showing", "arguments", "Reset zoom", "Click anywhere on the map to close this",
           "Click on the dot for details",
           "agree", "disagree", "Language", "English", "arguments", "of total",
           "Overview", "Cluster analysis", "Representative comments", "Introduction",
           "Clusters", "Appendix", "This report was generated using an AI pipeline that consists of the following steps",
           "Step", "extraction", "show code", "hide code", "show prompt", "hide prompt", "embedding",
           "clustering", "labelling", "takeaways", "overview"]
```


I think this method is a great cut-and-dried multilingual support, because you can translate any language without preparing translation data, just by writing it in the configuration file (I praise it).
However, in a situation where Japanese speakers are in the majority and there are people who are allergic to English, if the default screen is in English and you say, "You can also switch to Japanese! on the default English screen, they will probably leave the site without switching.

So I want to make it the "Japanese default".
The former seems to be easier than the latter, and the former seems to be better for our needs, so that's what we're going to do.

In the meantime, I've created English-Japanese data.
:

```
{'Argument': 'Discussion',.
 'Original comment': 'Original comment',.
 'Representative arguments': 'Representative arguments',.
 'Open full-screen map': 'Open full-screen map',.
 'Back to report': 'Back to report',.
 'Hide labels': 'Hide labels',.
 'Show labels': 'Show labels',.
 'Show filters': 'Show filters',.
 'Hide filters': 'Hide filters',.
 'Min. votes': 'Minimum number of votes',.
 'Consensus': 'consensus',.
 'Showing': 'Showing',.
 'arguments': 'discussion',.
 'Reset zoom': 'Reset zoom',.
 'Click anywhere on the map to close this': 'Click anywhere on the map to close this message',.
 'Click on the dot for details': 'Click on the dot for details',.
 'agree': 'I agree',.
 'disagree': 'disagree',.
 'Language': 'Language',.
 'English': 'English',.
 'of total': 'total',.
 'Overview': 'Overview',.
 'Cluster analysis': 'Cluster analysis',.
 'Representative comments': 'Representative comments',.
 'Introduction': 'Introduction',.
 'Clusters': 'Clusters',.
 'Appendix': 'Appendix',.
 'This report was generated using an AI pipeline that consists of the following steps': 'This report was generated using an AI pipeline that consists of the following steps',.
 'Step': 'Step',.
 'extraction': 'extraction',.
 'show code': 'Show code',.
 'hide code': 'hide code',.
 'show prompt': 'Show prompt',.
 'hide prompt': 'Hide prompt',.
 'embedding': 'embedding',.
 'clustering': 'clustering',.
 'labelling': 'labeling',.
 'takeaways': 'summary',.
 'overview': 'overview'}
```


Translation is done by function `t` returned by UseTranslatorAndReplacements, like `{t("Representative comments")}`.
You could hard code the above in this t.
The actual code uses useMemo or something like that, but I think that's because it's too heavy when translating all the data, if it's this much, it should be simple to write.

To be continued.

---
This page is auto-translated from [/nishio/Talk to the CityのUI日本語化](https://scrapbox.io/nishio/Talk to the CityのUI日本語化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.