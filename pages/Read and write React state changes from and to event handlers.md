---
title: "Read and write React state changes from and to event handlers"
---

2019-05-17  [[React Study Diary]]
I tried to implement "check every second to see if it has changed and save if it has changed" and wrote code to check with setInterval in the function component of React, but this is not correct.
typescript

```typescript
const App: React.FC = () => {
  let [toSave, setToSave] = useState(false);
  
  useEffect(() => {
    let t = setInterval(() => {
      if (toSave) {                    // NG
        setToSave(false);
        // saveSomething()
      }
    }, 1000)
  }, []);
```


The reason is that the toSave in the function object passed as the argument to setInterval (hereafter referred to as f) refers to the toSave in the outer scope at the time f was created, and even if the state is updated by subsequent calls to setToSave, etc., the initial value It remains false.

There was a proposal to "make the state a mutable object and update it destructively" on this matter.
This is yet another trap to tread.

In this code, two timers have one state that one (1) reads periodically and the other (2) rewrites periodically. Those two displays count up sequentially, so it may appear to be working as expected. But (3)'s DOM is not updated.
typescript

```typescript
const App: React.FC = () => {
  let [count, setCount] = useState({value: 0});

  useEffect(() => {
    let t = setInterval(() => {
      console.log("Read Timer", count);  // (1)
    }, 1000)
  }, []);

  useEffect(() => {
    let t = setInterval(() => {
      count.value++;
      setCount(count);
      console.log("Write Timer", count);  // (2)
    }, 1000)
  }, []);

  return (
    <div>
      <p>You clicked {count.value} times</p>    // (3)
    </div>
  );
}
```

I didn't know this either until yesterday, but if you destructively rewrite a past value and pass it to setCount, setCount will assume that it has not changed. So the DOM update is not triggered.

> Both useState and useReducer Hooks bail out of updates if the next value is the same as the previous one. Mutating state in place and calling setState will not cause a re-render.
- [https://reactjs.org/docs/hooks-faq.html#is-there-something-like-forceupdate](https://reactjs.org/docs/hooks-faq.html#is-there-something-like-forceupdate)

In other words, the reason why the Read Timer seems to be able to read the value written by the Write Timer in this sample code is not due to the effect of React's state management, but because "both are reading and writing the same object. The same behavior is observed even if we stop using useState as shown below.
typescript

```typescript
const App: React.FC = () => {
  // Rewrite
  // let [count, setCount] = useState({value: 0});
  let count = {value: 0};
  ...
  useEffect(() => {
    let t = setInterval(() => {
      count.value++;
      // comment out
      // setCount(count);
      console.log("Write Timer", count);
    }, 1000)
  }, []);
...
```


In Write Timer, if I create a new object and setCount, the rerender is triggered once. However, the value that count in the two timers points to is still {value: 0} in the scope at the time of the first render, so it will not be counted up.

And I'm not quite sure what to do about it. [[useRef]]?

----
2019-05-18
Since useRef does not trigger a rerender, I used it with useState and all three locations are now updated.
typescript

```typescript
const App: React.FC = () => {
  let [count, setCount] = useState({value: 0});
  let countRef = useRef(count);
  
  useEffect(() => {
    let t = setInterval(() => {
      console.log("Read Timer", countRef.current);
    }, 1000)
  }, []);

  useEffect(() => {
    let t = setInterval(() => {
      let newCount = {value: countRef.current.value + 1};
      setCount(newCount);
      countRef.current = newCount;
      console.log("Write Timer", newCount);
    }, 1000)
  }, []);

  return (
    <div>
      <p>You clicked {count.value} times</p>
    </div>
  );
}
```



---
This page is auto-translated from [/nishio/Reactの状態変化をイベントハンドラから読み書きする](https://scrapbox.io/nishio/Reactの状態変化をイベントハンドラから読み書きする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.