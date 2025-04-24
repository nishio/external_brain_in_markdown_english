---
title: "Talk to the City and Attribute Multiplication Analysis"
---

2025-04-11
- Implemented here in anno-broadlistening
    - [https://github.com/takahiroanno2024/anno-broadlistening/issues/9](https://github.com/takahiroanno2024/anno-broadlistening/issues/9)
- Later, when the hierarchy function was added, the UI was changed to Plotly, and it was temporarily turned off because it was not a priority to support at that time.

2024-12-06
There is a need to visualize the distribution of free-text data in 2D using [[Talk to the City]], and then analyze it in terms of specific attributes (e.g., age range, data source, answers to optional questions other than free-text for surveys, etc.).

There are a number of ways to do this analysis.
- Split data by attribute and visualize each in two dimensions
- After summarizing and 2D visualization, highlight/change the display according to attributes.
Each has its merits and demerits, but ultimately "you should try it and observe it," and since the former is as simple as separating the data, I'll write an explanation of the latter here

Data for visualization is compiled in `result.json` and read by `getStaticProps` in `index.tsx
So it would be a good idea to edit `result.json` and add data for attributes before visualization
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

like this
result.json

```json
{
  "clusters": [ ... ],
  "comments": [ ... ],
  "propertyMap": {
    "Age Group": {
      "arg1": "20s", "arg1".
      "arg2": "60s"
    },
    "Data Source": {
      "arg1": "X",
      "arg2": "mailed"
    },
  }
}
```


The actual scatter plots are implemented in `DesktopMap.tx` and `MobileMap.tx` as follows
DesktopMap.tsx

```
{/* DOT CIRCLES */}
{clusters.map((cluster) =>
  cluster.arguments
    .filter(voteFilter.filter)
    .map(({ arg_id, x, y }) => (
      <circle
        className="pointer-events-none"
        key={arg_id}
        id={arg_id}
        cx={zoom.zoomX(scaleX(x) + 20)}
        cy={zoom.zoomY(scaleY(y))}
        fill={color(cluster.cluster_id, onlyCluster)}
        opacity={
          expanded && tooltip?.arg_id !== arg_id ? 0.3 : 1
        }
        r={tooltip?.arg_id === arg_id ? 8 : 4}
      />
    ))
)}
```


This color function is given from outside the component as props, but since it takes a cluster_id as an argument, it is inconvenient that it can only paint by clusters as it is now. If this function also takes `arg_id`, it will be possible to change the color by attribute by changing the function to be given.
(onlyCluster is for the view where the individual clusters are described, but for future expansion, it might be better to make it an optional variable rather than a positional argument like this.)
(Personally, I would like to make it a function that also returns opacity as a set, so that it can do things like "keep the cluster color scheme, but increase the transparency of attribute data points that are not the focus of attention," but that would complicate things, so I'll pass on that for now).

This color is specified in `Report.tsx` with a custom hook called `useClusterColor`.
`const color = useClusterColor(clusters.map((c) => c.cluster_id));`
The detailed implementation will vary depending on whether you are adding a new view for attribute-by-attribute multiplication analysis or adding a multiplication function to this view, but basically you can change this so that it is not limited to coloring by clusters
`const [color, setColor] = useState(cluster_color) // default value to color in cluster`.
In the handler for the selection event in the UI that makes the selection of the attribute `attr`.
`setColor(color_by_attribute(attr))`
You can do things like
`color_by_attribute(attr)` is a function that returns "a function that takes an argument `arg_id' and determines a color by looking at the value of the argument's attr attribute

---
This page is auto-translated from [/nishio/Talk to the Cityと属性の掛け合わせ分析](https://scrapbox.io/nishio/Talk to the Cityと属性の掛け合わせ分析) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.