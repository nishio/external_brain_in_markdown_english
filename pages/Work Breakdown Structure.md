---
title: "Work Breakdown Structure"
---

- Abbreviated as [WBS
- Subdivide large tasks into smaller ones.
    - Cannot [[estimate]] without dividing into distinct units
- Everyone does it unknowingly.
- It's also an important element of project planning, so there's a lot of consideration being given to it.
    - Example: There are procedure-type WBS and deliverable-type WBS in WBS

- History
    - PMI introduced it to the public in [[PMBOK]] in 1987, after it was used by the U.S. Department of Defense and NASA.
    - In Japan, [[DIPS Intellectual Productivity System]] talks about task breakdown in 1992
        - Not hierarchical.

Nishio's tips on how to create an organized WBS
- For example, many people probably write down "things to do" in the form of a GTD Inbox or a TODO list (if you haven't, do it first).
- Often, "Vague and large tasks" that "cannot be started immediately" are mixed in among them.
    - Example: "Write an explanation of how to solve the traveling salesman problem with a quantum computer."
    - To perform this work, we need to break it up (i.e., break it down) into smaller pieces
- Some may divide it up somehow.
    - Example
        - Write an explanation of how to solve the traveling salesman problem with a quantum computer.
            - A brief description of quantum computers
            - Explanation of the traveling salesman problem
            - Explanation of what kind of Ising model should be used
    - Another example
        - Write an explanation of how to solve the traveling salesman problem with a quantum computer.
            - A quick look at Reference X
            - Make a sticky note with excerpts of what you think you might need.
            - Put them together and come up with a story.
    - The former is a deliverable-type WBS and the latter is a procedure-type WBS
    - If you have the extra capacity, you can make both and check them against each other to reduce omissions.
        - In the above example, the procedure WBS is supposed to look at the reference material and think about the story, but the deliverables WBS has a tree that assumes that the story has already been decided, which is strange.

- The purpose of creating a WBS is not to divide tasks.
    - The goal is to be able to perform a task, and the task is divided as a means to achieve this goal.
    - So once you get to a size where you can execute it, you don't have to divide it any further.
    - The more detailed the division, the higher the management cost. It is necessary to master this sense of balance.




Notes before ----- summary: -----
- Task division skills improve as you repeatedly create a WBS.
    - Typical patterns are clarified → WBS standard
    - By referring to it, oversight and lack of development can be avoided.

- Able to clarify the scope of work
    - What is written is what you do, what is not written is what you don't do.

- trick
    - Make it with the intention of asking someone else to do it for you.
        - I'm a stranger tomorrow.
    - (1) >The only advantage Excel has over project management tools is its initial ease of use.
        - When the number of cases exceeds 100, it becomes unmanageable.
    - Writing Method
        - Approx. 100 pieces
        - Vague task titles are not good.
            - Detail down to about the title of the document that will be the output.
            - Structure elemental deliverables (what you make) as a guide
    - At first, we are not aware of deadlines.
        - Adjustments are made only after the ideal plan is in place, ignoring deadlines.
        - There is no way the ideal plan will meet the deadline.

    - Proper attention to dependencies.
        - Do not optimize anything but the critical path
    - Clarify who is in charge
    - Progress is measured by deliverables, not time frames.
    - WBS is not built by one person.
    - WBS detailed to a level that works effectively is information overload for the customer

- WBS consists of levels and elements
    - 100% rule: all child elements add up to equal the parent element
        - Check to see if there are any leftovers.

- There are two patterns of elemental decomposition: decomposition into objects and decomposition into work.
- The leaves are called work packages.
- 8/80 rule: break down into elements until the work package is approximately 8 hours or more, but no more than 80 hours.
    - One day to two weeks, that is.

- 7 x 7 rule: The number of child elements hanging from one parent element is limited to about 7, and the overall WBS level is limited to about 7 levels.
    - The first level is one at the top level, so with 7 child elements and up to 7 levels, we can get to 117649 terminations.
    - Personally, I think adding a limit on the number of pieces is a streak evil, but it's practically a limit.

- Work decomposition type WBS
    - A WBS of all the work required for the project
    - Also called project scope
    - Phase -> task -> work procedure... and it becomes a work manual style.
    - Easy to drop into schedule
    - The conditions for the completion of each task are unclear.
    - Different people have different images of the scope of work and
    - Risky to use a work breakdown WBS in a lump sum contract.
    - Potential to overlook necessary deliverables.
- Outcome-decomposed WBS
    - A WBS of all deliverables that are essential to complete
    - Also called product scope
    - Scope of responsibility is clarified.
    - Image of physical manufacturing divided into parts
    - WBS Workshop, published by PMI.
        - Recommended because it is easier to define the scope of responsibility and the conditions under which the work will be completed.
    - Need to know deliverables in advance.
    - May overlook work needed for intermediate products
- hybrid
    - Create both a work decomposition WBS and a deliverable decomposition WBS
    - Compare in order from the top level and check for omissions


- WBS is a tool for improving the efficiency of routine work
    - About 10% of non-routine work
    - Efficiency by making 90% of the work routine.


    - Problems with [to-do list
    - Checks for omissions do not work.
    - Information that was in your working memory when you wrote it is lost, and you lose the details of the task.
        - What are we doing this for?"
        - What exactly are we doing?"
        - Act as if notes for specific tasks are independent tasks
        - That would make me unmotivated.
    - TODO lists are suitable for small tasks with no dependencies between lines, where one line completes one task.
        - Not suitable for "projects" that consist of multiple tasks or are large enough to span multiple days
        - WBS handles it in a tree format.


- Rule: Make it top-down.
    - why？
    - Is it true that "bottom-up" means leakage?
        - Even top-down, you're going to get leaks.
        - People make mistakes even when they intend to be MECE.
        - Wouldn't it be more harmful to do it top-down and think "it's top-down, so there are no leaks"?
    - rebuttal
        - The importance of having both top-down and bottom-up perspectives Theory
        - List as many as you can think of, then organize them into a tree after the fact.
        - Note that the deliverable and work perspectives are mixed when created in a bottom-up manner.

- Save the WBS you created for reuse.

    - [[Gantt chart]]
    - Create in parallel with WBS of procedures and WBS of deliverables
    - Sticky only work packages.
    - Thinking side by side according to dependencies, etc.

- First, get the big picture.
    - With two WBS
- Next, fill in from the hips.
    - Parable of the Dishwasher
        - After you start washing dishes, you realize there is no place to put them.
        - First we should think "let's wash the dishes", "washing the dishes means wetting, scrubbing, and dusting", and "there is no place to dust".
    - If you fill in from the deadline and the critical path is not met, that's not possible.
    - Non-critical may be done at any time within the constraints
    - Not all tasks need to specify start and end dates and times
    - Estimates of duration should be clearly stated.
        - Train your own estimating skills by seeing how the final estimate deviated.

- References
    - [10 Rules for Preventing Project Flames - The Art of WBS Creation | Intelligent Net Blog](https://www.ini.co.jp/blog/2013/06/wbs10.html)
    - [Successful Project Success with WBS (1): Learn WBS and use it for estimation and progress! (1/2) - ITmedia Enterprise](http://www.itmedia.co.jp/im/articles/0910/13/news131.html)



---
This page is auto-translated from [/nishio/Work Breakdown Structure](https://scrapbox.io/nishio/Work Breakdown Structure) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.