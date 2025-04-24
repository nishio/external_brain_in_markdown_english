---
title: "Function components cannot be given refs"
---

> Warning: Function components cannot be given refs. Attempts to access this ref will fail. Did you mean to use React.forwardRef()?

[[Material-UI]]'s Menu tries to inject a ref into a child element and is warned when it is a function component.
ts

```typescript
      <Menu ... >
        <MyMenuItem onClick={exportForRegroup}>Export for Regroup</MyMenuItem> 
```


ts

```typescript
  const MyMenuItem = (props: any) => {
    const { children, onClick, ...other } = props;
    const f = () => {
      onClick();
      setAnchorEl(null);
    };
    return (
      <MenuItem onClick={f} {...other}>
        {children}
      </MenuItem>
    );
  };
```


revision (e.g. of a rule, regulation, etc.)
Forward ref with React.forwardRef as per warning message
ts

```typescript
  const MyMenuItem = React.forwardRef((props: any, ref) => {  // here
    ...
    return (
      <MenuItem onClick={f} {...other} ref={ref}>  // here
        {children}
      </MenuItem>
    );
  });
```



---
This page is auto-translated from [/nishio/Function components cannot be given refs](https://scrapbox.io/nishio/Function components cannot be given refs) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.