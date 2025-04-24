---
title: "Stable Diffusion's prompt will be a 77 x 768 dimensional tensor"
---

- ![image](https://gyazo.com/9b56949eefcc9f7f031b74a847a68d1b/thumb/1000)
py

```
x = model.cond_stage_model.encode("a painting of a black cat with yellow eyes, a color pencil sketch by Betye Saar, deviantart, folk art, creative commons attribution, chalk art, charcoal drawing")
y = torch.clamp((x + 1.0) / 2.0, min=0.0, max=1.0)
Image.fromarray((255. * y[0]).cpu().numpy().astype(np.uint8)).save("token.png")
```

- [[Black Cat 42]]
- By the way, if the query is empty
    - ![image](https://gyazo.com/7b785e7dae25478475843a325f78742a/thumb/1000)

---
This page is auto-translated from [/nishio/Stable Diffusionのpromptは77×768次元のテンソルになる](https://scrapbox.io/nishio/Stable Diffusionのpromptは77×768次元のテンソルになる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.