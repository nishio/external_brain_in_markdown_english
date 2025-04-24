---
title: "Summer Polis Festival 2024"
---

I thought it would be interesting to set up Polis now, in the summer of 2024. I thought it would be interesting to set up Polis now, in the summer of 2024 ([[Polis Summer 2024]]).
    - From a [[digital democracy]] point of view, it is better to [[open up agenda-setting authority to people]].
- [[Talk to the City]] is OSS, so anyone can do it, but only engineers can do it.
- I would like to have a digital democracy festival (Summer 2024 Polis Festival) where a wider range of people can "participate".

policy
- Allow anyone to start a conversation (not limited to a specific camp)
- Does not take data tied to individuals (no linkage to Twitter or Facebook)
- All inputs are assumed to be [open data

-----
Published List
- [Arguments against election posters](https://polis.nhiro.org/6kvuuursmy)
        - [[Polis Preparation: Election Posters]]
- [Information System Commonality in Municipal DX](https://polis.nhiro.org/6spai5zjrr)
- [Voting rights from age 0](https://polis.nhiro.org/29uzxjufe9)
- [New Democracy](https://polis.nhiro.org/2fsjcfkkpz)
        - [[Polis Preparation: The New Democracy]]
- [Discussion on the redevelopment of Jingu Gaien (ver2)](https://polis.nhiro.org/4udffmr5yy)
    - [ver1](https://polis.nhiro.org/m/9herb9baam)
- [Arguments against violations of the Public Offices Election Law](https://polis.nhiro.org/4mudryyhwn)

template
- This is a forum for discussion about ~. You can vote for or against an opinion, or post a new one.
- Submissions and votes will be made open data in a form that does not identify individuals.

----- Work log

2024-06-18~22  [[Summer 2024 Polis Festival: Instance Preparation]]

2024-06-22
What to do after tomorrow
- Cut out the story until the server works.
- Commit changed files.
- Create a conversation, vote, make a comment, view a report, and look at the data in one step.


- [[Polis Preparation: Election Posters]]
![image](https://gyazo.com/bf0a4308ba38a456005e2529d782e134/thumb/1000)
When I create a conversation, I am the one who has already voted...
- I voted for 7 people and the visualization showed up too.


2024-06-23
![image](https://gyazo.com/0b83de49032550645aa3548e696798e6/thumb/1000)
Not tied to social networking sites

Tasks
- ✅Cut out the story of how the server works.
- Commit changed files.
- Create ✅conversation, VOTE, COMMENT
- view report
- View Data


js

```javascript
convasation_id = "6kvuuursmy"
report_id = "r4xnu5hwjajhsebyfbehb"
data = await fetch(`/api/v3/math/pca2?lastVoteTimestamp=0&conversation_id=${convasation_id}`).then(x=>x.json());
not_sorted_comments = await fetch(`/api/v3/comments?conversation_id=${convasation_id}&report_id=${report_id}&moderation=true&mod_gt=-1&include_voting_patterns=true`).then(x=>x.json());
comments = [];
not_sorted_comments.forEach(c=>{
    comments[c.tid] = c;
})
```



individual
js

```javascript
groupid = 0;
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


all
js

```javascript
for (let groupid = 0; groupid < 5; groupid++) {
    const repness = data.repness[groupid];
    let result = "";

    repness.forEach((r) => {
        const c = comments[r.tid];
        const overall = `Overall Group: Agree: ${c.agree_count}, Disagree: ${c.disagree_count}, Pass: ${c.pass_count}, Total: ${c.count}`;
        const g = data["group-votes"][groupid].votes[r.tid];
        const group = `This Group: Agree: ${g.A}, Disagree: ${g.D}, Pass: ${g.S - g.A - g.D}, Total: ${g.S}`;
        result += `${c.txt}\n${overall}\n${group}\n\n`;
    });
    let groupChar = String.fromCharCode('A'.charCodeAt(0) + groupid);
    console.log(`Result for Group ${groupChar}:\n${result}`);
}
```



Claude 3.5 Sonnet
:

```
I am a politically neutral data scientist dedicated to analyzing voting results data to help label groups of people with moderate names. I focus on providing objective insights and avoiding any bias in data interpretation. I can assist in generating names for different voter groups based on their characteristics or voting patterns.
Output should be in Japanese.

Group A
Obscene election posters are within the scope of freedom of expression.
Overall Group: Agree: 5, Disagree: 10, Pass: 4, Total: 19
...
```

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>Based on your request, we will propose a neutral name in Japanese that reflects the characteristics of each group:
- Group A: "Freedom of Expression Focus
    - This group values freedom of expression in election posters and tends to accept eccentricity as a strategy.
- Group B: "Regulatory prudence"
    - This group, while opposing abuses of the electoral system, is cautious about regulating the content of posters and police intervention.
- Group C: "Democratic Principle Faction"
    - This group tends to seek a balance between appropriateness and freedom of expression in the public sphere, while emphasizing democratic principles.
These designations are intended to objectively reflect the voting patterns of each group while avoiding overly biased interpretations.

I got 10 comments.
- Claude 3.5 Moderated by Sonnet

Unmoderated 10
Not only election posters, but sexually explicit postings should be discussed keeping in mind that there are people, not only children but also adults, who "don't want to see" them. In Taiwan and Scandinavia, it seems to me that there were fewer sexual postings to be seen, but I believe that this is a consideration of how sexuality should be, one's own choices, and people's comfort.
Election posters should be free, but it is recommended that the police be used to verify in advance whether or not they are expressions that break the law. However, the use of the police is voluntary.
Election posters should be issued by the candidate himself/herself. The use of election posters as a means of advertising by anyone other than the candidate himself/herself is prohibited.
The restrictions should be that the candidate's name must be included and that it should be his or her own statement for the election in question.
In the first place, I believe that the significance of the posters is diminishing, and abolishing them is a better idea.
Even election posters should be subject to other legal systems.
In the first place, it is not expression that is required in an election poster.
Pornography and nudity are different. It is the former that is in question in this case.
Rather than increasing the prohibitions, election posters should have more restrictive conditions in the first place.
The posters are a barrier to new entrants and should be posted with the posters attached from the beginning.

~2024-06-25
- [[Polis Preparation: Election Posters]]
- [[Polis Preparation: Information System Commonality for Municipal DX]]
- [[Polis Preparation: Voting Rights at Age 0]]
- [[Polis Preparation: Jingu Gaien Redevelopment]]

2024-06-25
I have a git clone on EC2, so I don't have id_rsa etc. and it asks me to authenticate when I push. I don't think GitHub does password authentication anymore, I've installed id_rsa, but I don't know what to do with the cloned repository.

ChatGPT
To configure an already cloned repository to authenticate using an SSH key, the URL of the remote repository must be changed from HTTPS to SSH. Please follow the steps below.

Check the URL of the current remote repository:

git remote -v
Change the remote repository URL to SSH:

bash
Copy code
git remote set-url origin git@github.com:ユーザー名/リポジトリ名.git
You can now use your SSH key to access GitHub. git push command will authenticate you using your SSH key.


`$ git remote -v`
origin  [https://github.com/nishio/polis.git](https://github.com/nishio/polis.git) (fetch)
origin  [https://github.com/nishio/polis.git](https://github.com/nishio/polis.git) (push)

`$ git remote set-url origin git@github.com:nishio/polis.git`

`$ git push`
:

```
The authenticity of host 'github.com (140.82.112.3)' can't be established.
ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```

yes

I could push.
Results of the last few days
[https://github.com/nishio/polis/commit/d8fee6cb9fbe938950fc54fa148fed619440301f](https://github.com/nishio/polis/commit/d8fee6cb9fbe938950fc54fa148fed619440301f)

The next step is to get this working in a local environment.


The problem of adding seed in Polis is a pain in the ass.
![image](https://gyazo.com/1e69883fb9834768d71f3e64924b5fc7/thumb/1000)

![image](https://gyazo.com/014e528d9e71620e16f4063e0f55dddc/thumb/1000)
![image](https://gyazo.com/46d61e54cd900b059315417ba1bdcc3d/thumb/1000)


2024-06-26
Talk of putting mouths to mouth for open data, pending not getting too many opinions in the first place.

I hope we can do more Polis more and more.

Problem of not being able to correct a typographical error even if you notice it after submission.
- Well, if you can change it easily, you can change it to mean something else after a vote in favor, and then you can fabricate the will of the people.
- However, it is possible if you edit the database.
- Maybe the crypto people will figure out a way to vote that can't be tampered with.

button = document.querySelector("#root > div > div.css-vurnku > div > div.css-ppq56n > div > div:nth-child(7) > div.css-vurnku > button")


/api/v3/comments
{txt: "a", pid: "mypid", conversation_id: "7dnp9ma5nv", is_seed: true}

js

```javascript
// Define multi-line text as a string
const multiLineText = `first comment

Next comment

Last comment`;.

// split on a new line and remove blank lines to make an array
const texts = multiLineText.split('\n').filter(line => line.trim() !== '');
```


Don't forget to change the conversation_id!
js

```javascript
// Asynchronous function that calls the API
async function postComments(texts) {
    const apiUrl = '/api/v3/comments';

    for (const text of texts) {
        const data = {
            txt: text,
            pid: 'mypid',
            conversation_id: '7dnp9ma5nv',
            is_seed: true
        };

        try {
            const response = await fetch(apiUrl, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(data)
            });

            if (!response.ok) {
                throw new Error(`HTTP error! status: ${response.status}`);
            }

            const result = await response.json();
            console.log('Response:', result);
        } catch (error) {
            console.error('Error posting comment:', error);
        }
    }
}

// Call a function to send text to the API
postComments(texts);
```


Multi-line summary post, done.


2024-06-27
> [nishio](https://x.com/nishio/status/1806226862525538537) (Claude) Looking at the characteristics of each group, I suggest the following names:
>  Group A: "Regulatory Focused
>  Tend to favor regulations for electoral fairness and for curbing the influence of money.
>
>  Group B: "Free Expressionists
>  Tend to value freedom of expression and oppose regulation. They value freedom of campaigning.
>
>  Group C: "Neutral Balanced"
>  There is a tendency to be divided in favor and against, and a flexible attitude to make decisions depending on the situation.
>
>  Group D: "Electoral Order Faction"
>  Strongly in favor of placing restrictions on behavior and expression during election periods.
>
>  Group E: "Free Market Faction
>  Tend to emphasize election-related commercial activities and freedom of expression.
>
>  These names reflect the voting patterns and opinion trends of each group, while attempting to avoid overly political language. We aim for an objective classification based on interpretation of the data.
>  ![image](https://pbs.twimg.com/media/GREBviObQAAXhJG?format=jpg&name=medium#.png)

> [nishio](https://x.com/nishio/status/1806227134920393120) Vote here
>  [https://polis.nhiro.org/4mudryyhwn](https://polis.nhiro.org/4mudryyhwn)
>  Click here to read the report
>  [https://polis.nhiro.org/report/r8kaansrbxtwu5wfrvitm…](https://polis.nhiro.org/report/r8kaansrbxtwu5wfrvitm…)
>
>  #Digital Democracy

> [nishio](https://x.com/nishio/status/1806231332508631105) Maybe there is a discrepancy between A-E in the image and A-E in the explanation (I think the neutral party is in the middle? I have a feeling like that)
>  Please understand that we are in the process of trial and error experimentation!


> [nishio](https://x.com/nishio/status/1806229343892582751) (Claude) We will propose a neutral name in Japanese based on the voting patterns of each group:
>  Group A: "Status Quo" This group is cautious about redevelopment and tends to want to maintain the status quo.
>  Group B: "Respect for Administrative Decisions" This group respects administrative decisions and believes that redevelopment should not be an issue in the TMG election.
>  Group C: "Citizen Participation Promoters" This group values citizen input and calls for more information disclosure and consultation.
>  Group D: "Cautious Redevelopment Supporters" This group recognizes the need for redevelopment, but values transparency and publicity.
>  ![image](https://pbs.twimg.com/media/GRECvJfbUAApui7?format=jpg&name=medium#.png)

> [nishio](https://x.com/nishio/status/1806229480324657197) Vote here
>  [https://polis.nhiro.org/4udffmr5yy](https://polis.nhiro.org/4udffmr5yy)
>  Click here to read the report
>  [https://polis.nhiro.org/report/r36bmkx37pa635xd6xmek…](https://polis.nhiro.org/report/r36bmkx37pa635xd6xmek…)


---
This page is auto-translated from [/nishio/2024年夏Polis祭り](https://scrapbox.io/nishio/2024年夏Polis祭り) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.