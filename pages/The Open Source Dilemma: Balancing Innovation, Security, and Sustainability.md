---
title: "The Open Source Dilemma: Balancing Innovation, Security, and Sustainability"
---

[The Open Source Dilemma: Balancing [[innovation]], [[security]], and [sustainability

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
Kazuho points out that the indiscriminate addition of features and dependencies in OSS projects creates security risks, that dedicated contributors are needed, and that the continuous addition of new features is essential to the success of OSS. He also warns that the ease of publishing and sharing OSS contributes to improved quality, but also allows the spread of security vulnerabilities.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Kazuho suggests that this incident does not indicate an overall exhaustion or decline in the efforts of the OSS community, but rather reflects a broader problem with OSS adoption and maintenance.

Furthermore, he criticizes the indiscriminate addition of features and dependencies to OSS projects and uses systemd and its integration with sshd as a case study. according to Kazuho, the attack on sshd was possible because the distribution added systemd-inotify support to sshd, which, according to Kazuho, was made possible by the unintentional introduction of a vulnerability via xz (liblzma). He argues that systemd's approach of supporting both traditional detached daemon management and its enhanced mode contributes to complexity and potential security issues, and that a more restrained approach in adding features and dependencies can mitigate such risks We suggest that a more restrained approach in adding features and dependencies can mitigate such risks.

Kazuho also mentions the risks inherent in shared libraries, noting that adding dependencies on these libraries may allow arbitrary code execution by executing initialization code that is executed at load time. This vulnerability also extends to indirectly loaded libraries, amplifying the potential for security breaches.

Despite these criticisms, Kazuho acknowledges that continuous development and innovation are necessary to ensure the spread and success of OSS. He references a statement by Yukihiro Matsumoto (Matz), founder of Ruby, about the importance of "keeping swimming" and remaining relevant and useful by actively addressing new challenges and continuing to generate "noise.

Finally, Kazuho reflects on the dual nature of the openness and ease of sharing of OSS as both a strength and a potential weakness. While this openness promotes cooperation and quality improvement, it also permits the rapid dissemination of flawed or vulnerable software. However, he suggests that the very act of sharing source code without the expectation of immediate profit improves quality, thereby contributing to the overall value and sustainability of OSS projects.

Through these observations, Kazuho offers a multifaceted perspective on OSS project management, the balance between innovation and security, and the broader implications of the open nature of OSS for software quality and community resilience.

> [kazuho](https://twitter.com/kazuho/status/1774580822210965651) Personally, I don't think it's exhaustion, I think it's inevitable due to the nature of OSS. If it is commercial software, if the maintenance cost is not worth it, it will not be released in the first place, and if it becomes difficult to maintain, it will be closed....
>  In other words, it is a problem for those who adopt third-party OSS
>  >kinu: xz backdoor, this is numbing...
>  The attacker also forked zstd and lz4, which could have been next. the OSS world is tired and cannot sustain itself without welcoming dedicated contributors with technical skills. The fundamental risk is there: hooking from ifunc resolvers and being able to observe performance differences under specific articles.
>  [https://openwall.com/lists/oss-security/2024/03/29/4…](https://openwall.com/lists/oss-security/2024/03/29/4…)


> [kazuho](https://twitter.com/kazuho/status/1774583847352750106) So, I think the countermeasure is not to easily increase the number of functions and dependencies, and if you do, make plug-ins and separate permissions. I think the reason for the attack on sshd this time is that systemd is the opposite of that, a culture of "I want to do this and I want to do that". In the first place...

> [kazuho](https://twitter.com/kazuho/status/1774587246722847216) 1. this time, I was able to create a backdoor to sshd via xz (liblzma) because distro companies added systemd-inotify support to sshd. systemd-inotify support to sshd.
>
>  2. systemd-inotify is a mechanism to notify the completion of daemon startup, but it "enhances" the management of daemons that are detached in the old fashioned way. If the daemon does not detach, it is not needed...

> [kazuho](https://twitter.com/kazuho/status/1774587248706777578) ... systemd should have been unified and guided to the non-detaching method, but chose to do "this and that" by supporting both methods and "enhancing" the detaching method as well.

> The systemd-inotify protocol is about 10 lines even in the original implementation, but it is provided as a library (libsystemd). I provided it as
>  4. * systemd depends on liblzma for log compression, but external command linking is sufficient for that (and wasn't that more flexible?).

> [kazuho](https://twitter.com/kazuho/status/1774587252527796239) The result of all these factors is that liblzma is loaded through libsystemd at ssh startup, and the liblzma attack The condition that the code works was established.

> [kazuho](https://twitter.com/kazuho/status/1774594811099779527) What is often overlooked is that shared libraries (.so) can embed initialization code to be executed at load time, so adding a dependency on a library The moment you add a dependency on a library, you are allowing arbitrary code execution even if you do not call that library (and this includes libraries that are loaded indirectly).

> [kazuho](https://twitter.com/kazuho/status/1774601465669234750) However, even if this view is correct, in order to spread and succeed as OSS
>  @yukihiro_matz
As > pointed out, it's important to "keep swimming" (keep working on new things and making noise), and adding new features is the solution...
>  >kazuho: So, I think the countermeasure is not to easily increase the number of functions and dependencies, or if you do, to make it a plugin and separate the permissions. In the first place...

> [kazuho](https://twitter.com/kazuho/status/1774930613679890710) Put another way, the advantage of OSS over commercial software is that it can be shared openly without second thoughts. Even if OSS is a bad currency with inferior quality, it is getting rid of commercial software which is a good currency.
>  In fact, giving up monetization allows source code sharing, which results in quality improvement.
>  >kazuho: Personally, I don't think it's exhaustion, I think it's inevitable due to the nature of OSS. If it is commercial software, if the maintenance cost is not worth it, it will not be released in the first place, and if it becomes difficult to maintain, it will be closed....
>  In other words, it is a problem for those who adopt third party OSS x.com/kinu/status/17...


---
This page is auto-translated from [/nishio/オープンソースのジレンマ：イノベーション、セキュリティ、そして持続可能性のバランス](https://scrapbox.io/nishio/オープンソースのジレンマ：イノベーション、セキュリティ、そして持続可能性のバランス) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.