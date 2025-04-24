---
title: "DBSCAN Revisited, Revisited: Why and How You Should (Still) Use DBSCAN"
---

[DBSCAN Revisited, Revisited: Why and How You Should (Still) Use DBSCAN: ACM Transactions on Database Systems: Vol 42, No 3](https://dl.acm.org/doi/abs/10.1145/3068335)
[PDF](https://www.khoury.northeastern.edu/home/vip/teach/DMcourse/2_cluster_EM_mixt/notes_slides/revisitofrevisitDBSCAN.pdf)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
This paper provides a rebuttal to the "DBSCAN Revisited" paper presented at SIGMOD in 2015. The main arguments are as follows:.
1. on the theoretical execution time limits of DBSCAN: 1.
    - The SIGMOD paper proved that DBSCAN cannot be performed in O(n log n), but that does not mean "computationally difficult" in practical terms
    - While many alternative methods are Θ(n²) or Θ(n³), DBSCAN is still a valid method for large data

2. problems of the experiment: 1.
    - The parameters used in the SIGMOD paper (especially epsilon) were inappropriately large
    - Showed that the original DBSCAN utilizing indexes runs faster when using a more appropriate smaller epsilon
    - Inadequate preprocessing of the data set, resulting in no significant clustering results

3. advantages of DBSCAN: 1.
    - Distance functions other than Euclidean distance can be used
    - Can be combined with various index structures such as R*-tree
    - Works efficiently in real applications

In conclusion, while the SIGMOD paper is valuable in that it presents a theoretical lower bound, it argues that the claim that "DBSCAN should not be used with large data" is not appropriate and that with the right parameters and indexes, DBSCAN is still a competitive algorithm. We agree.
---
This page is auto-translated from [/nishio/DBSCAN Revisited, Revisited: Why and How You Should (Still) Use DBSCAN](https://scrapbox.io/nishio/DBSCAN Revisited, Revisited: Why and How You Should (Still) Use DBSCAN) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.