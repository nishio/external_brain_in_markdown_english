---
title: "React.forwardRef"
---

I'm not sure at what point it's required.
ts

```typescript
type PropsType = { id: ItemId };
export const BigMenuItem = React.forwardRef<HTMLLIElement, PropsType>(
  ({ id }, ref) => {
    const onBig = () => {
      updateGlobal((g) => {
        const item = get_item(g, id);
        item.scale++;
      });
      close_menu();
    };

    return (
      <MenuItem onClick={onBig} ref={ref} data-testid="big">
        big
      </MenuItem>
    );
  }
);
```


---
React.forwardRef does not seem to be able to take function components as arguments as types. As an implementation, it can.

`function React.forwardRef<unknown, {}>(render: React.ForwardRefRenderFunction<unknown, {}>): React.ForwardRefExoticComponent<React.RefAttributes<unknown>>`

FC as an argument will result in an error.
> Argument of type 'FC<Props>' is not assignable to parameter of type 'ForwardRefRenderFunction<unknown, Props>'.
ts

```typescript
const _MenuItem: React.FC<Props> = (props) => {
  const { title, onClick, ref, ...other } = props;
  const f = () => {
    handleClose();
    onClick();
  };
  return (
    <MenuItem onClick={f} {...other} ref={ref}>
      {title}
    </MenuItem>
  );
};

export const AutoCloseMenuItem = React.forwardRef(_MenuItem);
```


The same implementation is OK as long as the type is not declared as FC
ts

```typescript
const _MenuItem = (props: Props) => {
	... // (same)
};

export const AutoCloseMenuItem = React.forwardRef(_MenuItem);
```


Added on 2021-09-01
- This is just implicitly throwing out the second argument, ref, because there's no type checking.

---
This page is auto-translated from [/nishio/React.forwardRef](https://scrapbox.io/nishio/React.forwardRef) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.