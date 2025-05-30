---
title: "Architected Agile Solutions for Software-Reliant Systems"
---

Boehm, Barry & Lane, Jo & Supannika, & Turner, Richard. (2010). Architected Agile Solutions for Software-Reliant Systems. INCOSE International Symposium. 20. 10.1007/978-3-642-12575-1_8.

How Much Architecting is Enough?
![image](https://gyazo.com/59270c68a9209b5ce7d26e4efe020777/thumb/1000)

left-most plan
- Red line is the percentage of time spent on preliminary design
- Black dotted line is the percentage of time spent redoing
- Green is the sum of
    - The three lines correspond to the number of lines of code
        - Preliminary design is not necessary for 10,000 lines.
        - At around 10 million lines, the time lost by redoing can be as much as 91%.
            - Therefore, it is reasonable to spend 40% of the time on preliminary design to lower the risk of redoing the project.

chart on the right
- black line
    - Average cost for a 100,000 line project
        - The thin one corresponds to the red line in the left figure, and the two thick ones to the green and black.
        - Redo cost, design cost, total cost
- red line
    - When design costs increase by 50% due to high specification variability.
    - Increased design costs
        - →Sweet spot moves to the left.
        - = less pre-design would be appropriate.
    - With a 50% increase in cost, the sweet spot moves from 20% to 10% (actually 15% because of the 50% increase).
- green line
    - 50% additional cost when problems occur due to lack of prior design
    - Higher redo costs
        - →Sweet spot moves to the right.
        - = Better to design more in advance.
    - Sweet spot moves to 30%.
        - However, about 5-10% of the area above and below is almost flat, so it is more of a "region" than a "spot".
        - Too few and the risk skyrockets when you come to the edge of the region.

- [[agile]]
- [[Sufficient Design]]
- [[Deadlines and estimation errors]]
- [[Agile estimating and planning]]

---
This page is auto-translated from [/nishio/Architected Agile Solutions for Software-Reliant Systems](https://scrapbox.io/nishio/Architected Agile Solutions for Software-Reliant Systems) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.