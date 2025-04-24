---
title: "hamburger menu"
---


![image](https://gyazo.com/de27cf95a9cfcbf5e0c38ac8ed41a6b9/thumb/1000)
![image](https://gyazo.com/d8f1d06d5f7c7b4663c3bf46625db78f/thumb/1000)

[[Material-UI]]
tsx

```
import React from 'react';
import IconButton from '@material-ui/core/IconButton';
import Menu from '@material-ui/core/Menu';
import MenuItem from '@material-ui/core/MenuItem';
import MoreVertIcon from '@material-ui/icons/MoreVert';

export const MoreMenu = () => {
  const [anchorEl, setAnchorEl] = React.useState(null);
  const handleClick = (event: any) => {
    setAnchorEl(event.currentTarget);
  };
  const handleClose = () => {
    setAnchorEl(null);
  };
  return <>
    <IconButton aria-label="more" aria-controls="long-menu" aria-haspopup="true" onClick={handleClick}>
      <MoreVertIcon />
    </IconButton>
    <Menu id="long-menu" anchorEl={anchorEl} keepMounted open={Boolean(anchorEl)} onClose={handleClose}>

      <MenuItem>hello1</MenuItem>
      <MenuItem>hello2</MenuItem>
      <MenuItem>hello3</MenuItem>
    </Menu>
  </>;
};
```



---
This page is auto-translated from [/nishio/ハンバーガーメニュー](https://scrapbox.io/nishio/ハンバーガーメニュー) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.