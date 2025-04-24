---
title: "Mutual reach"
---

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>In [[HDBSCAN]], [[mutual_reachability_distance]] ([[Mutual reach]]) and [[core_distance]] ([[core distance]]) are important concepts for identifying the structure of a cluster.

core_distance:
- core_distance(a) is a measure of the density of a point a.
    - core_distance(a) is a distance that indicates "how many other points are gathered around point a".
    - Specifically, it is the distance of the smallest radius such that a radius centered at point a contains a number of points at least equal to the "minimum cluster size" (e.g., 5 points).
    - The shorter this distance is, the more densely packed other points are around that point a. Conversely, the longer the distance is, the less dots are around it and the more sparse it is.
- The more dense a point is in a region, the smaller the core_distance will be, and the more sparse a point is in a region, the larger the core_distance will be.

mutual_reachability_distance:
- mutual_reachability_distance(a, b) represents the "mutual reachability distance" between two points a and b.
- This is defined by the following equation
- $\text{mutual\_reachability\_distance}(a, b) = \max(\text{core\_distance}(a), \text{core\_distance}(b), \text{distance}(a, b))$
- In the above equation, the greater of core_distance(a) and core_distance(b) and the maximum linear distance distance(a, b) between a and b are chosen.
- Thus, we evaluate whether points a and b are reachable from each other beyond the low-density region.

Thus, HDBSCAN uses mutual_reachability_distance to evaluate the connections between clusters and flexibly forms density-based clusters.

![image](https://gyazo.com/4bb0478e2078205e86bf6de9dbadb64b/thumb/1000)
Unlike normal distances, the distance between green and red in low-density areas is stretched beyond the original distance by the long green core distance, preventing clusters from being connected

---
This page is auto-translated from [/nishio/相互到達距離](https://scrapbox.io/nishio/相互到達距離) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.