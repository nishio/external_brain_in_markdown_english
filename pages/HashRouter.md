---
title: "HashRouter"
---

[[react-router-dom]]

ts

```typescript
import {
  HashRouter as Router,
  Switch,
  Route,
  Link
} from "react-router-dom";
```


ts

```typescript
const Foo = () => {
  let { id } = useParams();
  return <span>{id}</span>;
}

const App: React.FC = () => {
  return (
    <HashRouter hashType="noslash">
      <Switch>
        <Route path="/" exact children={<span>root</span>} />
        <Route path="/1" children={<h3>One</h3>} />
        <Route path="/2" children={<h3>Two</h3>} />
        <Route path="/:id" children={<Foo />} />
      </Switch> 
```


`<a href={"#" + key}>{value.title}</a>`
`<Link to={key}>{value.title}</Link>`

[https://github.com/ReactTraining/react-router/blob/master/packages/react-router-dom/docs/api/HashRouter.md](https://github.com/ReactTraining/react-router/blob/master/packages/react-router-dom/docs/api/HashRouter.md)



---
This page is auto-translated from [/nishio/HashRouter](https://scrapbox.io/nishio/HashRouter) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.