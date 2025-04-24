---
title: "pVectorSearch2023-06-05"
---

prev [[pVectorSearch2023-06-02]] parent [[pVectorSearch]]

NextJS
- [Getting Started: Installation | Next.js](https://nextjs.org/docs/getting-started/installation)
    - `$ npx create-next-app@latest`
    - They'll ask if you want to use TypeScript or something.
    - I named it `vecsearch-service`.
    - A folder with this name is created and Git managed.
- Put into Github
    - > push an existing repository from the command line
    - made private

Vercel
- Log in to your dashboard
- The repository you just saw is displayed, so select it and deploy.
- I was able to deploy.
- Oh, it's going to be `https://vecsearch-service.vercel.app/`.
- You can change it right from the settings.
    - [https://nishio-vecsearch.vercel.app/](https://nishio-vecsearch.vercel.app/)
What a convenient time we live in!

Create API
- [Routing: API Routes | Next.js](https://nextjs.org/docs/pages/building-your-application/routing/api-routes)
- If there is no `src`, the place to put it is `<project_root>/pages/api/foo.ts`.
ts

```typescript
import { NextApiRequest, NextApiResponse } from "next";

const handle = async (_req: NextApiRequest, res: NextApiResponse) => {
  res.status(200).json({ data: "hello world" });
};
export default handle;
```

- OK
- I was confused when it didn't work, but GPT-4 told me to reboot the server, so I rebooted it and it worked, convenient times.

API that taps other APIs
- Try ScrapboxAPI for now.
    - [https://scrapbox.io/api/pages/nishio/pVectorSearch2023-06-05](https://scrapbox.io/api/pages/nishio/pVectorSearch2023-06-05)
ts

```typescript
import { NextApiRequest, NextApiResponse } from "next";
import axios from "axios";

const handle = async (_req: NextApiRequest, res: NextApiResponse) => {
  const otherApiUrl =
    "https://scrapbox.io/api/pages/nishio/pVectorSearch2023-06-05";

  try {
    const response = await axios.get(otherApiUrl, {});
    res.status(200).json(response.data);
  } catch (error) {
      res
        .status(500)
        .json({ error: "An error occurred while calling the other API" });
  }
};
export default handle;
```

    - OK

Beating OpenAI
embed.ts

```typescript
import axios from "axios";

export const embed = async (textToEmbed: string) => {
  const model = "text-embedding-ada-002";
  const URL = "https://api.openai.com/v1/embeddings";
  // Call OpenAI Embedding API
  const openAIResponse = await axios.post(
    URL,
    { input: textToEmbed, model: model },
    {
      headers: {
        Authorization: `Bearer ${process.env.OPENAI_API_KEY}`,
        "Content-Type": "application/json",
      },
    }
  );
  const openAIEmbedding = openAIResponse.data.data[0].embedding; // assuming the embedding is in this path
  return openAIEmbedding;
};
```

embed.ts

```typescript
import { NextApiRequest, NextApiResponse } from "next";
import { embed } from "../../utils/embed";

const handle = async (req: NextApiRequest, res: NextApiResponse) => {
  const textToEmbed = req.body.text;
  const openAIEmbedding = await embed(textToEmbed);
  res.status(200).json(openAIEmbedding);
};
export default handle;
```

- OK

Striking the Qdrant
search.ts

```typescript
import { NextApiRequest, NextApiResponse } from "next";
import { embed } from "../../utils/embed";
import { QdrantClient } from "@qdrant/js-client-rest";

const handle = async (req: NextApiRequest, res: NextApiResponse) => {
  const textToEmbed = req.body.text;
  const openAIEmbedding = await embed(textToEmbed);

  const COLLECTION_NAME = process.env.QDRANT_COLLECTION_NAME!;

  const client = new QdrantClient({
    url: process.env.QDRANT_ENDPOINT,
    apiKey: process.env.QDRANT_API_KEY,
  });

  const grdantResult = await client.search(COLLECTION_NAME, {
    vector: openAIEmbedding,
    limit: 3,
  });

  res.status(200).json(grdantResult);
};
export default handle;
```

- OK

Take a search string from a form
:

```
Error: Event handlers cannot be passed to Client Component props.
 <button id="search" onClick={function} children=...>
                             ^^^^^^^^^^
If you need interactivity, consider converting part of this to a Client Component.
```


Formatting the response
- Create URL from Scrapbox title
- ![image](https://gyazo.com/27e93ce643025450fc3930f36cbffb46/thumb/1000)
- Looks aside, the search was done.
    - Click on the title to jump to the corresponding page in Scrapbox
    - I'm new to TailwindCSS and don't know what to do with the look and feel.
        - Let's ask ChatGPT w
    - I said "Make the result looks better." and they made it look good. w
        - ![image](https://gyazo.com/91e36c13c5d7e4a50e292b8fea06ab4e/thumb/1000)
    - I had the whole thing fixed.
        - ![image](https://gyazo.com/05926e6fbdd4634d05ea0e3e899b86d7/thumb/1000)
        - As for the appearance design of a web app that I'm not particular about, ChatGPT is good enough...

Note for next time
- Page title image
    - `/api/pages/:projectName/:pageTitle/icon`

- Screen for administrator
    - Search queries are stored and made available for the administrator to see.
        - Create a page with an explanation to that effect.
        - At the time of the search, the results are put into Firebase to produce permalinks, or
    - Published in.
        - I try to use it myself from my phone.
        - I looked at it from my phone and the background wasn't black.
        - When I search, I can't tell if the search is in progress or died due to an error ✅fixed
        - The error on my phone ✅fixed
            - Forgot to set environment variables!
            - .env.local doesn't go into the environment variable at the deployment destination (it was .gitignore to begin with and not in the repository!)
    - Attach [URL Fragment Text Directives
        - This is tricky.
            - For example, if there's Scrapbox notation in the mix, there's no notation in the browser text, so there's no hit.
            - If we're going to be serious about this, it needs to be plain text.

[GPT](https://chat.openai.com/share/a0afa341-a147-4c0f-a164-9587eb4fc815)
next: [[pVectorSearch2023-06-06]]

- [[Related pages in vector search]]
---
This page is auto-translated from [/nishio/pVectorSearch2023-06-05](https://scrapbox.io/nishio/pVectorSearch2023-06-05) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.