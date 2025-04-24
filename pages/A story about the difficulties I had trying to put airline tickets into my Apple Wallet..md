---
title: "A story about the difficulties I had trying to put airline tickets into my Apple Wallet."
---

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>This sentence expresses the difference in perception between you and your wife regarding a certain system and your discussion about it.

The main points are as follows
- Actual use experience: in the process of a certain procedure, the husband and wife had different approaches and ideas.
- System design philosophy: Husbands believed that "systems should be more intuitive and easier to use," while wives tended to accept the reality that "old systems often have not kept up with new technology."
- Methods of Accessing Information: Husbands and wives also had different perceptions about how to find information. The husband believed that there should be a link from every page to the appropriate page, while the wife believed that the link was connected from the top page, no matter how far away it was.
- How information was organized: Husbands tended to prefer non-hierarchical ways of organizing information, such as Scrapbox, while wives preferred to organize information in a hierarchical way, such as a tree.
- Ideal vs. reality: Ideally, all information should be organized for easy access, but in reality such organization is often difficult.

This discussion highlights a general problem with system design and information access methods.

---
Interesting difference between my perception and my wife's perception, so I'll try to summarize.
My Point of View
- View your email on your PC
- Click "Click here for 2D barcode for boarding" (Screen A)
    - [https://booking.jal.co.jp/jl/dom-pbkg/AACCLoginFw](https://booking.jal.co.jp/jl/dom-pbkg/AACCLoginFw)
    - In fact, the GET parameter is loaded.
- Authenticate with your ticket number."
- Copy the 6-digit reservation number
- error
- Back to Mail
- I can't find my ticket number.
- Confused (wife tells me there must be other emails).
- View the email of the reservation → Copy
- →Verify (Screen A) → "e-Ticket Customer Receipt" page appears (Screen B)
- No flow line to sign up for Apple Wallet.
- Search by "JAL Apple Wallet
- [Can I receive my boarding pass via Wallet? [https://faq.jal.co.jp/app/answers/detail/a_id/20970/~/wallet%E3%81%A7%E6%90%AD%E4%B9%97%E5%88%B8%E3%81%AE%E5%8F%97%E3%81%91%E5%8F%](https://faq.jal.co.jp/app/answers/detail/a_id/20970/~/wallet%E3%81%A7%E6%90%AD%E4%B9%97%E5%88%B8%E3%81%AE%E5%8F%97%E3%81%91%E5%8F%) 96%E3%82%8A%E3%81%8C%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B%E3%80%82]
- >  [If you are using an iPhone
    - > Please select "Add to Wallet" on the "Issue Boarding Pass" screen after completing online check-in, and click the "Add to Apple Wallet" button to register.
- > [If you are using other terminals
    - > Select "Use Wallet" on the "Issue Boarding Pass" screen and send an e-mail. You can register for Wallet from the attached file.
- [[If you are using other terminals]] "Use Wallet" on the "Issue Boarding Pass" screen]
    - There is no "Use Wallet" on (Screen B)
    - [What does the ""Issue Boarding Pass"" screen mean?
    - I don't know!
    - My wife tells me to go to the JAL top page.
- Open the top page on iPhone
    - Reservation management? Boarding and check-in?
    - Reservation Management→Tickets → "Search Reservations".
    - If it is "boarding and check-in," it will be an e-ticket customer receipt, so it will stop in this future.
- I logged in after a bit of a struggle and found the Add to Wallet button!
Wife's Perspective
- (saying, "I'll probably look at it on my iPhone.") I'll look at my email on my PC.
- Click "Click here for 2D barcode for boarding" (Screen A)
- Authenticate with your ticket number."
    - We know that there is no "Ticket Number" in the email here, so click on "About Ticket Number".
    - [https://www.jal.co.jp/jp/ja/dom/boarding/ticketnumber/](https://www.jal.co.jp/jp/ja/dom/boarding/ticketnumber/)
- > Listing Location ... Purchase Completion Screen, Purchase Completion Email
- View the reservation e-mail → Copy → Authenticate (Screen A) → "e-Ticket Customer Receipt" page appears (Screen B)
- No flow line to sign up for Apple Wallet.
- Search by "JAL Apple Wallet
    - [[For iPhone users]]"
    - Decided "iPhone should be used."
- Don't know which page to go to? You should follow it from the top page.
consideration
- I said, "It's too difficult, it doesn't make sense that the necessary numbers are not in the e-mail, and if there is a page to open, it should be in the e-mail, so why do I have to follow it from the top page?
- My wife said, "I don't see what the difficulty is. The system where you make a reservation and get it emailed to you was created a long time ago, and Apple Wallet has only recently become available, so you can't expect the system to be logically thought out and optimally structured."
- I said, "I see."
- They both share the same perception of the ideal state of how the system should be designed, but my wife has an additional sense of resignation that the system in the world is often not the way it should be, and that it can't be helped.
- I said, "When the world's systems aren't well organized, why try to trace them from the top page?"
- Wife: "No matter how far away from the top page we think we are connected."
- Me: "That feeling may be related to my preference for hierarchical organization and not Scrapbox."
- My wife said, "You know, books have a table of contents, and the next best design is to maintain that tree."
- Ideally, there would be links from all pages to the appropriate page, but realistically, that maintenance cost cannot be expended.
    - Ideally, the user's cost of payment is O(1), but the provider must update all pages about it for each new addition
    - Then add to the tree with O(1)
    - If the tree is well organized, users can access it with O(logN)
    - Better than no access.
    - If the tree is well structured" often fails.
        - Especially when verbalizing something that doesn't have a very clear structure beforehand.
        - So when considered as a personal knowledge management tool, the Scrapbox approach wins over the tree approach.
---
This page is auto-translated from [/nishio/航空券をApple Walletに入れようとして苦労した話](https://scrapbox.io/nishio/航空券をApple Walletに入れようとして苦労した話) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.