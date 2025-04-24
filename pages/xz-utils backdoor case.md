---
title: "xz-utils backdoor case"
---

[Everything I know about the XZ backdoor](https://boehs.org/node/everything-i-know-about-the-xz-backdoor)
[xz-utils backdoor situation](https://gist.github.com/thesamesam/223949d5a074ebc3dce9ee78baad9e27)

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>A summary of the xz-utils backdoor incident is as follows
- On March 29, 2024, a backdoor was discovered in the widely used compression software xz-utils.
- The backdoor is believed to have been planted by Jia Tan, the maintainer of xz-utils, who became involved in the development of xz-utils about two years ago and gradually gained its trust.
- The backdoor was very cleverly designed and was only triggered under certain conditions. The main targets were Linux systems using systemd and openssh.
- Once the backdoor is triggered, it will be possible to bypass ssh authentication and enter the system. However, no other effects are known at this time.
- Jia Tan also exhibited suspicious behavior, including using another account to strongly push a patch containing a backdoor.
- The main maintainer, Lasse Collin, was on vacation and could not stop Jia Tan's activities. Some have pointed out that the harsh conditions of open source developers are behind the situation.
- Jia Tan's GitHub account has been frozen and the backdoor removed, but other impacts are being investigated; numerous systems, including xz-utils, are being investigated and updated.
As described above, this was an attack from within by a developer with whom we have established a long-term relationship of trust, and it is an incident that once again highlights the vulnerability of open source software.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- A "Linux system using systemd and openssh" is a very major infrastructure of the digital society, and a "backdoor" that makes it "hackable" is like a master key that can open any door, to use a non-engineer's analogy.
- Fortunately, this time the workmanship was discovered before it was widely introduced, but some are concerned that there may be workmanship that has not yet been discovered due to successful hiding, based on the idea that "things that are easy to find will be found first.
- Others believe that the behavior of using compressed software, which is seemingly unrelated to the system to be penetrated and difficult to attract attention, as a clue, and then using the personal circumstances of the main maintainer to commit the crime after long-term trust-building behavior, suggests the existence of a sponsor, such as the state or an antisocial organization, for example, rather than a spontaneous motivation of a single individual. Some people believe that this is the case. There is no clear evidence to determine whether this is [[conspiracy theory]] or correct speculation.


> [dmikurube](https://twitter.com/dmikurube/status/1773975696526000129) Amazing. Three years of building trust and planting backdoors. It's like a thousand years of work to trick the demon tribe, but there's actually an incentive to do this... [Everything I know about the XZ backdoor [https://boehs.org/node/everything-i-know-](https://boehs.org/node/everything-i-know-) about-the-xz-backdoor]
> [dmikurube](https://twitter.com/dmikurube/status/1773979679810257118) The fact that the maintenance of these things is on the shoulders of individuals, and the fact that it was almost entirely the work of individual craftsmanship that detected them... What can I say?
> [dmikurube](https://twitter.com/dmikurube/status/1773981126643814479) But the fact that there was one of these, I guess I should see that there are others. Ugh.
> [dmikurube](https://twitter.com/dmikurube/status/1773983031025664412) In the open source culture, there are many people who say "I'm waiting for your contribution", but it is difficult to see examples like this. But when I see examples like this, it's difficult. But as a maintainer, I can't accept it so lightly.
> [dmikurube](https://twitter.com/dmikurube/status/1773983943001567495) (I am quite bitter about people who complain like that. Even if I am not the maintainer.)
> [dmikurube](https://twitter.com/dmikurube/status/1773986943933862360) In fact, with Embulk, if you can sneak in a little work, you can probably divert data from one company to another. I'm watching it carefully. Many plug-ins are out of our jurisdiction, though.
> [dmikurube](https://twitter.com/dmikurube/status/1773987824494370841) I try not to carelessly use third-party actions like GitHib Actions. It's a good target to do something. And typically, Gradle plugins...
> [dmikurube](https://twitter.com/dmikurube/status/1774035020199710776) "In April 2022, Jia Tan submits a patch via a mailing list. The patch is A new persona - Jigar Kumar enters, and begins pressuring for this patch to be merged." Wow. I guess those who pressure people to "merge this" should be classified as the same.
>  "In April 2022, Jia Tan submitted a patch via the mailing list. The patch is irrelevant, but the events that follow are irrelevant. A new persona - Jigar Kumar - comes in and starts pressuring us to merge this patch. Wow. I guess those who pressure you to "merge this" should be judged the same way.
> [dmikurube](https://twitter.com/dmikurube/status/1774035165444296802) "Soon after, Jigar Kumar begins pressuring Lasse Collin to add another In the fallout, we learn a little bit about mental health in open source.
>  "Shortly thereafter, Jigar Kumar began pressuring Lasse Collin to add another maintainer to XZ. As a result, we can learn a bit about mental health in open source" Hmmm...

> [izutorishima](https://twitter.com/izutorishima/status/1773959339629498628) wow, they spent 3 years contributing to xz-utils to win their trust and then put a backdoor in... too egregious! ......
>  I can only say that it was a coincidence that I found it, and if it had gone around to Ubuntu or something, I'd be scared to log in to any public server that sshd's out to without a password.

> [piro_or](https://twitter.com/piro_or/status/1774059039812645020) The [[colors.js]] debacle was about the developers themselves messing things up, not necessarily because it was open source, [[[WinGroove Incident WinGroove]], but it is a story that only open source can tell, where the developer has gained trust through contributions and even commit privileges, and then becomes an attacker.
> [piro_or](https://twitter.com/piro_or/status/1774061170259067265) WinGroove case, could it now be the subject of an investigation for unauthorized electromagnetic recording?

> [nishio](https://twitter.com/nishio/status/1774001859545674130) Given the law of "a fraud that is found is a fraud that is poorly covered up", you found a remote login backdoor in xz and dealt with it while you still can. I'm glad you were able to do it. ......, but it's more likely that a similar backdoor was planted in something that isn't known and is spreading.

> [Cryolite](https://twitter.com/Cryolite/status/1774300154566455736/photo/1)
>  ![image](https://pbs.twimg.com/media/GJ-URGkaIAALUI9?format=png&name=small#.png)

- [[The Open Source Dilemma: Balancing Innovation, Security, and Sustainability]]

[[Cybercrime]]
- [[cyber warfare]]

---
This page is auto-translated from [/nishio/xz-utilsバックドア事件](https://scrapbox.io/nishio/xz-utilsバックドア事件) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.