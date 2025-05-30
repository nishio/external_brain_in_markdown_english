---
title: "Co-editing Regroup"
---

Explanation of how the collaborative editing tool is realized in Regroup

ts

```typescript
ReactDOM.render(<Router />, document.getElementById('root'));
```


ts

```typescript
const Router = () => {
  return (
    <HashRouter>
      <Route path="/:id" component={WhenHashSpecified} />

      <Route exact path="/">
		...
      </Route>
    </HashRouter>
  );
}
```


ts

```typescript
function WhenHashSpecified(obj: any) {
  return (
    <App urlParam={obj.match.params.id} />
  );
}
```


ts

```typescript
const App = (props: { urlParam: string }) => { 
  useUrlParam(props.urlParam)
  ...
```


ts

```typescript
export const useUrlParam = (urlParam: string) => {
  useEffect(() => {
    // resolve map name
  	// subscribe changes on server
  	...
  }, [urlParam]);

  const items = getGlobal().items;
  useEffect(() => {
  	// save to server if items are changed
  }, [items]);
};
```


// save to server if items are changed
- When the position of a sticky is moved by dragging the mouse, a request is sent for each mouse move, which is too slow, so we changed it to every 100ms.
- Now I've reconsidered, "It's not a good idea to do a React-like state update with every mouse move in the first place.
ts

```typescript
if (toSave) {
  // do nothing
} else {
  toSave = true;
  setTimeout(() => {
    toSave = false;
    saveToServer()
  }, 100)
}
```


// resolve map name
- Resolve the name of the map to be referenced based on the URL parameter.
- When I first created it, I wanted to achieve something like GoogleDoc, where you can edit the map with a link to view it, and then you can't edit it, but you can view it. A system where the edit link is not predictable from the view link.
- Error handling is messy, if a key is not found, foul back to a blank map.
- This is where I want to "show local data if not connected to the internet".
ts

```typescript
if (urlParam.match(/key=([^&]*)/)) {
  const key = RegExp.$1;
  db.collection("key_to_map").doc(key).get().then((doc: any) => {
    if (doc.exists) {
      console.log("map exists")
      const toConnect = true;
      const { isReadOnly, mapname } = doc.data()
      setGlobal({
        toConnect: toConnect,
        isReadOnly: isReadOnly,
        mapname: mapname
      })
      setUpReadSubscription(toConnect, isReadOnly, mapname);
    } else {
      // doc.data() will be undefined in this case
      console.log("No such document!");
    }
  }).catch((error: any) => {
    console.log("Error getting document:", error);
  });
} else {
  // handle special case for development
} 
```


// subscribe changes on server
The basics go like this
ts

```typescript
let unsubscribe = db.collection("map").doc(mapname).onSnapshot((doc: any) => {
  loadFromServer(doc.data());
});
```

When it is writable, I read it first and then subscribe, with the intention of "not overwriting the server data by changing it at hand before reading it," but it should not be editable until the reading is complete in the first place.

Create a new map
- I'm writing the initial state to the server and opening it in a new tab.
- I want to create a new one even when there is no network connection.
- But add's CATCH is not called immediately, because it is silently retried internally
        - [[Offline determination in Firestore]] The fact that it can't be done by itself may have something to do with it.
ts

```typescript
const createNewMap = () => {
  saveToNewMap(INITIAL_GLOBAL_STATE).then((docRef: any) => {
    window.open(`/#/key=${docRef.id}`)
  })
}
```

ts

```typescript
export const saveToNewMap = (state: TYPE_GLOBAL_STATE) => {
  const doc = convertStateToFirestore(state);
  return db.collection("map").add(doc)
    .then((docRef: any) => {
      return db.collection("key_to_map").add(
        { mapname: docRef.id }
      )
    })
    .catch((error: any) => {
      alert(`Error: ${error}`)
    });
}
```



---
This page is auto-translated from [/nishio/Regroupの共同編集](https://scrapbox.io/nishio/Regroupの共同編集) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.