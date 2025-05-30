---
title: "I want to merge JSON in Scrapbox."
---

When importing into Scrapbox, if you don't want to overwrite and lose content, you have to export first, merge locally, and then import

Survey on 2019-10-31
- export
    - POST to `https://scrapbox.io/api/page-data/export/PROJECT_NAME.json`.
        - request
            - It's loaded with connect.sid.
                - see  [[Tapping Scrapbox's private project API]]
                - Payload `{"metadata":false}`.
                    - If you make it true, it will be the one with the update date and time for each line.
            - The request header has X-CSRF-TOKEN, do we need to get and load this in some way?
            - Sounds like you need both.
            - `curl -X POST https://scrapbox.io/api/page-data/export/PROJECT_NAME.json -b connect.sid=SECRET_ID -H "X-CSRF-TOKEN: ..." -o export.json`
                - Now I could download it.
        - response
            - UI-wise, a "download" button is created and then clicked.
                - I thought the file was generated on the server side and it would be a link to the file.
                - But the response is returning JSON for the entire project.
            - The button is `<a href="blob:https://scrapbox.io/446e...." download="nishio.json" ... >Click to download... </a>`
            - I guess they make a blob and let you download it as a file.
                - `URL.createObjectURL(new Blob(...)) Like `...
                - [Blob - Web API | MDN](https://developer.mozilla.org/ja/docs/Web/API/Blob)

- merge
    - afterwards

- import
    - If page deletion occurs, the project must be deleted once
        - This is pending.
    - Displays how many pages will be imported when the file to be imported is specified.
        - I thought I was sending it to the server, but no request was sent.
        - You're checking with JS at the client.
    - `POST https://scrapbox.io/api/page-data/import/PROJECT_NAME.json`
    - This is also loaded with connect.sid and X-CSRF-TOKEN
    - It looks like you are just sending the json contents as Form Data.
        - name: undefined, but I guess this means it doesn't matter because it is not used even if it is not specified.
        - `-F "jsonfile=@path/to/jsonfile.json"` I wonder if I can do it with `-F "jsonfile=@path/to/jsonfile.json"`.

---
This page is auto-translated from [/nishio/ScrapboxのJSONをマージしたい](https://scrapbox.io/nishio/ScrapboxのJSONをマージしたい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.