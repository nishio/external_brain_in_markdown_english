---
title: "SpeedReader"
---

- [[speed reading]] Support software
Minimize the lag when turning pages in PDF

- Gamepad can be used.
    - Analog joystick to adjust page flip speed.
    - However, there are very few situations that require speed adjustment in such fine increments.
    - Connecting a gamepad is a hassle.
        - Maybe not if you're constantly connected to a permanent machine.
        - Useful to be able to lie in bed with the monitor overhead and use the gamepad to control it when reading a book in bed

- Pre-conversion of books
    - The main reason for the heavy backlog is the heavy "pre-conversion of books".
        - If I put a book on S3, should it be automatically converted?
    - It just wasn't that necessary.
        - Useful for checking multiple books here and there when writing.
        - I'm converting it all together with "I need this book and this book in this chapter."
    - The problem is that there was no language that told us what to do when we wanted to convert.
    - Now put them in idea-generation/make_movie/input and convert them automatically.
        - Using pdfs_to_pngs.py
        - I really want to improve the quality by incorporating the experiments in pdf2png.
        - If I can disregard the "conversion time", I'd like to be able to output PNGs and DirectX format at the same time.
        - Maybe we should make a separate file for PNGs for enlargement and a separate file for listing.

- Why not show shortcut keys?
    - Z and C to zoom in and out
        - forget
    - ESC should bring up the settings screen and the key configuration screen that is common in games.
        - It would be best to be able to do key configurations as well, but it's better just to be able to see them.
- Shortcut keys that I thought might be nice to add
    - Show full size at 1
    - Jump to a specific page?
    - Set page feed to N pages.
- I want to change the left/right exchange and the number of pages to be sent out at a time without rewriting the configuration file.
    - It does not have to be a shortcut key, just a configuration dialog.
- Open by drag-drop to an icon, not drag-drop to a window.

- How to put out a GUI
    - [https://github.com/Siv3D/Reference-JP/wiki/GUI](https://github.com/Siv3D/Reference-JP/wiki/GUI)
    - [http://qiita.com/Mitsugoro32/items/76d584b9fcdeb9be535d](http://qiita.com/Mitsugoro32/items/76d584b9fcdeb9be535d)
- Display 3 pages when 3 pages can be displayed
    - So, do you prefer to turn three pages or one page (read by gazing at the center of the page)?
    - Two-page display would be nice to have a two-page feed function
    - Only one page feed when zoomed out display is slow.
- I'm currently switching LTRs by rewriting the configuration file, but should be able to do it in the GUI.

- I'd like to relegate all key binding changes to the INI.
    - [https://github.com/Siv3D/Reference-JP/wiki/INI,CSV,JSON](https://github.com/Siv3D/Reference-JP/wiki/INI,CSV,JSON)

- If the current directory is a multiple string, files can be listed even if they are not all in one place.

- I want to put permalinks on specific pages of a book.
    - [[speedreader://bookname/pageid]] and so on.


2017-07-11
done
- I need a way to open it other than drag-drop.
    - List of book-like items in the specified folder
        - If there is a "cover.png" in the folder, display it.

- Should there be a key to go up to a higher level in FS?
    - If there is a folder within a folder, it would be useful to have the ability to dig down one level and check if there is a cover image and load it, maybe a list of books, etc.
→Jump to the "Book List Directory" with the X key.

- If it fits, why not put out three pages at a time?
    - →I decided to put everything out there as much as possible to display on the screen.


- LR Exchange
    - R key
- Disable automatic playback in book list mode
- Zoom out to some extent from the beginning in book list mode
    - Display during loading
- fix Seems to be an out of bounds error in book list mode.
- Bring up the progress bar vertically

2017-07-05
done
- Do not exit with ESC
    - [http://qiita.com/sin5ddd/items/71e6ea487b89b010c103](http://qiita.com/sin5ddd/items/71e6ea487b89b010c103)

---
This page is auto-translated from [/nishio/SpeedReader](https://scrapbox.io/nishio/SpeedReader) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.