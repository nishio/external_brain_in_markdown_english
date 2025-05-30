---
title: "Effective timing of unilateral license revision"
---

- In connection with the [[GeForce Data Center Usage Restriction Case]], the topic of when a software copyright holder unilaterally revises the license terms without the consent of its users, and when the revision takes effect, came up and is interesting to summarize.

One-line summary: When a user is presented with a license and then downloads the software, the user is deemed to have agreed to the license and it becomes effective. If the user has not downloaded the software after the license has been unilaterally revised, the license agreement has not taken effect in the first place.

First, the contract between the remote parties.
- Civil Code Part I General Provisions Chapter V Legal Acts Section 2 Declaration of Intention
    - >  (Declaration of Intent to Separate Persons)
    - > Article 97 A manifestation of intention to a person in a remote place shall become effective as from the time when the notice thereof reaches the other party.

- Civil Code Part III Claims Chapter II Contracts Section 1 General Provisions Subsection 1 Formation of Contract
    - >  (Time of formation of a contract between separatists)
    - > Article 526 A contract between bifurcated persons shall be formed when a notice of acceptance is issued.
    - > 2 If the notice of acceptance is not required by the applicant's manifestation of intention or by customary practice in the transaction, the contract is formed when there is a fact that should be recognized as a manifestation of the applicant's intention to accept the contract.
- So it is important to know when the old and new licenses arrived at the other party.

See [NVIDIA](http://www.nvidia.co.jp/content/DriverDownload-March2009/licence.php?lang=jp&type=GeForce) for a concrete example,
> NVIDIA GeForce Home > Driver Downloads > NVIDIA GeForce Software Customer Use License
> important notice - please read carefully: this nvidia geoforce software customer use license ("license") is owned by nvidia corporation and its subsidiaries ("nvidia") and governs your use of the geoforce software (including computer software and related materials) ("software") available for download here. This Agreement governs your use of the GeForce software (including computer software and related materials) ("Software") owned by NVIDIA Corporation and its subsidiaries ("NVIDIA") and available for download here. by downloading, installing, copying or otherwise using the software, you agree to be bound by the terms of this license. if you do not agree to the terms of this license, do not download the software.
It says, "I'm downloading this file," so let's assume that it is presented to you before you download it and you agree to it and download it.

In this case, NVIDIA's declaration of intent becomes effective when it appears on the screen of the person who intends to download, and a contract is formed when the user starts downloading in response (when there is a fact that should be recognized as a declaration of intent to accept).

So what happens if the user agrees to the old license, downloads and uses the software, and the licensor renews the license?

First of all, since the declaration of intent on the part of the licensor becomes effective when it reaches the user side, the question is whether it has reached the user side or not.
The most commonly used way to ensure that it has been received is by certified mail.
In this case, there is no such thing as "an obligation for the user to check daily what the latest license of the software is," so simply changing the license information posted on the Web cannot be considered as having reached a declaration of intent.
If you send a notification email and it reaches them, you can consider it reached.

Next, we would like to know if this declaration of intent terminates the "contract under the old license" that has already been executed. The license terms state the following with respect to completion of the contract

- > 3. Termination
- > This license shall automatically terminate if you fail to comply with any of the terms and conditions of this Agreement. In such case, you must destroy all copies of the Software and all of its components.
- > defensive suspension. If you initiate or participate in any legal proceeding against NVIDIA, NVIDIA may, in its sole discretion, suspend or terminate all licenses and all other rights granted under this License during the pendency of such legal proceeding. NVIDIA may suspend or terminate all licenses and all other rights granted under this License at its sole discretion during the pendency of such legal proceedings.

To put the situation in perspective.
- Old license agreement allowing use of the software has been executed.
- The user is using the software in a specific situation (in a data center) according to its contract
- Licensor declares intent for new license.
    - New license prohibits use in certain circumstances

That is, even if the new license prohibits use in certain situations, doesn't that mean that the old license "abides by the terms and conditions" of the old license agreement, so the old agreement is not terminated, and the software downloaded under the old license agreement can continue to be used?

I created a page to discuss what would happen if the license expired and I continued to use it, but surprisingly, the old license had not expired. Hmmm. Anyway, the rest of the story.

Suppose that the license has expired for some reason.
The right of reproduction is exclusive as the right of the copyright holder.
- (Japanese) Copyright Act
    - >  (Right of reproduction)
    - > The author shall have the exclusive right to reproduce his work.
But there is no such thing as a "right to use. Since the right to use a copyrighted work is not exclusive, the copyright holder has no right to tell a person who has obtained the work to "stop" using it.
So saying "don't download" before downloading (=reproduction) is valid, but saying "don't use" after downloading is not. There is no law on which to base that claim.

Furthermore, since the user is the "owner of a copy of the program work," he is allowed to reproduce it for use, etc.
- >  (Reproduction, etc. by the owner of a copy of a work of a program)
- > Article 47-3 The owner of a copy of a program work may reproduce or adapt the work (including reproduction of derivative works created thereby) to the extent deemed necessary for his/her own use of the work on a computer. (2) The owner of a work may However, this shall not apply where the provisions of Article 113(2) apply to the use of the reproductions pertaining to such exploitation.
- > 2 After the owner of a reproduction set forth in the preceding paragraph ceases to have the right of ownership of any of said reproductions (including reproductions made pursuant to the provisions of the said paragraph) for any reason other than loss (2) After the owner of a reproduction set forth in the preceding paragraph has ceased to have the right of ownership of any of the said reproductions (including a reproduction made under the same paragraph) for any reason other than loss, he/she shall not preserve any other reproduction unless the copyright holder has expressed his/her intention otherwise.
    - Incidentally, Article 113 is the provision for "acts deemed to constitute infringement. For example, exporting a copy.

Whether you can continue to have a copy when the license expires. The license states.
> This license shall automatically terminate if you fail to comply with any of the terms and conditions of this Agreement. In such case, you must destroy all copies of the Software and all of its components.
As long as you have agreed to the contract and downloaded (=reproduced) the material, you must destroy the reproductions if these conditions are met. Otherwise, it is a breach of obligation and you are subject to a claim for damages.
- civil code
    - >  (Compensation for damages due to default)
    - > Article 415 If an obligor fails to perform in accordance with the essential purpose of his/her obligation, the obligee may demand compensation for damages caused thereby. The same shall apply when the obligor has become unable to perform due to reasons attributable to the obligor.
In this case, the requirement clearly states "if the customer fails to comply with any of the terms and conditions of this agreement," so there is no reason why the user would have to break the contract if NVIDIA terminates it.

Can NVIDIA terminate this agreement?
> Subsection 3 Cancellation of Contract
> (Exercise of the right to terminate)
> Article 540 When one party has the right of rescission pursuant to the provisions of a contract or law, such rescission shall be made by a manifestation of intention to the other party.
The contract does not say that NVIDIA can terminate the agreement, and there is no law that gives NVIDIA the right to terminate the agreement, so it cannot be terminated without the agreement of both parties.
---
This page is auto-translated from [/nishio/一方的ライセンス改定の効力発生タイミング](https://scrapbox.io/nishio/一方的ライセンス改定の効力発生タイミング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.