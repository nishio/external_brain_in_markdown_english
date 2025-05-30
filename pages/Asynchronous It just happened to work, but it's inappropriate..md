---
title: "Asynchronous It just happened to work, but it's inappropriate."
---

from  [[Test asynchronous React state updates]]
It just happened to work when I await the resolve, but it's inappropriate.
I put "await" in front of "resolve" and the test happened to pass, but when I think about it, it makes no sense to await it because "resolve" does not return a Promise.
TypeScript also warns: `'await' has no effect on the type of this expression. ts(80007)`
I'm still not sure why this writing style worked, but I decided to cut it out because at least this is not the right way to write it and it would be confusing to mix it up with the main story.

-----
Rewrite as follows to execute in the order 1,2,3,4,5,6,1,2,7.

ts

```typescript
export const MyAsyncComponent = () => {
  const [value, setValue] = useState(0);
  console.log(1);
  userTrigger = () => {
    console.log(4);
    return new Promise<number>((res) => {
      resolve = res;
    }).then((x) => {
      console.log(6);
      setValue(x);
    });
  };
  console.log(2);
  return <span>{value}</span>;
};
```


ts

```typescript
  render(<MyAsyncComponent />);
  expect(screen.getByText("0")).toBeTruthy(); 
  console.log(3);
  
  userTrigger();
  console.log(5);
  expect(screen.getByText("0")).toBeTruthy();
  
  await resolve(1);
  console.log(7);

  expect(screen.queryByText("0")).toBeNull();
  expect(screen.getByText("1")).toBeTruthy();
```


(PS: await resolve(1); is wrong)

To wrap updates in setValue with act [[Replace useState]].

The warning disappeared and the test passed. I'm so happy.
full source code: [https://gist.github.com/nishio/06249db25dafef81646d961ec9c0c70e](https://gist.github.com/nishio/06249db25dafef81646d961ec9c0c70e)

---
This page is auto-translated from [/nishio/非同期たまたま動いたけど不適切](https://scrapbox.io/nishio/非同期たまたま動いたけど不適切) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.