---
title: "Azure Document Intelligence"
---

> [hiro_gamo](https://x.com/hiro_gamo/status/1799104021703405829) A good thing a day, so... today I'd like to introduce you to a humble service that is often used to extract information from RAG documents... Azure Document Intelligence.
>
>  Azure Document Intelligence (ADI) is an API service for OCR and layout extraction of PDFs that continues to evolve in the context of LLM's RAG.
>
>  Basic functions from PDFs, images, and other files
>  ・Character
>  ・Table structure and internal text
>  ・ Location of the figure
>  These can be output as JSON or markdown.
>
>  When outputting markdowns, not simply extracting text, but also taking chapter titles into consideration, etc. can be extracted.
>
>  GPT and other LLMs are relatively strong in reading markdown formats and can be effective in extracting information from RAG documents, as interpretability can vary depending on chapter construction.
>
>  Actually, VLMs such as GPT-4o can do the same thing, but this service is still in high demand because it eliminates the need for prompting, fixing the output format, and supports fine tuning.
>
>  The following is often performed in the extraction of information for RAGs.
>  1. layout analysis and markdown with ADI
>  2. Crop only the figure from the figure's location information
>  3. pass the figure to GPT-4V and extract readable information
>  4. return the information obtained in 3. to markdown
>  This text information is used as a starting point for processing chunks, etc.
>
>  Marked down makes subsequent processing (dynamic chunking into GPT4, FAQing, etc.) easier, so please use it.
>
>  You can even try it out from the GUI as long as you build the resources.
>
>  [https://learn.microsoft.com/ja-jp/azure/ai-services/document-intelligence/concept-layout?view=doc-intel-4.0.0&viewFallbackFrom=form-recog-3.0.0&tabs=sample-code…](https://learn.microsoft.com/ja-jp/azure/ai-services/document-intelligence/concept-layout?view=doc-intel-4.0.0&viewFallbackFrom=form-recog-3.0.0&tabs=sample-code…)
>  ![image](https://pbs.twimg.com/media/GPerwIEbEAAmI9O?format=png&name=medium#.png) ![image](https://pbs.twimg.com/media/GPeuFiQaoAAZioi?format=jpg&name=large#.png)


---
This page is auto-translated from [/nishio/Azure Document Intelligence](https://scrapbox.io/nishio/Azure Document Intelligence) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.