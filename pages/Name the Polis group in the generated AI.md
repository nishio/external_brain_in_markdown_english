---
title: "Name the Polis group in the generated AI"
---

[[Polis2024-05-08]]
[[pPolis]]
I tried to wget the Polis report screen, but it is almost empty, and the contents to be rendered are retrieved from JSON using the API and rendered using JS. Conversely, the API can obtain enough data from the client side to render that report, so there is a high degree of freedom.

## conversations
General Information
`/api/v3/conversations?conversation_id=<ID>`

## comments
Aggregation by question
`/api/v3/comments?conversation_id=<id>&report_id=<id>&moderation=true&mod_gt=-1&include_voting_patterns=true`

Why do we need report_id?

## pca2
Data for visualization in reports
`/api/v3/math/pca2?lastVoteTimestamp=0&conversation_id=<id>`
I thought it was just PCA, but I've got most of it all tucked in here.

miscellaneous codes
js

```javascript
data = await fetch(`/api/v3/math/pca2?lastVoteTimestamp=0&conversation_id=${id}`).then(x=>x.json());
not_sorted_comments = await fetch(`/api/v3/comments?conversation_id=${id}&report_id=${report_id}&moderation=true&mod_gt=-1&include_voting_patterns=true`).then(x=>x.json());
comments = [];
not_sorted_comments.forEach(c=>{
    comments[c.tid] = c;
})
```

js

```javascript
groupid = 1;
repness = data.repness[groupid];
result = "" 
repness.forEach((r)=>{
    c = comments[r.tid];
    overall = `Overall Group: Agree: ${c.agree_count}, Disagree: ${c.disagree_count}, Pass: ${c.pass_count}, Total: ${c.count}`;
    g = data["group-votes"][groupid].votes[r.tid]
    group = `This Group: Agree: ${g.A}, Disagree: ${g.D}, Pass: ${g.S - g.A - g.D}, Total: ${g.S}`;
    result += `${c.txt}\n${overall}\n${group}\n\n`;
})
console.log(result);
```


# GPTs
[ChatGPT - Polis cluster naming](https://chatgpt.com/g/g-h15rqoZlE-polis-cluster-naming)

## base prompt
.
:

```
I am a politically neutral data scientist dedicated to analyzing voting results data to help label groups of people with moderate names. I focus on providing objective insights and avoiding any bias in data interpretation. I can assist in generating names for different voter groups based on their characteristics or voting patterns.
```


---
This page is auto-translated from [/nishio/生成AIでPolisグループを名づける](https://scrapbox.io/nishio/生成AIでPolisグループを名づける) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.