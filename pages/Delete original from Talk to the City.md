---
title: "Delete original from Talk to the City"
---

Delete original text from [Talk to the City
![image](https://gyazo.com/a9c1e423b0e8b549a8aff2be124a2f1a/thumb/1000)

In Talk to the City, click on a dot to see the original text.
![image](https://gyazo.com/a29a8db4850f02678f17a4d8e890e2be/thumb/1000) ![image](https://gyazo.com/ca98459215468c0d5d2f550aa5f15bb8/thumb/1000)
However, there is a problem that the report screen becomes heavy because all data is embedded to display the original text, and there are cases where the original text is not desired to be displayed due to lack of permission for the right to make the original text transmittable, etc.
- After talking to someone who is familiar with the law, I realized that I could claim "citation" in a broader scope than I had originally thought.
- Related: [[Anything published can be cited.]]

# Remove from UI
.
[https://github.com/AIObjectives/talk-to-the-city-reports/blob/main/scatter/next-app/components/Tooltip.tsx#L67-L87](https://github.com/AIObjectives/talk-to-the-city-reports/blob/main/scatter/next-app/components/Tooltip.tsx#L67-L87)
ts

```typescript
    {expanded ? <div>
      <VideoLink {...point} showVideo={true} showThumbnail={false} />
      <div className='text-sm opacity-80 mt-2'>
        <span className='font-semibold'>{t(point.video ? "Transcript" : "Original comment")}:</span>
        "{point.comment.length > 100 && !showMoreComment ?
          <span>
            {point.comment.slice(0, 200) + '..."'}
            <span className='underline cursor-pointer'
              onClick={() => setShowMoreComment(true)}>
              {t("read more")}
            </span>
          </span> :
          point.comment + '"'}
      </div>
      <div className='text-xs opacity-50 italic mt-4'>
        {t("Click anywhere on the map to close this")}
      </div>
    </div> :
      <div className='text-xs opacity-50 italic'>
        {t(point.video ? "Click on the dot to see original video and transcript" : "Click on the dot for details")}
      </div>}
```

If this range is commented out, it can be removed from the UI (static content must be regenerated).
- `$ main.py -o visualization config/...`


# erase from data as well
.
But I'd like to erase it from the data as well (it would be needlessly heavy).

The data type looks like this
ts

```typescript
export type Argument = {
  arg_id: string;
  argument: string;
  comment_id: string;
  x: number;
  y: number;
  p: number;
};

export type CommentObj = {
  comment: string;
  agrees?: number;
  disagrees?: number;
  video?: string;
  interview?: string;
  timestamp?: string;
};

export type CommentsMap = {
  [id: string]: CommentObj;
};
...
export type Point = Argument & Cluster & CommentObj & { color: string };
```


Where are you reading the data?
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


The result.json of the output of the analysis execution environment is read and turned into static HTML by server-side rendering.

To delete from static HTML already generated
This data is under `_next/data` after static output
![image](https://gyazo.com/6c72e29ea71539ec1686a21f0eee4f96/thumb/1000)

![image](https://gyazo.com/56a9864d1b189b4cf5206955bdbd4a40/thumb/1000)
Let's empty this.

# comment emptying process
.
python

```
import json
filename = "_next/data/8gQb47OhoAQvRNCBqVMIF/index.json"
```

python

```
data = json.load(open(filename))
comments = data["pageProps"]["result"]["comments"]
for k in comments:
    comments[k]["comment"] = ""
json.dump(data, open(filename, "w"), ensure_ascii=False) 
```


![image](https://gyazo.com/0345f756f553ce9f41743b2553461be7/thumb/1000)
I was able to turn it off.

But this wasn't enough to make it disappear from the web screen.
I wondered why it was all embedded in index.html in the first place (what is index.json for? Is it being read?)
![image](https://gyazo.com/f4e5228d3f59ed8ce46fc4f27dbd5264/thumb/1000)
json

```json
{"props": ...,"page":"/","query":{},"buildId":"aZQl6X8wn0bor6WDO4T50","assetPrefix":".","isFallback":false,"gsp":true,"scriptLoader":[]}
```

The contents of index.json are embedded in the ... The contents of index.json are embedded in the
If you replace the contents here with the contents of the comment-empty index.json

![image](https://gyazo.com/6ae6643dffe9fb2b2c8c887a8cb04400/thumb/1000)
It was confirmed to have disappeared from the data as well.

When performing UI regenerations
I think it would be better to erase it from the JSON before visualization.

---
This page is auto-translated from [/nishio/Talk to the Cityから原文を消す](https://scrapbox.io/nishio/Talk to the Cityから原文を消す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.