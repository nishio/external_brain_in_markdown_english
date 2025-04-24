---
title: "Modifying the Talk to the City UI"
---

As you can see in `visualization.py`, I just hit `command = f "REPORT={output_dir} npm run build"` in subprocess

In the aggregation step before visualization, all data necessary for visualization are aggregated into result.json.
Reading it in `next-app/pages/index.tx
index.tsx

```
export async function getStaticProps({ params }: any) {
  const report = process.env.REPORT
  if (report && report.length) {
    const fs = require('fs');
    const result = fs.readFileSync(`../pipeline/outputs/${report}/result.json`, 'utf8');
    return { props: { result: JSON.parse(result) } }
  }
  const fs = require('fs');
  const subfolders = fs.readdirSync(outputs, { withFileTypes: true })
    .map((x: any) => x.name)
    .filter((x: string) => !x.startsWith('.'));
  return { props: { subfolders } };
}
```


This `{ props: { result: JSON.parse(result) }` part is embedded in the HTML like this

html

```html
    <script id="__NEXT_DATA__" type="application/json">
      {
        "props": {
          "pageProps": {
            "result": {
              "clusters": [
                {
                  "cluster": "environmentally friendly city", ...
```

So, if you write out the `"result": { ... }` to result.json, you can develop an advanced UI based on the static HTML report.

Suppose you put the exported result.json in `scatter/pipeline/outputs/tokyo/result.json
`$ REPORT=tokyo npm run build` in `scatter/next-app%` will output to `scatter/pipeline/outputs/tokyo/report/`.

In the meantime, I've added a search highlight.
    - [[Talk to the City search highlight feature]]


(I expected `npm run dev` to start the hot reload development server, but I got an error `Error: Cannot find module 'react/jsx-runtime'` and gave up because I wasn't sure)



---
This page is auto-translated from [/nishio/Talk to the CityのUIを改造する](https://scrapbox.io/nishio/Talk to the CityのUIを改造する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.