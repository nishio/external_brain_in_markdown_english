---
title: "History of threading (or rather concurrency)"
---

First published [[Hatena2011-05-12]].

- Since when is a process flow called a "thread"?
    - At the latest, in 1965, we were calling in the Berkeley Timesharing System.
    - Prior to that, however, it was called "process". (even in Dijkstra's '65 paper).
        - This "process" (unlike what we now imagine as a Unix-like process) had shared memory and used semaphores for exclusivity.
- In 1970 Max Smith prototyped threads on Multics, which was an attempt to have multiple stacks in a single weight process.
- The originator of "threads" in programming languages is probably PL/I by IBM (1965-)
    - It had the syntax `CALL XXX (A, B) TASK;'.
    - This forks a thread for XXX.
    - I do not know if any compilers have implemented this feature.
    - It was made after careful study of how Multics was designed. For example, TASK calls are not mapped to processes, and memory is fully visible between threads.
    - However, Multics changed direction and IBM removed TASK functionality from PL/I.
- Then Unix emerges.
    - Unix used the word "process" to mean "thread + virtual address space".
    - (Incidentally, this notation in Unix is directly inherited from Multics.)
    - That is why "process" in the Unix sense has become a heavy thing that involves switching virtual address spaces.
    - The processes could not share memory because they each have their own individual address space, but they could interact with each other using pipes and signals.
    - The shared memory feature will be added much later.
- After a while, Unix users began to miss the old "memory sharing process.
    - This triggered the invention of the so-called "thread".
    - A thread is an "old-style process" that shares the virtual address space that a single Unix process has.
    - The term "lightweight process" was also used in contrast to the heaviness of the Unix process.
    - This distinction between "lightweight" and "heavyweight" processes can be traced back to the late 70s and early 80s, to the first "microkernels.



log
- I suddenly wondered when threads were invented and looked it up, but I'm not sure.
    - Linux has supported kernel threads since 2.6, so 2003, or is that surprisingly new? Of course user-level threads are probably even older, but I wonder when.
    - hideaki_t: NeXTSTEP (Mach 2.0?) had cthread.
    - atsuoishimoto: I first heard the term "thread" in OS/2 in the early '90s, I think.
    - This is 2004 > NetBSD 2.x+, and DragonFly BSD implement LWPs as kernel threads (1:1 model)
    - shidocchi: I learned about it when I was doing Mach source reading in my grad school lab.
    - October 2, 2001 Mac OS X v10.1...real-time threads, thread management, and
    - Single task -> cooperative multitasking -> preemptive multitasking (but one thread per process) -> so Unix connected processes with pipes -> but it's hard if the data to be shared is large -> let's make a more detailed execution unit in the process (which can share data) -> user thread -> kernel thread Kernel thread, and so on.
    - koyama41: pthread is 1995 and Solaris libthread is 1993, I thought UNIX origin was around that time [http://download.oracle.com/docs/cd/E19253-01/819-0390/mtintro-75924/](http://download.oracle.com/docs/cd/E19253-01/819-0390/mtintro-75924/) index.html
    - So Simula was 67 and the Actor model was 73 with Smalltalk in between.
    - I understand that the concept of monitor, introduced by Hoare in concurrent Pascal, became widely popular when it was adopted by Java, but as a result, it was used in inappropriate ways, and the actor model was brought back into the spotlight by Aran and Scalar. Also, I'm trying to figure out what's going on with closure.

- (I can't find the origin of the thread here, so the story is spreading into parallelism.)
    - I didn't Tweet this, but the time-sharing system was proposed in 1957, MIT's demonstration of the feasibility of a time-sharing system in 1961, and IBM's release of a commercial time-sharing system OS in 1967.
    - Dijkstra's semaphore in 1965, the actor model in 1973, Hoare's monitor in 1974, Java's release in 1995, and pthread in 1995. That seems to be about the time flow. I thought, "Threads are surprisingly young.

- ksmakoto: the days when we called it "lightweight process".
- kosaki55tea: I think the thread is older than the process. I can't find any references, though. I mean, if you have an OS that doesn't have virtual space management or something like that, you automatically only have threads.
- AkioHoshi @kosaki55tea @nishio Excuse me for sidestepping, but the basic concept of Mach operating system is "task and thread", which was introduced by Masami Hagiya at DECUS in Japan around 1987. native threading in UNIX was later From.
- uebayasi: I googled faqs.org right away, but Usenet is too old for you to know. uebayasi: I googled it and found faqs.org right away.
- `[2.2.3]` The history of threads [http://www.faqs.org/faqs/os-research/part1/section-10.html](http://www.faqs.org/faqs/os-research/part1/section-10.html)
- terazzo I googled and found that the idea of "the importance of being able to create a lightweight process with ease" came from [http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.41.3458&rep=rep1&type=pdf](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.41.3458&rep=rep1&type=pdf) It seems to have come from THOTH ([http://cseweb.ucsd.edu/classes/wi08/cse221-a/papers/cheriton79.pdf)](http://cseweb.ucsd.edu/classes/wi08/cse221-a/papers/cheriton79.pdf)) or something like that.

- A rough translation of The history of threads [http://www.faqs.org/faqs/os-research/part1/section-10.html:.](http://www.faqs.org/faqs/os-research/part1/section-10.html:.)
- When did we start calling a process flow a "thread"? We called it in the Berkeley Timesharing System in 1965 at the latest. But the concept of concurrency did not exist before then; it was called "process" then. (Even in Dijkstra's '65 paper.) This "process" (unlike what we now imagine as a process in the Unix sense) had shared memory and used semaphores for exclusions.
- In 1970 Max Smith prototyped threads on Multics, which was an attempt to have multiple stacks in a single weight process.
- The originator of "threads" in programming languages was probably PL/I (1965-) by IBM, which had the syntax `CALL XXX (A, B) TASK;'. This forks a thread for XXX. I don't know if any compilers implemented this feature; it was made after careful study of how Multics was designed. For example, TASK calls are not mapped to processes, and thread-to-thread memory is completely transparent. However, Multics changed direction and IBM removed the TASK feature from PL/I.
- Then came Unix, which used the word "process" to mean "thread + virtual address space. (Incidentally, this notation in Unix was inherited directly from Multics.) So "process" in the Unix sense became a heavy thing that involved switching virtual address spaces. Processes couldn't share memory because they each had their own individual address space, but they could interact with each other using pipes and signals. The shared memory feature was added much later.
- After a while, Unix users began to miss the old "memory-sharing processes". This triggered the invention of so-called "threads. Threads are "old-style processes" that share the virtual address space of a single Unix process. This distinction between "lightweight" and "heavyweight" processes can be traced back to the late 70s and early 80s, to the first "microkernel".

- Harmless old man: the so-called threads predate Mach, V (1981-).
    - If it's a hardware thread, it seems to have been around since the 1950s.
    - The first hardware interrupts seem to be UNIVAC I, which has only overflow interrupts, and NBS DYSEAC, which can do I/O interrupts.
- soda
    - Solaris libthreads and pthreads are very similar in specification to Mach's cthreads. I think it is safe to say that these are all straightforward bindings of Hoare's Monitor to C. (To put a finer point on it, there are some minor variants of Monitor's semantics...)

---
This page is auto-translated from [/nishio/スレッドの(というか並行処理の)歴史](https://scrapbox.io/nishio/スレッドの(というか並行処理の)歴史) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.