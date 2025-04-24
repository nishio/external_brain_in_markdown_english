---
title: "ref and useEffect"
---

![image](https://gyazo.com/9a294a69bcfc79a07aa38d51b4722ef8/thumb/1000)

- The second stage is the generation of the DOM. It takes place after the function component has finished executing its function. useEffect is called after it has finished.

ts

```typescript
const MyComponent: React.FC<{}> = () => {
  console.log("function body")
  const [, setX] = useState({});
  const ref = useRef(null);
  console.log("ref.current", ref.current);
  useEffect(() => {
    console.log("useEffect")
  })
  const onClick = () => {
    console.log("onClick");
    setX({});
  }
  return <div ref={ref}>
    <button onClick={onClick}>redraw!</button>
  </div>
}
```

![image](https://gyazo.com/919b4dfb1d3b951bb6fd1b6deff2d55d/thumb/1000)


---
This page is auto-translated from [/nishio/refとuseEffect](https://scrapbox.io/nishio/refとuseEffect) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.