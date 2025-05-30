---
title: "GeForce Data Center Usage Restriction Case"
---

Organize for your own learning about the popular GeForce data center use restriction case.

Note: Although specific names are given as examples of companies that fall under Company A in the text, the discussion on this page is not about Company A in particular, but about whether NVIDIA's actions are unlawful in general terms, so please do not misunderstand me.
- [Sakura Dedicated Server High-Power Series Quad GPU Model Temporarily Unavailable | Sakura Internet](https://www.sakura.ad.jp/news/sakurainfo/newsentry.php?id=1828)

Assumed Facts
- The tangible "GeForce" has already been sold and ownership has already been transferred from NVIDIA to Company A.
- A separate license agreement is in place for the software "Device Driver", which is essential to the use of "GeForce". [this](http://www.nvidia.co.jp/content/DriverDownload-March2009/licence.php?lang=jp&type=GeForce) [previous version](http://archive.is/oMeH4)
- This change is not about a purchase agreement, but about a license agreement.
- A clause was added to the contract prohibiting its use in certain circumstances (in data centers).
- As a result, Company A is no longer able to use its own GeForce in certain situations
- NVIDIA insists that you use their other product, which is about 10 times more expensive, if you want to use it in certain situations.
- It is not easy to replace hardware made by other companies. This is because the software development environment for using that hardware is proprietary.
    - > Takeshi Izaki, NVIDIA Japan Corp.
    - > I don't think the competition is only about hardware, such as semiconductors. We have GPUs as hardware, but we have our own development environment called CUDA that allows us to maximize the performance of the GPUs. That is what makes us different from other companies.
        - [Why NVIDIA seems invincible in the AI era for the foreseeable future | AI4U](http://ai-4-u.com/cases/column-by-tsuruaki-yukawa-2) 2017-01
- Third-party TechCrunch opinion on NVIDIA's position. (I looked for actual market share figures but couldn't find them, so here they are instead)
    - > Nvidia's rapid growth is attributed to a surge in demand for GPUs for deep learning computer processing such as automated driving and natural language understanding.
    - > Nvidia is now an indispensable hardware source for many companies, especially startups trying to use artificial intelligence. Nvidia cards are indispensable] for models that take advantage of huge amounts of data and process it efficiently on the fly.
    - > Nvidia says "GPU computing in data centers has almost tripled year over year. This is an important indicator for Nvidia's future. There is no doubt that the company is [[currently]] [[at least]] the leader in supplying the hardware that deep learning requires.
        - [Nvidia's profit is surging, more than doubling over the previous year - machine learning and deep learning are driving it | TechCrunch Japan [http://jp.techcrunch.com/2017/05/10/20170509](http://jp.techcrunch.com/2017/05/10/20170509) nvidia-is-surging-after-its-income-more-than-doubled-year-over-year/] 2017-05
- NVIDIA's market share is 82%.
    - It's not limited to Deep Learning applications, and it's a bit old, but it's a good reference.
    - [Nvidia graphics cards record 82% market share...AMD continues to struggle](https://damonge.com/p=6423)

question
- Is this NVIDIA conduct tortious?".

consideration
- Whether or not this constitutes "abuse of a superior bargaining position" under [[antitrust law]] has already been discussed here.
- Claim A [Terms Change Restricts GeForce's Use of Data Centers | IT Law/Competition Law](http://itlaw.komazawalegal.org/?p=167)

> Article 2
> 9 The term "unfair trade practices" as used in this Act means any of the following acts
> 5. Taking advantage of the superiority of one's position in a transaction over the counterparty, and committing any of the following acts unreasonably in light of normal commercial practices
> (c) Refusing to accept the goods pertaining to the transaction from the counterparty, causing the counterparty to take back the goods after receiving them from the counterparty, delaying payment of the consideration for the transaction to the counterparty or reducing the amount thereof, or otherwise setting conditions of the transaction to the disadvantage of the counterparty, or change the terms of the transaction or conduct the transaction in a manner disadvantageous to the counterparty to the transaction.

- requirement
    - Taking advantage of the superiority of one's bargaining position over the other party,
    - unreasonable in light of normal business practices,
    - Change the terms of a transaction to the detriment of the other party to the transaction

In the above allegation A, referring to the Fair Trade Commission's [Antimonopoly Law Approach to Abuse of Superior Bargaining Position](http://www.jftc.go.jp/hourei.files/yuuetsutekichii.pdf), the following criteria are introduced for "taking advantage of the superiority of one's own trading position over that of the other party, in a manner that is unreasonable in light of normal The following criteria are introduced for "unreasonably in light of normal business practice".
- In such a case, "If KT makes a request, etc. that is extremely disadvantageous to Paygate, but Paygate has no choice but to accept it, because the difficulty of continuing business with KT would be a major obstacle to the management of Paygate.
- "We will comprehensively consider the degree of dependence of JQA on KT, KT's position in the market, the possibility of a change in JQA's business partners, and other specific facts that indicate the necessity of doing business with KT."

Claim A does not appear to "consider the totality of the specific facts" in this case.

As per the above facts
> Unique software development environment to use the hardware, which prevents easy migration to other companies' products.
It is clear that if it becomes difficult to continue business transactions due to the

Also, NVIDIA's market position and the need to do business is described in the words of TechCrunch as follows:.
(It would be nice to have numerical data, so please let me know if you know.)
> It is now an indispensable source of hardware for many companies, especially startups that are trying to use artificial intelligence.
> Nvidia's cards are essential for a model that uses vast amounts of data and processes it efficiently on the fly.
> Nvidia says "GPU computing in data centers has almost tripled year over year. This is an important indicator for Nvidia's future. The company is certainly the leader (at least for now) in supplying the hardware that deep learning requires.

So, by combining the above facts with the argument up to this point in Claim A, NVIDIA's conduct constitutes an "unfair trade practice".

So far I have looked at claim A and thought about the route of using the Unfair Competition Prevention Act. The author would like to consider the route of using the Civil Code, but for now, I will disclose it here so far.

-----
There are two types of damages: damages for default (Article 415) and damages for tort (Article 709), but I don't think we can go so far as to say that "NVIDIA had promised to allow the data center to continue to use it" in this case, so I will focus on damages for tort.

> Chapter V Torts
>  (Damages for tortious behavior)
> Article 709 Any person who intentionally or negligently infringes the rights or legally protected interests of another shall be liable for damages resulting therefrom.
requirement
- 1: Intentionally or through negligence
- 2: Infringement on the rights or legally protected interests of others
effect
- liable to compensate for damages incurred

The act of "adding a clause prohibiting use in a data center" is clearly intended to intentionally prevent "use in a data center." Therefore, requirement 1 is satisfied. The issue is whether "use in the data center" was a right or legally protected interest of Company A.

I'm still trying to sort it all out, but here's the zap.
- It is common business practice to assume that when an object is bought or sold, the buyer may use the object.
- When a purchase or sale of an object was made, software essential to the use of that object was licensed free of charge.
- At the time the sale was consummated, NVIDIA did not prohibit the use of its software in the data center.
    - No Guarantee" is not "Prohibited."
        - [Official Twitter claim at](https://twitter.com/nvidiaaijp/status/943141204744585222)
            - > [[Notice]] The use of GeForce/TITAN-based products in data centers has long been non-guaranteed. In that sense, we have refused to use them for data centers or cloud services, but this does not preclude their use in university laboratories, etc. The latest NVIDIA TITAN V presented at NIPS is also an ideal product for HPC and deep learning.
        - As for "no guarantee for use at the data center," it is generally accepted that "no guarantee" is a different concept from "prohibition," and is interpreted to mean "not actively guaranteed, but available for use at your own risk.
        - In fact, in Article 6.1 of the license, NVIDIA itself expressly states that it "makes no warranty of any kind. If one were to argue that "no warranty means prohibition," then this license would have prohibited any use.
            - > 6.1 No Warranties. to the fullest extent permitted by applicable law, the software is provided "as is" and nvidia and its suppliers disclaim all warranties of any nature or kind, whether express, implied or statutory, relating to or arising out of the software, including, but not limited to, implied warranties of merchantability, fitness for a particular purpose, title and noninfringement. NVIDIA and its suppliers disclaim all warranties of any nature or kind, whether express, implied, statutory, or otherwise, including, but not limited to, implied warranties of merchantability, fitness for a particular purpose, title, and non-infringement.
    - Buyers naturally think "I can use what I buy in the data center".
- To revise the license of software that is essential for the use of the thing after the purchase agreement has been executed, and to prevent the use of the thing, would undermine the benefit of "being able to use the thing" that the buyer anticipated at the time of the purchase agreement.
- This interest should be legally protected.
    - incident involving a public bath that occurred after a public bath that was rented by a university student
    - > (1) The interest of a person who believes that his/her legal conception requires that he/she be provided with a remedy for the infringement based on tortious behavior
    - Even if it is not expressly stated as a legal right, if there is an infringement of a benefit for which the judge feels that "relief should be granted for this infringement," the act of infringement of that benefit may be held to be a tort and relief may be granted

Very similar cases
- [Sony to pay compensation for removing PS3's "ability to install Linux and other operating systems" - GIGAZINE](https://gigazine.net/news/20160622-sony-ps3-linux/)
- Sony has agreed to pay compensation to approximately 10 million users who were harmed by the 2010 update in a lawsuit over Sony's removal of the ability to install Linux and other operating systems from the PS3.
- factual arrangement
    - The tangible "PS3" has a purchase agreement and ownership has already been transferred from Sony to each individual.
    - Updates were distributed for software running inside the PS3 [official announcement](http://www.jp.playstation.com/info/support/sp_20100329_ps3.html).
        - The claim is that this is a response to problems caused by security vulnerabilities.
            - Apparently there was a reference to "content piracy" in the courtroom. (Hearsay)
            - By installing an operating system such as Linux, the company attempted to destroy the possibility of infringing the copyright of the content by using its functions (interpretation).
        - Application of this update was optional.
        - However, if the update is not adapted, access to the PlayStation Network will be impossible, making it impossible to play games online, for example.
- Sony is much better off in this case than in the NVIDIA case (subjective opinion of the author).
- It is possible to "install Linux or other software" and "pirate content through it" on a PS3 before the update, and it makes sense to try to stop piracy of the latter.
- However, the fact that they stopped "installing Linux and other software" as a means of doing so was seen as problematic.
- The removal of "the ability to install Linux and other software" from a PS3 after transfer of ownership constituted "infringement of another person's rights or legally protected interests" and damages were to be awarded.
    - (Of course, this case is U.S. law, so the text is different.)


On the other hand, think about how you would argue if you were on NVIDIA's side.
- Sure, we made a deal to sell GeForce, but that only gives you ownership of the thing.
    - I don't care if it works or not.
    - You just made the wrong decision when you bought it because you thought it was something you could use.
- Device drivers are my property, and I am free to decide under what conditions I want to license them.
    - If you are dissatisfied, don't use it.
    - Just because at this point in time (with no incentive for other companies to develop them by providing them free of charge) you have only one choice of device drivers, there is no reason why you should have to use it. If you are dissatisfied with the contents of the license agreement, you can make your own device drivers or buy them from other suppliers (which are not available).
        - I feel like they are taking advantage of their 100% monopoly position regarding device drivers on GeForce...
        - The scorched-earth strategy of free distribution is what created that monopoly position.
- Hmmm, the "if you're not happy, make your own devadora" theory makes a certain amount of sense.
    - Except from an antitrust perspective.
    - Given the PS3 case, NVIDIA's side of the argument appears to be unfavorable.

Summary so far
- I support the position that the legally protected interest is being intentionally harmed, but I guess I'll have to let the courts decide.
- It would be good if Company A sued, saying, "You should compensate us because the unavailability of GeForce caused damages equivalent to the cost of purchasing GeForce and the profits of the business that had been earned by using GeForce in the GeForce data center.
    - Pointing out that Article 3 of the license is obnoxious.
    - > defensive suspension. If you initiate or participate in any legal proceeding against NVIDIA, NVIDIA may, in its sole discretion, suspend or terminate all licenses and all other rights granted under this License during the pendency of such legal proceeding. NVIDIA may suspend or terminate all licenses and all other rights granted under this License at its sole discretion during the pendency of such legal proceedings.
    - ref [[Intellectual Property Technician Level 1 28th Q20#5a128386aff09e0000bf2b9a]].
- I feel like the conclusion is kind of conventional.


Other Topics
- 'Even the previous license prohibited rentals!' Regarding the claim that
    - > No Rental. Customer may not rent or lease the SOFTWARE to someone else.
    - Since it is clearly stated as software rental, hardware rental is not restricted.
    - Rent the hardware in a pre-driver-installed state, and each user can agree to the EULA and download the drivers on their own.
    - Rather, is the act of providing an AMI with drivers installed on Amazon EC2 or something else okay?
- The license presented when downloading the driver from [https://www.geforce.com/drivers/license](https://www.geforce.com/drivers/license) does not have a data center clause, so if you download it from here, you can use it in the data center without violating the new license
- "Does a copyright owner have an injunctive right against a user if the user's continued use of legally obtained software results in lost profits to the copyright owner?"
    - The copyright holder does not occupy the right to use the software, so there is no right to demand an injunction.
- If the user can claim damages for the user's continued use of the old license, can the user apply to the court for a stay of use with the goal of preventing further damages?"
    - First, in order to be able to claim damages, the user's act of using the old license must be a tort.
    - The issue is whether the user is undermining a benefit that deserves legal protection on the part of NVIDIA.
    - According to the Law Encyclopedia, the principle in Japan is to make a claim for damages after the fact, and the right to demand an injunction is only granted on a limited basis by individual laws. Therefore, there is no right to demand an injunction in this case.
- What is the difference between a web service provider terminating a service?
    - Where tangible goods are bought and sold in advance.
    - In addition, many web services have a clause in their terms of use that reads something like "This service may be suspended, discontinued, or modified at any time without prior notice to you.

---
This page is auto-translated from [/nishio/GeForceデータセンター利用制限事件について](https://scrapbox.io/nishio/GeForceデータセンター利用制限事件について) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.