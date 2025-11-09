---
title: "Three types of multidimensional benchmarks"
---

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
Multi-objective benchmark
- Abstract: A framework for evaluating model performance from a pareto improvement perspective by simultaneously presenting multiple indicators O = {o₁,...}.
- the key
    - All indicators are published separately and weighted by commensurating function f as needed.
    - To visualize the trade-offs between indicators, the entire "front" is shown without collapsing to a single score.
- Benefits: Explicit negotiation of implicit agreements such as usefulness vs. harmlessness.
- Challenges: Large number of indicators increases the cost of measurement, and design decisions on which indicators to include are heavy.

Trade-off steerable benchmark
- Abstract: We measure whether a single model can be induced to an arbitrary steering commensurating function ℱ (e.g., linear sum w-O) during inference.
- the key
    - Evaluate the steerability with which the model can produce an optimal response according to different weightings f ∈ ℱ.
    - Example reward: ∑ ∑ f∈ℱ₎ f(ℳ_f) - sum the performance at each weight.
- Benefits: Guaranteed flexibility to dynamically adjust for each user/circumstance after deployment.
- Issue: Incompatible with value incommensurability (the philosophical position that value is not interchangeable).

Jury-pluralistic benchmark
- Abstract: A diverse set of evaluators jury / population J = {j₁,...} is explicitly specified, and individual utilities are integrated and evaluated by the welfare function w.
- the key
    - Each rater function jᵢ(x,y) is measured separately and aggregated with any w, such as Utilitarian or Rawlsian.
    - Transparency on "whose values are aligned" and adjustable fairness.
- Benefits: Useful for Democratic AI Alignment and consensus building support.
- Issues: cost of collecting evaluation data, welfare function selection biases such as tyranny of the majority and fanatical influence.


---
This page is auto-translated from [/nishio/多元的ベンチマークの3類型](https://scrapbox.io/nishio/多元的ベンチマークの3類型) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.