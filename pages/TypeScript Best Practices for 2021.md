---
title: "TypeScript Best Practices for 2021"
---

10 bad TypeScript habits to break this year
[http://startup-cto.net/10-bad-typescript-habits-to-break-this-year/](http://startup-cto.net/10-bad-typescript-habits-to-break-this-year/)
It's a good article with a set of reasons, but it's not a good list, so I've itemized it.

- 1: Use strict.
- 2: Use `? ` or use default arguments in the first place.
- 3: Use unknown instead of any as the type
- 4: Instead of typecasting with as, test with type guard and throw if the type is different.
- 5: Instead of casting an ad-hoc object that only partially satisfies the type requirement to any in your test code and using it as a mock, define a proper mock in one place and use it.
- 6: When an object has or does not have a certain property depending on its type, make it explicit in the interface what type it has, instead of making it an optional property with ? to make it an optional property, but make it clear in the interface what kind of property it has when it is present.
- 7: Avoid single-character variables because generics type variables are also variables.
- 8: Use explicit comparison operators instead of making non-true values conditional expressions
- 9: Instead of using `! to make a non-true value true, let's use the comparison operator explicitly!
- 10: Instead of equating null and undefined and using `! = null`, but distinguish between undefined and null and use `! == null` and `! == undefined`.

Below are my personal impressions
- 7: For type variables that have no meaning, I think a single-character variable is fine to state that they have no meaning.
    - Well, there aren't many opportunities to write type variables that don't have meaning.
- 10: I think this is a point of disagreement even among strong programmers.
    - There are both "don't use undefined, use null" and "don't use null, use undefined" and "don't distinguish between the two since there are both factions, use `! = See: [null and undefined - TypeScript Deep Dive](https://typescript-jp.gitbook.io/deep-dive/recap/null-undefined)
    - The article's assertion that, assuming TypeScript's strict mode, the compiler should check for the mistake between null and undefined, and there is no need to bother with loose conditional judgments, makes sense.
    - I didn't really understand this area when I started using TypeScript, but I was corrected early on when I created a project with create-react-app and it warned me about this by default. see: [no-eq-null - Rules - ESLint](https://eslint.org/docs/rules/no-eq-null)
        - I just tried it and it didn't warn me, but I'm not sure if I'm remembering it right or if they stopped warning me?
- 4, 6: I don't disagree that it is better to do this, but it is also much more work, so I think it is a trade-off.
- I have no objection to the rest.
- I tried [[I spent two days eradicating ANY...]].

---
This page is auto-translated from [/nishio/2021年のTypeScriptベストプラクティス](https://scrapbox.io/nishio/2021年のTypeScriptベストプラクティス) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.