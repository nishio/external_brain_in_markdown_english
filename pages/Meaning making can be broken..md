---
title: "Meaning making can be broken."
---


How you interpret the facts (meaning) is only a view and can be broken
- However, it is a prerequisite to be able to trace "what kind of facts it is based on".

![image](https://gyazo.com/70d233abecaf54eed1a62a50d78ec08d/thumb/1000)

<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
Roger. I'll keep the abstraction but give it the feel of a "design principle".

slogan
References are reversible (can be returned) / Implications can be broken (cannot be returned)
→ This is guaranteed by the σ/ρ separation.

Symbolic correspondence (separation of roles)
- E: Original experience, original text, primary source material (including moya"[[material layer]]")
- S: Description, summary, classification, bundling, and visualization ("[[representation layer]]")
- σ : E → S (Table 1)
    - Transcribe "material" into "expression". It can be irreversible (summary, compression, interpretation can reduce information).
- ρ : S ⇢ E (regression)
    - Return from "expression" to "material" by reference. It does not have to be a perfect inverse mapping, but the reference path is necessary.
Goal: ρ∘σ ≈ Id_E (at least get back to the reference point)

What is/is not "reversible"?
- Reversible (absolutely protect) = See also
    - Anchor to the material, including source, location, time stamp, ID, hash, etc.
    - ρ is the implementation of the "path" following this anchor
- Irreversible (can be broken) = Implication
    - Summarizing, chaptering, clusters, aka bundling, weighting, shortest paths...
    - This is a view (S-side state). May be destroyed, overwritten, or recalculated.
Intuition: break the map projection / leave the latitude and longitude.

Abstract Architecture (Layers)
1. material layer (E): immutable. Non-writable.
2. reference layer (for ρ): anchor table of E ({source_id, offset/time, hash}...)
- Representation layer (S): "variable views" such as summary, relationship, quotient, layer, and path.
- Transformation log (σ columns): mapping sequence of operations that create S (for auditing).
constraints
- S→E is reference only (ρ); E must not be updated.
- S updates are destructive and OK (meaning making can be broken).
- Each time a new S is created, a string is added to the reference layer (maintaining the way back and forth).

What this separation brings
- Freedom to break: Trial-and-error in the way of bundling and separating to create "novelty".
- Responsibility: only S can be destroyed; E and references are protected
- Auditability: any S claim can be returned to E by ρ (can hit the source)

Abstract Checklist (minimum)
1. is there an anchor: {source_id, location/time, hash} for each claim
2. is the way back alive: 1-2 clicks/operations from any view to the material
3. is E invariant: the original material is not increased, decreased, or modified by view updates?
4. are the semantics independent: summary, bundle, and cluster exist only on the S side
5. will differences remain: S updates can be tracked in version/logs (who broke what)

Anti-pattern (abstract)
- Override the reference with semantics: leave only the summary text and discard the source (ρ dies).
- "Save as Formatted" of the material: Edit the original text to make it consistent (E dies).
- Lack of anchor unification: disparate reference formats for each separate display (outward and return are disconnected)

In a word.
You can "destroy" as much as you want with σ. However, we will always leave a "returnable" path with ρ.
As long as this dual structure is maintained, **[[novelty (patentability)]] (break) and [[trust]] (return) ** are simultaneously valid.
- [[Novelty and trust are compatible.]]

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Isn't σ invertible? Then f: S→S breaks a lot of things, but only ρ as an inverse map can be maintained without breaking, right?
- ![image](https://gyazo.com/70d233abecaf54eed1a62a50d78ec08d/thumb/1000)

<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
Good point. Bottom line--I'm not sure.
- In general, σ is not reversible (i.e., "representations" including summaries and abstractions drop information).
- However, if we separate the "reversible part" from the "irreversible part" in the design, we can make the composition you describe.

Decompose and consider (recommended design)
Divide σ into two steps:
1. σ_ref: E → S₀ (referentialization)
    - Just add an anchor (source_id, offset/time, hash) to the source material. Lossless.
    - → reversible here: ρ∘σ_ref = Id_E
2. σ_view: S₀ → S (implication)
    - Summarize, bundle, classify, visualize, etc. OK in lossy.
    - → It does not have to be reversible here.
The entire "representation" is then σ = σ_view ∘ σ_ref.
ρ is a S→E regression, but since it actually acts only on the anchor
We need only observe ρ∘σ_ref = Id_E and do not require the converse for σ_view.

f: Condition S→S (range that may be broken)
The transformation f on the semantic side may be broken, but observe the following
- Anchor conservation: ρ∘f = ρ (= reference is invariant)
- If this holds, then ρ∘f∘σ = ρ∘σ = Id_E (we can certainly return to E)
So the intent of your equation can be phrased this way:
ρ is the right inverse of σ_ref, and any implication transformation f on S makes ρ invariant (ρ∘f=ρ).
So no matter how much you break the signification, you don't break the referential reciprocity.

summary
- Is σ reversible?" → The reference part (σ_ref) is reversible, the semantic part (σ_view) is irreversible.
- Practical rule: Anchors always rotate (ρ∘f=ρ)/original material is invariant.
- This simultaneously establishes "freedom to break" (novelty) and "the way back" (auditability).

---
This page is auto-translated from [/nishio/意味づけは壊してよい](https://scrapbox.io/nishio/意味づけは壊してよい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.