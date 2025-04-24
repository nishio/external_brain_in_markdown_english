---
title: "🤔Make a screenshot in full size"
---

If you zoom out to see the whole map and take a screenshot, you can't see the small text, and if you zoom in, it doesn't fit on one screen -> then you should have the ability to take a screenshot of the whole map at full size

The last time I tried it, I "resized the canvas already used for drawing afterwards".
- And then there was the mysterious drawing displacement, etc.
- Instead, just create a new canvas, draw on it, and destroy it.
- For this purpose, I would like the ability to change the canvas to be drawn on.

---
- I've already done the part where the canvas is made into an image.
    - `image.src = canvas.toDataURL();`
- Just set the scale to 1, enlarge the canvas to fit the content area, and then do it.
    - Calculation of content range not yet implemented
        - Is `paper.project.activeLayer.getBounds()` enough?
        - Need to resize the canvas, redraw, and wait until it is done before making it into an image
        - [http://localhost:3000/#/key=n8ma4V1BtQyc8Bc6JDKD](http://localhost:3000/#/key=n8ma4V1BtQyc8Bc6JDKD)
        - Changing canvas size, not working as expected
            - Unexplained breakage that stretches vertically or misaligns stickies and text.
            - ![image](https://gyazo.com/48d97dcd8b9b6762bb4bfa818b0bcdab/thumb/1000)
ts

```typescript
  test: () => {
    // @ts-ignore
    const b: paper.Bound = app.paper.project.activeLayer.getBounds();
    console.log(b, b.width, b.height);

    const canvas = document.getElementById("myCanvas") as HTMLCanvasElement;
    canvas.width = b.width;
    canvas.height = b.height;
    updatePaperZoomCenter(b.center, 1);
  },
```

            - Put in 'feature/fullscreenshot' and hold.
        - ？？
            - ![image](https://gyazo.com/1d55791f71522408e58acf9f44281efd/thumb/1000)
        - [html - Canvas width and height in HTML5 - Stack Overflow](https://stackoverflow.com/questions/4938346/canvas-width-and-height-in-html5/43364730)
        - I see, [[canvas element has separate width and style.width]].
        - The problem with the aspect ratio being wrong has been fixed.
        - Offset is wrong.
            - I can understand this one.
        - The position of the text on the sticky is misaligned with the position of the recto.
            - Why this is so is puzzling.

    - Once implemented, it can also be used to handle cases where the viewport is not specified in the URL.
        - [[Zoom with full view when loading editor]]
        - [[Specify viewport by URL]]
        - [[If the coordinates are not specified, the whole display first.]]
        - Needs to be delayed.
- It looks like it could be an automatic download.
js

```javascript
link.href = canvas.toDataURL()
link.download = 'filename.png'
link.click()
```

- I have a theory that it doesn't work with IE and Edge, but oh well.

[[pRegroup]]

---
This page is auto-translated from [/nishio/🤔原寸でスクリーンショットを作る](https://scrapbox.io/nishio/🤔原寸でスクリーンショットを作る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.