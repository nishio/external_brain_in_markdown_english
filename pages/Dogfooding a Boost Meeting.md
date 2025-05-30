---
title: "Dogfooding a Boost Meeting"
---

from [[mitoujr2021]] 2021-06-04~2021-06-06

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I've actually been thinking for a few days about what would happen if the mentors [[dogfooding]] the Boost conference, but I've been so busy that I haven't been able to do anything, so I made a page anyway.

-----
- [[How to make a presentation video for the Boost Conference]]
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I read it again, but it doesn't say anything about what should be said or what the purpose of the presentation is, well, I guess it's communicated by communicating with the mentors.
- [[5 Tips for Creating a Communicative Proposal]]
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'll think about it as I look at this.
    - area
        - digital notebook
        - Information Sharing Tools
            - I'm wondering which one to use. If it is a notebook, it can be used mainly by one person, but if it is an information sharing tool, it would be strange to say "mainly used by one person".
        - Digital whiteboard
            - You can use it alone to get your head out of the clouds, or you can use it with multiple people.
            - Maybe not as "one of a kind" feeling as a notebook.
    - Objective.
        - To organize information
            - What do you mean "organize"?
        - Digital assists in situations that can be confusing when you're thinking in your head to help you get your head straight.
            - Is it strange that digital assistance is a means to an end, so it's not right to include it here?
        - The purpose of this service is to help people who are confused trying to think of complex things in their minds to become organized and clear.
    - means
        - Running in the browser
        - Sticky notes with pieces of information that can be dragged and moved.
        - Is this a common story so far?
        - Compared to existing
            - Important stickies can be made larger.
            - Stickies can be grouped and folded
            - Can be handwritten.
→"Write down what's in your head and drag it around to help organize it on the digital whiteboard Regroup2" (tentative)

> Let's find out what was created for a similar purpose as the proposal.
- Post sticky notes on the whiteboard.
- Move sticky notes and information cards on the desk.
- outline editor
- Miro
- Comparison
    - whiteboard
        - Good for information sharing among multiple people in the same physical location.
            - But as remote work progresses, problems arise.
            - Taking pictures of the whiteboard with a camera doesn't share very well with the remote.
            - It would be nice if the digital whiteboard could be shared with remote
                - But maybe this isn't directly related to the goal of "getting my head out of my ass."
        - For single use
            - Actually, the legible and accessible area of a vertical whiteboard is not very large due to height limitations.
            - The next "on the desk" has more sticky notes it can handle.
    - Sticky note on the desk
        - This is pretty good, or I used to use it myself.
        - discontent
            - Written on paper is difficult to search and reuse.
            - The effort of writing by hand on a paper sticky note is hard when you already have something written digitally.
            - This is a common problem with whiteboards as well, but they take up a lot of space, so you often have to clean up what you've laid out.
            - Bundling" allows "compression," but then the spatial arrangement is destroyed.
                - Regroup2 "Fold" will be restored to its original form.
    - outline editor
        - Bullet points to organize ideas.
        - The tree can be folded.
        - Low degree of freedom of placement
        - Less information can be displayed on one screen.
    - Miro
        - Online Shared Whiteboard Service
        - Sticky note functionality has also been added.
        - [https://kawazoezoe.com/miro-sticky-note.html](https://kawazoezoe.com/miro-sticky-note.html)
        - Hmmm, there are minor feature differences, but "why not just use Miro?" It's hard to say...
        - Maybe, but Miro is not specialized in organizing information, so there could be a difference there...
        - I'm getting the feeling you're not going to adopt anything.
        - I wouldn't be persuaded to at least give Miro a try...
                - [[Comparison of Miro and Regroup]]
- I feel that Miro is not good at all, but I need to explain why that is so that the audience can understand
    - Regroup is focused on organizing 100+ sticky notes as an assumption, maximizing the limited screen space.
    - I get the feeling that Miro is not suited for organizing sticky gaps, shadows, and other things like getting stuck on a limit and failing to import after a few dozen stickies.

- Well, aside from the comparison with Miro, consider what to do with the boost meeting if it were to be adopted.
    - The prototype is pretty much done, but there is no point in appealing to the public about it because it will just end with "it's done.
    - I think I'll focus on what I want to do and my immediate concerns.

- outline
    - What is this?
    - What to make it for.
    - What are you struggling with right now?

What is this?
- You're blurring the axis of whether it's a "digital whiteboard" for multiple people or a "digital notebook" for one person...
- I think the analogy to a whiteboard is rather misleading, since the envisioned use is to first put 100 sticky notes on it and then move them around.
- I wouldn't compare it to a notebook or a whiteboard...
- An AI that helps you organize by writing out what's in your head and dragging it around."
    - You can't do that.
    - AI is going to be too vague and picky.
    - But I'd like to assist there in the future.
- I'd say it's widely done up to the point of "moving stickies around to organize your mind," but there's a limit to the number of sheets and such due to the constraints of physical stickies and whiteboards.
    - This is like, for example, the kind of work you do on your PC now can only be done on the small screen of your smartphone.
    - Restrictions on video limit human intellectual production.
    - So technology needs to evolve in a direction that removes that limitation.
- Let's call it a "thought support tool."

- What to make it for.
    - The basic premise is that when organizing thoughts, it is very useful to put them on sticky notes and move them around as you think.
        - I need to be convinced here.
    - But there are some dissatisfactions with the current tool.
    - So we need better "tools for thinking".

- What I'm struggling with now
    - Can we assume that it's "for one person's use?"
        - The backend is Firestore, so casual collaborative editing is still possible, which is surprisingly convenient.
            - One person can both list on the wide screen of a PC and handwrite on an iPad + Apple Pencil.
            - There are cases where you want others to see what you have organized.
        - The fact that tools that support thinking are supposed to be used by one person may be a captive of the idea that thinking is something to be done by one person.
        - On the other hand, the "make it possible to edit together well" line requires a complete change of the server side to our own implementation, and I'm not sure if I should do that.
    - The current prototype was made while learning React and TypeScript, so the code is dirty, but I wonder if I should rebuild it.

Let's demo the title slide.

Information density issues, hard to understand, so I'll start by talking about the benefits of digitization.
- I'll go ahead and mention the hassle of "digital to paper" because it could be countered by talking about OCR from paper to digital.
- Everything needs to be done digitally.

Assumed Questions
- Automatic placement with machine learning and physics
    - →I can do it, but I don't think it will end well.
    - If it's not auto-placement but presentation of related stickies, it's possible.
    - Placement is a human intellectual product and should not be overridden by mechanical output.

Digital whiteboards
- Miro
    - Show them how to use it the way it's supposed to be used and tell them it's not good at all.

Assumed zone with more than 100 sticky notes.
- For example, if you have about 20 sheets, you can do it with sticky notes on the whiteboard or with Miro, but if you have more sheets, it becomes harder to do it.
- Even if you use your smartphone to do work on your PC.
- Human potential is limited.

---
I was going to release it yesterday to help other creators, or to eliminate the anxiety of being the first to release it, but Mattermost failure has taken up all my time.
memo
- The title demo will ask "Digital Notebook? Digital whiteboard? → Let's do a "Thinking Support Tool" flow.
- Let's use the key phrase "think with your hands" somewhere.

I thought the deadline was 23:59 but it was 11:59!

I'm very late to the party, but what should I do?

Write down what's in your head.
Move sticky notes around to organize your thoughts.
Tools to Support Thinking

---
tag
what's inside your head
Write it down.
tag
Organize.
Move it.
thinking
thinking
support
notebook
whiteboard
digital
Tools to Support Thinking

inside the head
jumbled up
I want to organize.
Write it on a sticky note.
Move it.
Organize.
Commonly used methods

When you already have something digitally written.
Labor to write by hand on paper sticky notes
occupy space
I've gone to a lot of trouble to arrange them.
It will need to be put away.
On paper
search (e.g. for someone using a search engine)
reuse
difficult (e.g. customer, guest, child)
spicy

conversion to electronics
necessary

whiteboard
Physically in the same place.
Information sharing for multiple people
The problem with more remote work
Taken with a camera
Cannot share well.
Get your head out of the clouds.
Might not be directly connected.
For single use
Visible and accessible areas
Not very wide due to height limitations.
Sticky note on the desk
I used to use it myself.
Difficult to search and reuse
Labor to write by hand on paper sticky notes
occupy space
It will need to be put away.
compression
Bundling" allows for "compression."
Spatial arrangements are destroyed.
Regroup's "Fold"
Restored to its original form
outline editor
Bullet points to organize ideas.
The tree can be folded.
Low degree of freedom of placement
Less information can be displayed on one screen.
Miro
Online Shared Whiteboard Service
Sticky note functionality has also been added.
I don't specialize in organizing information.
character limit
Only halfway through is imported.
Organize information in a limited area
Opening gaps and
Shadows and
Low density of information
Failure to adjust font size
Font smaller than necessary
Multi-line text
Paste does not import with sticky
Become a text box
Paste into a spreadsheet and copy and paste again
good point
touchpad
Two-finger swipe to move parallel
Pinch to zoom in and out
Regroup
assumption
More than 100 sticky notes
Limited screen space
Organize.

- [[Regroup, a tool to support thinking by writing and moving the contents of your mind to organize your thoughts Presentation materials]]
The presentation materials are ready for now, but my wife is taking a nap, so I'll take pictures later.

- [[Thinking Support Tool Regroup]]
done

---
This page is auto-translated from [/nishio/ブースト会議をドッグフーディングする](https://scrapbox.io/nishio/ブースト会議をドッグフーディングする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.