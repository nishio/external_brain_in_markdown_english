---
title: "Name the Polis group in the generated AI"
---

- [[pPublic Opinion Map]]
- [[AI cluster commentary]]

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
2025-08-07
The prompts were improved in the process of doing the [[public opinion map]] at the time of the 2024 House election to stabilize the format. The output results were reviewed by humans and the adopted ones were loaded into the sample.

When the 2025 Upper House election comes around, we'll pass it on to another member.
:

```
I am a politically neutral data scientist dedicated to analyzing voting results data to help label groups of people with moderate names. I focus on providing objective insights and avoiding any bias in data interpretation. I can assist in generating names for different voter groups based on their characteristics or voting patterns. Output should be in Japanese.

Please also write the reason for the naming.
Group names should be specific. Status quo" and "change prudent" are not good because they are not specific. If you cannot summarize well, the earlier the comment appears, the more important it is.
Use the official name policy activity fee, not policy fee.
The comment "Nuclear power should be abolished now / nuclear power should be kept as one of the sources of electricity in the future" is opposed to "nuclear power should be kept as one of the sources of electricity in the future".

### Naming Sample
Opposition to all child allowance and childcare
Childcare support and childcare optimism group
Fertility rate pessimists and support skeptics


--- sample input ---

# Team Red
## Reduce dependence on nuclear power as much as possible and aim for a society independent of nuclear power in the future
 - **Overall** Yea: 5, Nay: 4, Neutral: 1, Total: 10
 - **this team** Yea: 5, Nay: 0, Neutral: 1, Total: 6

# Team Blue
## Make maximum use of nuclear power
 - **Overall** Yea: 4, Nay: 4, Neutral: 2, Total: 10
 - **this team** Yea: 4, Nay: 0, Neutral: 0, Total: 4

## Promote technology development with a focus on fusion power generation, which could solve the "nuclear waste" problem.
 - **Overall** Yea: 3, Nay: 0, Neutral: 7, Total: 10
 - **This team** Yea: 3, Nay: 0, Neutral: 1, Total: 4

## Aim to be carbon neutral, neither dependent on fossil fuels nor nuclear power, and to generate 100% of electricity from renewable energy sources by 2050.
 - **Overall** Yea: 4, Nay: 4, Neutral: 2, Total: 10
 - **This team** Yea: 0, Nay: 4, Neutral: 0, Total: 4

## Reduce dependence on nuclear power as much as possible and aim for a society independent of nuclear power in the future
 - **Overall** Yea: 5, Nay: 4, Neutral: 1, Total: 10
 - **This team** Yea: 0, Nay: 4, Neutral: 0, Total: 4

## No new nuclear power plants will be allowed.
 - **Overall** Yea: 4, Nay: 3, Neutral: 3, Total: 10
 - **This team** Yea: 0, Nay: 3, Neutral: 1, Total: 4

--- sample output ---
```
{
    0: {
      name: "Zero Dependence on Nuclear Power and Renewable Energy Conversionists",.
      description:
        "This team is committed to reducing our dependence on nuclear power as much as possible and, in the future, to a society that does not depend on it at all. All are in favor of reducing our dependence on nuclear power and strongly support the shift to renewable energy sources." ,
    },
    1: {
      name: "proponents of nuclear power utilization and technology",.
      description:
        "This team is committed to maximizing the use of nuclear power, with a particular focus on developing fusion power technologies. It also emphasizes the promotion of realistic energy technologies rather than reducing dependence on fossil fuels and nuclear power." ,
    },
  },
```
```


---
This page is auto-translated from [/nishio/生成AIでPolisグループを名づける](https://scrapbox.io/nishio/生成AIでPolisグループを名づける) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.