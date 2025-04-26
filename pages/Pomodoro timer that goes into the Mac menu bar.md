---
title: "Pomodoro timer that goes into the Mac menu bar"
---

Enter the Mac menu bar [[Pomodoro Timer]].
<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
Tips for choosing
- If you want detailed statistics and application blocks → Flow has the most functions, and if you buy Pro, you can also export history in CSV.
- Super lightweight, want to start immediately → Horo can be used as if typing ⌘+Space → horo 25m.
- Want to manage tasks together → Be Focused (stand-alone completion) or PomoDoneApp (integration with other tools).
- Try it quickly without additional charge → If you create "Start Timer" and "Start Break" with macOS Shortcuts and make them resident in the menubar, you can operate Pomodoro for free.
All are confirmed to be compatible with Apple Silicon (M1/M2/M3).

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'm curious how you do it with [[macOS Shortcuts]].

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
## macOS shortcut to create a "Free Pomodoro" 
.
(Confirmed from Sonoma onward; almost the same in Ventura)
## 1. Create a "Start Concentration" shortcut
.
1. click ### shortcut.app → +
 and name it
- `Pomodoro 25` (example)
2. top right `i` button → ### "pin to menu bar"
 on
Add the following actions in order
- 1.Start timer.
        - `25` min
2. (optional) set the concentration mode → set "Good night mode" to 30 min.
    3. Show Notification → [[25 Minute Intensive Start]].
- 4.standby → `1500` seconds (=25 minutes)
    5. Show Notification → "Good job!"
6. play sound → "Glass" etc.

This single device completes the process from "Concentration→Notification→To Rest".
(There was also an explanation of running a break timer in a chain of events, but I omitted it.)

## 3. Small tricks to make it even more comfortable
.

- ⌘⌥P etc. to start instantly.
    - `i` button → set keyboard shortcut
- Play music when done
    - Added "Play in Music" action
- Auto-logging.
    - Get Current Date" -> "Append to CSV" -> `~/Documents/pomo.csv` Save
- Automatically start the first one every morning.
- | "Automation" -> "Time" -> 9:00 -> Execute the shortcut just described.

## 4. Execution Method
.
- New icon 🟠 appears in the menu bar → click to run
- You can also type `Pomodoro` in Spotlight and Enter.
- To avoid multiple simultaneous executions, insert the action "Exit if running" at the top.

This completes the ### completely free, menubar-resident Pomodoro environment
 without the need for a dedicated application.
Please let us know if there are any areas that you would like to customize in more detail (e.g., changing the log storage location, notification text, etc.)!

---
It's good business for the makers of the Pomodoro timer.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

---
This page is auto-translated from [/nishio/Macのメニューバーに入るポモドーロタイマー](https://scrapbox.io/nishio/Macのメニューバーに入るポモドーロタイマー) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.