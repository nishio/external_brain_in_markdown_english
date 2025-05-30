---
title: "AI generated image inventory 2022-10-02"
---

from  [[Diary 2022-10-02]]
AI generated image inventory 2022-10-02
Inventory.
![image](https://gyazo.com/454002ce651f79d6443307ca736cbeea/thumb/1000)

from  [[Diary 2022-10-01]]
- Input to Thompson sampling is buggy.
    - An "image that has not yet been reviewed" is treated as "an image that has been reviewed and judged to be bad".
    - Therefore, we're generating more and more keywords that look good, and more and more are considered "bad" and are lost.
from  [[Diary 2022-09-27]]
- About inpaint
    - > It is easier to programmatically create the mask image itself by looking at the differences.
        - > Prepare the original image and the image painted with a semi-transparent marker, and mask the areas where there are differences.
    - This didn't work.
        - I sent the PNG to my iPad, added it back, and it became a JPEG😅.
        - Should I open and edit with a decent drawing tool instead of the standard addendum tool?
        - But if that's the case, why not just use layers in the first place?
from  [[Diary 2022-09-26]]
- Problem with SSH connection to WSL
- Instructions for inpaint and img2img [[Diary 2022-09-21#632b0b13aff09e0000a6378b]].
    - In this regard, img2img's multiple-image generation can be specified with a command line argument, so it might be a good idea to use that.
    - Inconveniences include
        - ID and placement is different from the normal generation process.
            - I'd like to at least have a common ID.
        - Normal generation process is paused before generation, want to resume after generation
            - Is SIGCONT correct?
    - About inpaint
        - I want to be able to experiment at hand.
        - Experimental: The mask should be a gradient in the first place.
        - It is easier to create the mask image itself by looking at the differences in the program.
            - Prepare the original image and the image painted with a semi-transparent marker, and mask the areas where differences exist.
        - Can't I just make the outside of the mask of what came out after ✅ generation original? Do the borders stand out?
            - [[mask again after inpaint]]
- NFT
    - NFT was interesting to me because it was unknown to me and I was tinkering around with it, but once again, when I think about how to get AI to earn its own maintenance, it needs to be something stable like fan club dues, not something uncertain like NFT....
        - Image of [[Patreon]] or something like that.
from  [[Diary 2022-09-25]]
- I was thinking that I could put the original img2img images in Dropbox, but that's no good because the new arrival file will be a placeholder with no content and the PIL will fail to load.
from  [[Diary 2022-09-22]]
- It's interesting to see the rankings, so I'll see if I can create a script to output the rankings with images over the weekend.
- It would be good to give a ranking every weekend or every other week.
- Ranking of Insta Likes with images, done [/c3cats/Instagram Likes Best 30 (~2022-09-22)](https://scrapbox.io/c3cats/Instagram Likes Best 30 (~2022-09-22)).
- I like how they're using data science to beat art to the punch (is that a good thing?) with "from 315 AI-drawn cat drawings, over 400 followers around the world (90% outside of Japan) rated this drawing with likes and it got 55 likes."
- Ignoring arguments such as whether it is good art or not, or whether AI works can be art or not, we accumulate data without hesitation and talk about it with data.
from  [[Diary 2022-09-21]]
- Take an image as a parameter
- inpaint would also take the mask off.
- take a prompt
- Change the seed and run it.
- There are so many parameters that trying to specify them on a single line in a text file is nonsensical.
- txt2img separates output folders at the prompt, which is inappropriate
- Create folders with start times, etc., and write detailed settings inside.

![image](https://gyazo.com/a0fc311e149a3551e4b925503b8da4ec/thumb/1000)

![image](https://gyazo.com/af4dd5c1e05ba13761239be12668393b/thumb/1000)

I have two pieces I want to make.
- One needs heavy use of img2img

The insta post buffer is empty and needs to be added.
- A decision needs to be made regarding this, "whether or not to re-submit a re-post of something that has already been submitted with a lot of reactions".
    - You can post new images nonchalantly without re-submitting them.
    - Maybe we can wait until much later to re-post it.
    - The problem is that I forgot what exactly I was supposed to do with the buffer piling process.

The issue of Thompson sampling being crazy isn't actually urgent.
- Just stop.
- There are many pre-created image buffers.
- I've been busy and it's accumulated unreviewed.
    - The problem is that there is no distinction between this unreviewed and the ones that have been reviewed and turned into "Not Good".
    - The root of the problem lies in the fact that the state is represented by a folder.
    - Fixing it, on the other hand, is a big job.

The problem with the installer
- I expressed whether it has been submitted or not by moving the contents of the GOOD folder to PUBLISHED, but I think it's subtle.
- What happens if a new review process adds images to the GOOD folder while this program is running?
    - I'm reading and running the image and Prompt mapping file, so I'm good to go.
    - Problem of not knowing how many buffers are left
    - It's a hassle to add things along the way.
        - I need to merge the files.

You didn't even add the newly reviewed one to Scrapbox.
- And there's no mention of the Okoso series or any of the other interesting ones.

---

Let's not post the same image over and over again on Instagram.
- Even if you repost the one with the most likes, you should post it with the addition of "Best m with n likes" instead of posting it with the same wording.
- I'll write that code eventually.

Proposed new review system
- Now it's made in a size to be projected on a TV for two people to watch at the same time and have a good time.
- But that would require both of us to have free time together.
    - Tasks are heavy
- Compatibility with Thompson sampling
    - You have to promptly review to select GOOD from "unreviewed" and consider the rest NOT GOOD.
- In fact, I'm the one who checks in between experiments.
    - Hopefully we can use the information we have determined at this stage.
    - If you decide that a pair is not worth reviewing, you can immediately give them a not-good decision.
    - What I chose GOOD is, "I think this is good, what do you think?" I hope I can show it to you right away.
    - If you choose GOOD now, that will be left out of the pair review.
- If it's supposed to be viewed by one person, it should be designed for an iPhone screen size.
    - Can be reviewed while bathing.

- I like the idea of being able to access it from outside the local network.
    - Can be reviewed while walking.
    - Can be shown to test users

There was a proposal to turn the TV screen into a web app with automatic updates.

----
✅Insta posting resumes
✅Fixed Thompson sampling problem
- It would require a spectacular modification to stop expressing the status in the file system, so the operational rule "move reviewed items from new to not_good" is used to avoid this.
    - The ones in the NEW were considered unreviewed and removed from the tally.
    - Well, "already reviewed and in the new" doesn't match the naming of the new, either.

I'll have to merge the img2prompt results instead of replacing them.
- I'm using it as a candidate for Thompson sampling.
- Should we rather merge at the point of output?

Scrapbox needs to be merged as well.
- At first I used the ID as the page name with @ at the beginning, but OpenSea wouldn't accept it, so I decided to remove it.


---
This page is auto-translated from [/nishio/AI生成画像棚卸し2022-10-02](https://scrapbox.io/nishio/AI生成画像棚卸し2022-10-02) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.