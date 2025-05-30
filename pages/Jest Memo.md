---
title: "Jest Memo"
---

- [[Jest Memo Day1]]
- [[Jest Memo Day2]]
- [[Jest Memo Day3]]

2021-02-22
    - [[Test asynchronous React state updates]]
    - [[Replace useState]]
    - [[Export Promise created with useEffect]]
- Finally a decent test of "when there is a previous dialogue ID, there is a menu, when there is not, there is not".

- How do I test the code "when the server is sleeping, wait a second and try again"?
    - I see, so instead of using setTimeout raw, you wrap it in a Promise and make a "Promise to be resolved after 1 second".
        - [[Wrap setTimeout with Promise]]

- I'm trying to test the Regroup one, and the problem is that there's a lot of drag.

2021-02-25
- I'm wondering how to test for drags, etc. on Regroup in Jest...
    - I want to record events and use them for testing, but the problem is that if I record all the mousemove events, the amount of events is too large.
        - That kind of event should be recorded only immediately before, and only when the space key is pressed, the previous event is added to the event record.
    - This will allow "Surrounding with the long rope tool" to be expressed with fewer events.
        - The problem is that "pressed the space key" can be done on a PC, but it's hard to do on an iPad...
        - Do you want to thin it out by hours? Then can you have it recorded by stopping for a moment when you type?
        - [[Sentry with MouseMove thinned out]]
- I got the value of the coordinates, but I'm fireEventing in the test and nothing is happening, it's hard to track where you're getting a grip...
    - As for testing needs, I don't need to test the "event arrives when mousedown on canvas" because it has been tested enough, but I want to test the part after the event arrives.
    - It sounds tough, but I managed it.
        - Use an object that looks like a ToolEvent, IGNORE the type error, say it's a ToolEvent, and pass it on.
        - Emulate drag and automate "lassoing nothing".
            - This was a pile of bugs: "it dies when the mouse is down", "you can select it, but lines appear in weird places", and "dragging an enclosed area dies because there's nothing to move".
        - I've reproduced it in a test, and when there was nothing in the enclosed area, I reverted to the mode before it was enclosed, and even if the same bug occurs, the test should tell me next time.
- I want to refactor it because it feels like I was forced to test it and forced to fix it.
    - I really wanted to refactor first, but I knew that if I refactored the buggy stuff without writing any tests, it would break a lot, so I held off.
    - It's not a good design to have the lasso or balloon menu disappear directly in the collision detection between the lasso and the selected object.

2021-02-26
- I checked the screen size before writing the sticky drag test and found that it was 600 x 300, and every time I resized it, it doubled in size, a mysterious phenomenon...
    - Simply doing nothing and causing a resize event doubles the canvas size.
    - One pixel and one unit on the canvas may be off by a factor of 2 or something.
    - For now, it seems that the actual position of a sticky when it is added is determined regardless of its size, so let's separate it as a separate story and move on.
- I'm reminded of the Legacy Code Improvement Guide.
    - 'To refactor safely you need to test, but to test you need to refactor.' LOL.
        - [[The Legacy Code Dilemma]]
- I was able to test the balloon menu by clicking on the sticky, so I thought it was surprisingly easy, but when I tested the drag, the test runner stopped exiting, why...
    - Maybe an infinite loop when Jest strings some kind of object for screen display.
    - It's not supposed to be a circular reference...
- I was able to test it to the point where a sticky is selected by lasso selection.
    - I was able to eliminate the unpleasant situation of manipulating the menu UI from within the collision detection code, after covering it with tests, happily ever after!
- Coverage is about 39%.
- 46% by adding the tests for selecting multiple items and grouping them together and moving them together.
    - Well, let's add to it, piece by piece.
- When I test with jest's normal test runner, I'm so worried about asynchrony, but when I use electron, I write without worrying about it, and it works fine.
    - However, testing takes time.
- Hmmm, I clicked on the pen button but it didn't switch to the pen, inexplicable...
    - You're saying that the pen implementation is grabbing events before where the mouse events are currently being poured, so switching to the pen can't be automated.
    - I was able to test the pen drawing, but after drawing with the pen, both the path and the group that encompasses the path appear in the display order... this must be a bug that is drawing twice...
- Coverage is now 51%.
    - Let's do it next week for the issue that may be double drawing.

2021-03-01
- The double drawing was a simple bug that I fixed.
    - If this unexpected inconsistency is left unchecked, another problem is likely to occur
    - Selecting and ungrouping paths is going to develop into an even stranger situation.
- Paper.js project was created in a test case and accumulated because it was not deleted.
    - I removed them all in the afterteach that runs after each test case.
- I've been looking at the coverage from the smallest percentage of coverage, but I wonder if it's possible to order the number of uncovered statements - that would mean the coverage would increase efficiently if you tested it!
    - There were none, so I'll look at them in order of number of rows, or I'll do the red one with the most rows.
    - ![image](https://gyazo.com/b795c664b893480f62eb605cabcdaf41/thumb/1000)

2021-03-02
    - [[Test asynchronous processing in third-party libraries]]
    - I wanted to test drawing two passes to investigate the [[first pass jumps bug]], but the canvas redraw in Paper.js was asynchronous.

2021-03-03
    - [[Sentry with MouseMove thinned out]]
    - [[console.log in Safari on iPad]]
- `60.32% Statements 1444/2394 41.48% Branches 358/863 59.55% Functions 240/403 60.93% Lines 1421/2332`

2021-03-04
- Testing multi-touch operation with touch events
- I haven't been able to reproduce the problem of the two-finger tap becoming a click when released without moving, due to the same "ToolEvent not reaching for some reason" as before, but I found another bug when I was chasing down the cause of the mysterious error.
    - Zoom to zero if two-finger tap is released without moving
    - Maybe this is what caused the rare blank slate problem.
- Unexplained Phenomena
    - Throwing a mouse event on the canvas is not responsive.
    - I threw a touch event and he responded.
    - I wrote a test case thinking that touch would respond, but it doesn't.
    - Depending on the order in which the test cases were executed, "touchmove only reacts without touchstart reacting" occurred.

2021-03-05
- I notice that there is a warning on elecron side to the effect that "React status updates are not wrapped in act" (not relayed to jest side).
- Elecron does not show where there are unwrapped status updates.
- Narrow down the range by putting console.log
- I know where it is, but when you replaced the state update with the mock, shouldn't that have been replaced as well? That's what it looks like.
- The code to replace useState with mock is working.
- Then actually that replaced useState is called
- But it wasn't called at the time of the useState in question.
    - [[It wasn't replaced by just.spyOn.]]
- [Discussion on Facebook at](https://www.facebook.com/1129148772/posts/10224268346672864/?d=n)
    - UseState, maybe replace it with jest.mock.
        - Create a mock module that imports React, rewrites it, and re-exports it.
    - Instead of calling setState directly, try calling it in fireEvent with onClick that calls it, and if the interpretation is correct, there should be no warning that there is no act
    - Try to apply the component separation technique to solve the asynchronous problem by testing separately before and after Promise is used.
    - Container/Presentation separation
        - Designing it that way makes it easier to test.
        - On the other hand, when "adding tests to something that doesn't yet have test code," we want to cover it with tests and then refactor it, rather than refactor it and then test it.

- I wrapped it honestly because I was warned to "wrap it in ACT" in the first place, but you don't understand what is done when you wrap it...
    - react-dom/test-utils
        - [https://github.com/facebook/react/blob/master/packages/react-dom/src/test-utils/ReactTestUtilsPublicAct.js#L76](https://github.com/facebook/react/blob/master/packages/react-dom/src/test-utils/ReactTestUtilsPublicAct.js#L76)
    - react-testing-library
        - act
            - [https://github.com/testing-library/react-testing-library/blob/master/src/act-compat.js](https://github.com/testing-library/react-testing-library/blob/master/src/act-compat.js)
        - tests
            - [https://github.com/testing-library/react-testing-library/tree/master/src/__tests__](https://github.com/testing-library/react-testing-library/tree/master/src/__tests__)

2021-03-08
    - [[What does react-dom/test-utils act do?]]
- > useState, maybe we can replace it with jest.mock
    - `Do not import @jest/globals outside of the Jest test environment`
    - I'm not quite sure why I'm getting this error.
- [[requestAnimationFrame + jest-electron = unstable behavoir]]

2021-03-09~2021-03-12
- [[Can't perform a React state update on an unmounted component]]
---
This page is auto-translated from [/nishio/Jestメモ](https://scrapbox.io/nishio/Jestメモ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.