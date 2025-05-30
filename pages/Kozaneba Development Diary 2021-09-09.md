---
title: "Kozaneba Development Diary 2021-09-09"
---

prev  [[Kozaneba Development Diary 2021-09-08]]
![image](https://gyazo.com/cef794096b06743c1bbd9b9c4b40f0c4/thumb/1000)

---
Yesterday I was able to read JSON and visualize the source code.
- I should make sure it is in the correct format when importing because if a user tries the same thing and puts in incorrectly formatted JSON and gets an error, Sentry will see it and I will be confused.
- When it is not correct, I should give feedback to the user instead of sending the error to me.

Arrow function
- There is no means of attaching it via GUI.
- Do you want the arrows you put in the GUI to be clickable?
    - The current one is too thin for that.
    - But I liked the thin one for source code visualization.
    - Need to be able to switch in Ba units.

physical operation
- You can turn it on and off by hitting the API from the console.
- Attach buttons with user scripts

I want a user script edit screen.
- Even when this is done and an error occurs, it should be fed back to the user instead of sending it to Sentry.

---
Error feedback on import, done.

You didn't write the release notes yesterday.
- `Annotation Layer` added.
    - Currently only the arrows are implemented.
    - GUI has not been created yet, can only be created by importing JSON
- Physics-based auto-shaping functionality has been added.


Next to Edit User Script screen
- done
- Adding physics buttons with user scripts

![image](https://gyazo.com/d493d53577b82f002ebac352258d2925/thumb/1000)

![image](https://gyazo.com/679775b480aa540d3a095a97287a9792/thumb/1000)
![image](https://gyazo.com/8f571f642b87f4a20ae59fa5f7f0207a/thumb/1000)
![image](https://gyazo.com/6f34662f37f13b9ade7b6fd8b1d0ed51/thumb/1000)

>  Do you want the arrows you put in the GUI to be clickable?
>  The current one is too thin for that.
>  But I liked the thin one for source code visualization.
>  Need to be able to switch in Ba units.
This is an error.
- Arrows that are programmed to generate 700 arrows are not the same as arrows that are attached by hand by humans.
- Arrows to be generated should be lighter weight data
- Just put a custom style on the one the user makes.

![image](https://gyazo.com/8c1ce3bb6927e704966910f4aaa240b0/thumb/1000)

release notes
- Added UserScript dialog to review, rewrite, execute, and save current code
    - Until now, the only way for UserScript was to rewrite localStorage directly.
- Arrows can now be added from the selection menu.
    - ![image](https://gyazo.com/cef794096b06743c1bbd9b9c4b40f0c4/thumb/1000)

No deletions yet, but we'll operate it for a while to see if it's necessary.
I was going to click on the arrow when I wanted to change the arrow style after the fact, but now I'm wondering if it's quite easy to use, since I have to click on the "unheaded" side of the arrow when I want to put the head on the unheaded side of the arrow.

I was thinking of adding help to Kozaneba besides the tutorial, but I'm starting to feel like I should just write it in the forum and show the link.
- For example, if I add Scrapbox format and Markdown format loading to the Add Kozane dialog in addition to the current "1 line 1 kozane", and if I put a help icon there, when I open this in the help dialog in the app, the original dialog will be closed.
- The tutorials had the advantage of being integral to the program since they do rather a lot of things like "detect the screen size and warn if it's too small" or "provide presets to try out operations", but I don't think so for the additional content...

Tomorrow we will improve Keicho and Keicho will also move to project management in Kozaneba

Copy as Text from Kozaneba does not try to keep groups indented or anything, and I am thinking of adding Copy as Scrapbox and Copy as Markdown separately...
Well, I'll do the Keicho one tomorrow, so I'll just work on ideas, and if I do it, it will be next week. Some people say that we are adding too many features, so we might make a week where we don't add any features.
---
This page is auto-translated from [/nishio/Kozaneba開発日記2021-09-09](https://scrapbox.io/nishio/Kozaneba開発日記2021-09-09) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.