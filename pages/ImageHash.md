---
title: "ImageHash"
---

[ImageHash · PyPI](https://pypi.org/project/ImageHash/)
[GitHub - jgraving/imagehash: A Python Perceptual Image Hashing Module](https://github.com/jgraving/imagehash)

Image Similarity Search
- The URL of the PNG digested locally with the md5 command matches the URL when it is uploaded to Gyazo
- But when I copy-paste an image into Scrapbox, the one automatically uploaded to Gyazo has a different URL
    - Is the content of the file different due to different server-side settings for converting to PNG, etc.?
    - I downloaded this image and looked at the md5 and it matched the URL.
- Hard to determine if the same image is in the original image, the image posted to Twitter and served by twimg, the image saved locally, or the image pasted into Scrapbox.
    - Doing an [[Image Similarity Search]] in Python
    - [[imgsim]] and ImageHash.
        - The former winds up using Torch to create a 768-dimensional feature vector.
        - Maybe a companion to [[clip-ViT-L-14]].
    - The latter feels like no machine learning.
        - The latter sounds like a good fit.
    - It was found that ImageHash can determine that images uploaded by pasting with different hash values are identical.

---
This page is auto-translated from [/nishio/ImageHash](https://scrapbox.io/nishio/ImageHash) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.