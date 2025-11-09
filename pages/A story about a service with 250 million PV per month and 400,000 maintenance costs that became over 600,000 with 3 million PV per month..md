---
title: "A story about a service with 250 million PV per month and 400,000 maintenance costs that became over 600,000 with 3 million PV per month."
---

> [Peing_net](https://x.com/Peing_net/status/1959252696550002973) We respectfully apologize for any confusion this may have caused you.
>
>  Currently, we are losing nearly 500,000 yen per month in infrastructure costs alone, so we need to first optimize our infrastructure and review our inefficient code as soon as possible.
>  (I respect the former company that managed to continue to operate in that state.)
>  (2/3)
> [Peing_net](https://x.com/Peing_net/status/1959252698320314543) Also, the fact that the entire code is made in Rails is causing server load, and we plan to replace it with Go or Node, even partially. ...

> [sesere115](https://x.com/sesere115/status/1959484141986275599) As for the question box thing, I'm just saying, "Can't you make money using Rails?" I don't want to be misunderstood, so I'll just say that at the time I gave it to them (I forget the details), they should have had several million in the black every month. At any rate, at least 2 million should have been in the black.
>
>  So I think the failure of strategy and infrastructure is more essential.


> [sesere115](https://x.com/sesere115/status/1959478836883771886) Interesting topic that came up..,
>
>  At the time I was running the site, at 250 million PV/month, the server cost was 150,000 yen/month plus 150,000 yen/month for sending mail, for a total of about 300,000 yen (no matter how high it was, it should not have been more than 400,000 yen).
>  Since it was that amount of money with almost no optimization, I'm wondering if it's a "not a problem with Rails but a problem with the infrastructure" situation, like putting it on AWS when it's not needed or using it in a wealthy way and the egress fee jumped up (what features were added after the transfer? (I don't know what features were added after the transfer, so I'm just talking about the base features)
>
>  As a side note, when we originally designed the site, we had a policy of using Twitter to deploy both images and text, so that users would not access the site, and we were trying to keep infrastructure costs down by having Twitter bear the burden of controlling infrastructure costs (although we still had 250 million PV/month).
>
>  And I'm sure the infrastructure was done by conoha vps, and they don't charge egress fees there.
> [sesere115](https://x.com/sesere115/status/1959482445528776736) Not only this, but all aws are expensive, so I think adopting them is the last option and we should think about other means (vps parallelization/fly.io and other PaaS) first. I think we should consider other means (vps parallelism/fly.io or other PaaS) as a priority.
>
>  It's not realistic to use egeless expensive aws on an ad-based site where growing views = revenue, even if the service has a solid monetization structure.


> [kenn](https://x.com/kenn/status/1959672461588680942) You seem to be naive in your bottleneck analysis when you easily blame Rails.
>
>  I used to handle an API with 1 billion hits per month with Rails at a cost of about 300,000/month, but more than 1/3 of the cost was for the DB. I used to run an API with 300,000 hits/month using Rails, but more than 1/3 of the cost was for the DB.


> [Peing_net](https://x.com/Peing_net/status/1959506538437226550) ■Is Rails really the problem?
>
>  → I say this because the problem appears to be the load on the application server in terms of behavior, but I am still checking the details.
>  First of all, we consider it urgent to optimize queries, review DB, and make some screens static.
>  Since full refactoring is too expensive, only high-frequency and high-load APIs should go out.
> [Peing_net](https://x.com/Peing_net/status/1959506540378857875) In addition, there was 100 million PV/month at the peak.
>  Currently, we have 3 million PV/month, and we do not think this is the scale to write everything in a scripting language like Rails.
>  (Including PHP and Python, no disrespect intended to Ruby/Rails only)
> [Peing_net](https://x.com/Peing_net/status/1959506542342099375) ■What is it costing so much?
>
>  → Currently, the application server (Compute Engine) costs 200,000 yen/month, Cloud SQL (DB) costs 400,000 yen/month, and so on.
>  The DB is 3TB and the storage fees alone are exorbitant. It seems that they are also storing unnecessary data, so deleting that data will be an issue as well.


> [kenn](https://x.com/kenn/status/1959676721583849752) was actually 3 million PV/month...
>  The assumption that "this is not the scale to write in a scripting language" is triggered by this cute scale, as expected, I knew the bottleneck analysis was too naive.
>  Be careful not to delete all DB data at once, because it is very heavy and will kill you. In the future, partitioning should be introduced.
> [kenn](https://x.com/kenn/status/1959682831959126127) I think engineers whose primary mission is programming and not architecting systems tend to overestimate the difference between programming languages. In systems of a certain complexity, it is rather rare that the rate-limiting step of the whole process is the speed of program execution.

---
This page is auto-translated from [/nishio/月間2.5億PVで維持費40万のサービスが300万PVで60万以上になった話](https://scrapbox.io/nishio/月間2.5億PVで維持費40万のサービスが300万PVで60万以上になった話) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.