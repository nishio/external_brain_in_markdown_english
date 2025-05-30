---
title: "The Incremental Garbage Collection of Processes"
---

[PDF](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=0236335b815ef41e86f0fe41e53a2acc1d4742f6) 1977
The paper proposed a concept that has now become famous in the form of JavaScript Promise.
- If the user gives an expression, "future" is returned immediately.
- This promises to "provide value later"
- When an explicit value of future is required, such as + for a primitive, the value is available immediately if it is complete, or wait until it is complete if it is not





This paper examines several issues related to argument evaluation order, called "future" order, which is different from call-by-name and call-by-value.
In call-by-future, each formal parameter of a function is bound to a separate process (called "future") dedicated to evaluating the corresponding argument.
This mechanism has been shown to increase the expressive power of the language by allowing fully parallel evaluation of arguments to functions.
An approach to the problem that arises in this context is to address the issue of a future that was considered relevant at the time of its creation, but becomes irrelevant when it is ignored in the body of the equation to which it was bound. The problem of irrelevant processes also appears in multiprocessing problem-solving systems, where multiple processors begin processing the same problem using different methods and return the first finished solution. This parallel method strategy has the drawback that the process examining the losing method must be identified, stopped, and reassigned to a more useful task.
The solution we propose is garbage collection. We propose that the goal structure of the solution be represented explicitly in memory as part of graph memory (like a heap in Lisp) so that the garbage collection algorithm can discover which processes are doing useful work and which can be recycled for new tasks.
An incremental algorithm for unified garbage collection of storage and processes will be described.

> This paper investigates some problems associated with an argument evaluation order that we call "future' order, which is different from both call-by-name and call-by-value. In call-byfuture, each formal parameter of a function is bound to a separate process (called a "future") dedicated to the evaluation of the corresponding argument. This mechanism allows the fully parallel evaluation of arguments to a function, and has been shown to augment the expressive power of a language.
>  We discuss an approach to a problem that arises in this context: futures which were thought to be relevant when they were created become irrelevant through being ignored in the body of the expression where they were bound. The problem of irrelevant processes also appears in multiprocessing problem-solving systems which start several processors working on the same problem but with different methods, and return with the solution which finishes first. This parallel method strategy has the drawback that the processes which are investigating the losing methods must be identified, stopped, and reassigned to more useful tasks.
>  The solution we propose is that of garbage collection. We propose that the goal structure of the solution plan be explicitly represented in memory as part of the graph memory (like Lisp's heap) so that a garbage collection algorithm can discover which processes are performing useful work, and which can be recycled for a new task.
>  An incremental algorithm for the unified garbage collection of storage and processes is described.
>


More precisely, a future is a 3-tuple (process, cell, queue), where process is the virtual processor initialized to evaluate this argument expression in its proper environment, cell is a writable location in memory which will save the value of the argument after it has been computed to avoid recomputing it, and queue is a list of the processes which are waiting for the value of this future. A future's process starts evaluating its expression in the given environment. If any other process needs the value of this future, and the value is not yet ready, the requesting process enters the queue of the future and goes to sleep. When the value promised by the future is ready, its process stores the value into its cell, wakes up all processes waiting in its queue, and dies.
Henceforth, any process needing this future's value can find it in the future's cell without waiting or further computation.

---
This page is auto-translated from [/nishio/The Incremental Garbage Collection of Processes](https://scrapbox.io/nishio/The Incremental Garbage Collection of Processes) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.