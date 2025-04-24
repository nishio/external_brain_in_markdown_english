---
title: "Spreading an instance of a class does not duplicate the method."
---

ts

```typescript
class Greeter {
  greeting: string;

  constructor(message: string) {
    this.greeting = message;
  }

  greet() {
    return "Hello, " + this.greeting;
  }
}

const x: Greeter = new Greeter("world");
const y: Greeter = { ...x };
// Property 'greet' is missing in type '{ greeting: string; }' but required in type 'Greeter'.
```

[[TypeScript]]

---
This page is auto-translated from [/nishio/クラスのインスタンスをspreadしてもメソッドは複製されない](https://scrapbox.io/nishio/クラスのインスタンスをspreadしてもメソッドは複製されない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.