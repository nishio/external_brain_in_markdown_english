---
title: "Add a callback to be called after updating Paper.js"
---

Paper.js redrawing seems to be done asynchronously.
Is that in itself a good thing? in itself is a good thing?

- Set the Zoom value for Paper
- Erase Image
- Show Paper

If the process is called

- Image disappears
- Paper before zooming is displayed.
- A zoomed Paper is then displayed.

It looks terrible.
I wonder if Paper has a handler that is called after the end of the redraw or something, I want to delay turning off the Image.

The setZoom is causing the Matrix to change.
[https://github.com/paperjs/paper.js/blob/cc135eaba80943f78075f84ca430dc3152bd154e/src/basic/Matrix.js#L382](https://github.com/paperjs/paper.js/blob/cc135eaba80943f78075f84ca430dc3152bd154e/src/basic/Matrix.js#L382)
That calls for _changed

This is deleting and redrawing the entire screen.
[https://github.com/paperjs/paper.js/blob/cc135eaba80943f78075f84ca430dc3152bd154e/src/view/CanvasView.js#L132](https://github.com/paperjs/paper.js/blob/cc135eaba80943f78075f84ca430dc3152bd154e/src/view/CanvasView.js#L132)
I assume this is probably called asynchronously, but I'm not sure where it's being called.

DomEvent.[[requestAnimationFrame]] here.
[https://github.com/paperjs/paper.js/blob/cc135eaba80943f78075f84ca430dc3152bd154e/src/view/View.js#L222](https://github.com/paperjs/paper.js/blob/cc135eaba80943f78075f84ca430dc3152bd154e/src/view/View.js#L222)

So, as for my request for a callback on completion of drawing, I'd like to see a callback on completion of drawing.
[https://github.com/paperjs/paper.js/blob/cc135eaba80943f78075f84ca430dc3152bd154e/src/view/CanvasView.js#L142](https://github.com/paperjs/paper.js/blob/cc135eaba80943f78075f84ca430dc3152bd154e/src/view/CanvasView.js#L142)
We would like there to be a callback call here, but there is none at present.
→ Apply the monkey patch.

ts

```typescript
  window.app.paper.project.view.__proto__.update = function() {
      if (!this._needsUpdate)
          return false;
      var project = this._project,
          ctx = this._context,
          size = this._viewSize;
      ctx.clearRect(0, 0, size.width + 1, size.height + 1);
      if (project)
          project.draw(ctx, this._matrix, this._pixelRatio);
      this._needsUpdate = false;
      if(window.app.callbackAfterCanvasViewUpdate){
        window.app.callbackAfterCanvasViewUpdate();
      }
      return true;
  }
```

after having done ...
ts

```typescript
  window.app.callbackAfterCanvasViewUpdate = () => {
      image.style.display = "none";
      let canvas = document.getElementById("myCanvas") as HTMLElement;
      canvas.style.display = "inline";
      window.app.callbackAfterCanvasViewUpdate = null;
  }
```

It's like.

[[pRegroup-done-2019]]

---
This page is auto-translated from [/nishio/Paper.jsの更新後に呼ばれるコールバックをつける](https://scrapbox.io/nishio/Paper.jsの更新後に呼ばれるコールバックをつける) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.