---
title: "Google Cloud Vision API"
---

<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
First, you must install the Google Cloud SDK, set up and certify your project.

- Install the Google Cloud SDK: [https://cloud.google.com/sdk/docs/install](https://cloud.google.com/sdk/docs/install)
- Set up a project with the gcloud init command: [https://cloud.google.com/sdk/gcloud/reference/init](https://cloud.google.com/sdk/gcloud/reference/init)
- Create service account key: [https://cloud.google.com/docs/authentication/getting-started](https://cloud.google.com/docs/authentication/getting-started)
    - > To grant access to a project, grant the service account the Project > Owner role.
    - >  To grant a role, find the Select Role list and choose Project > Owner.
        - Trap that is translated and not found in searches.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - ![image](https://gyazo.com/13aa452634eb1f91bad91b4e53896024/thumb/1000)

- Set the path to the environment variable GOOGLE_APPLICATION_CREDENTIALS:.


The following code can perform OCR using the Google Cloud Vision API.

python

```
import os
from google.cloud import vision
from PIL import Image

os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "/path/to/your/service-account-key.json"

def ocr_image(image_path):
    client = vision.ImageAnnotatorClient()

    with open(image_path, 'rb') as image_file:
        content = image_file.read()

    image = vision.Image(content=content)
    response = client.text_detection(image=image)
    texts = response.text_annotations

    if texts:
        return texts[0].description
    else:
        return ""

def ocr_readable_images(images_dir):
    ocr_texts = []
    for image_name in sorted(os.listdir(images_dir)):
        if image_name.startswith("readable_page"):
            image_path = os.path.join(images_dir, image_name)
            ocr_text = ocr_image(image_path)
            ocr_texts.append(ocr_text)
    return ocr_texts

if __name__ == '__main__':
    images_dir = 'output/images'
    ocr_texts = ocr_readable_images(images_dir)
    for i, text in enumerate(ocr_texts):
        print(f'Page {i+1}:\n{text}\n{"="*40}')
```



<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- `$ pip install google-cloud-vision`
- `PermissionDenied: 403 Cloud Vision API has not been used in project 573408197915 before or it is disabled. Enable it by visiting https://console.developers.google.com/apis/api/vision.googleapis.com/overview?project=... then retry.`
    - ![image](https://gyazo.com/b87af84021d2ca24093e39f187394017/thumb/1000)
- `PermissionDenied: 403 This API method requires billing to be enabled. Please enable billing on project`
- OK
    - input
        - ![image](https://gyazo.com/99abdce33c5963c4b4f9fbf061d31a2d/thumb/1000)
    - output
        - ![image](https://gyazo.com/dc950232861a0723e2c3ce96fba25ffc/thumb/1000)
- [price](https://cloud.google.com/vision/pricing)
    - ![image](https://gyazo.com/14463ed63ed3610cfbd680c0386e5b0b/thumb/1000)

- It usually takes a little over a second per request.
- Rate limit is 1800 per minute, so I could do about 30 parallels.



---
This page is auto-translated from [/nishio/Google Cloud Vision API](https://scrapbox.io/nishio/Google Cloud Vision API). If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.