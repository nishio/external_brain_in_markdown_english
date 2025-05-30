---
title: "Sentry with MouseMove thinned out"
---

In automating the Regroup test, we want to record and reproduce the user's "drag and enclose" operation. However, we do not want to record all of the MouseMove events, as there are many of them.
![image](https://gyazo.com/e228c23fff2d61bc95430876234ac701/thumb/1000)
Therefore, we decided to "not record if the last event is a MouseMove event and if it is within 500ms". The recording destination is a ring buffer, and only the last 100 events are retained.
ts

```typescript
export const push = (data: IHasType) => {
  if (data.type === "Drag") {
    if (prevEvent?.type === "Drag") {
      if (Date.now() - prevEventTime < 500) {
        prevEventTime = Date.now();
        prevEvent = data;
        return;
      }
    }
  }
  prevEventTime = Date.now();
  prevEvent = data;
  
  const json = JSON.stringify(data);
  if (ringBuffer.length < MAX_RECORD_NUM) {
    ringBuffer.push(json);
  } else {
    ringBuffer[index] = json;
    index = (index + 1) % MAX_RECORD_NUM;
  }
};

export const get = () => {
  return ringBuffer.slice(index).concat(ringBuffer.slice(0, index));
};
```


I added "Send to Sentry" to the menu; you can get the following on Sentry.
![image](https://gyazo.com/6f055b05a6732fabdb59455fcb1476d2/thumb/1000)


PS
- I went to the trouble of making it, but the default canvas size was too small when I tested it, so I had to fiddle with the values by hand and thought, "What? If this is the case, why didn't you just type it in by hand from the beginning?" I thought, "If this is the case, why didn't I just type it in manually from the beginning?
- Well, I can say that doing this made it easier because I understood what events were happening and in what order.
- Sending to Sentry has the advantage of recording problems that occur outside the development environment, but in the development environment, direct observation in console.log is better for immediate observation after operation.
- Console.log in the event handler will result in a large number of move-type events, so in that sense, this method of thinning out the events by time is a good one.

---
This page is auto-translated from [/nishio/MouseMoveを間引いてSentry](https://scrapbox.io/nishio/MouseMoveを間引いてSentry) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.