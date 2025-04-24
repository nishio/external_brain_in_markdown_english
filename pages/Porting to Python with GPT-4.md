---
title: "Porting to Python with GPT-4"
---

Trying to see how realistic it is to transplant at GPT-4.
- Related [["I had GPT-4 write it"]][/villagepump/Twitter to Scrapbox GPT](https://scrapbox.io/villagepump/Twitter to Scrapbox GPT).
- result
    - I got the ported code in one shot.
    - It contained both easy-to-understand and hard-to-understand bugs.
    - Bugs that were difficult to understand were misplaced when GPT was shown the error messages, so it was necessary to observe and understand what was going on.
    - Once the cause was identified, GPT4 immediately responded with a fix.
    - I ordered a refactoring, and it refactored properly, but I got a bug that was hard to understand.
    - Which is faster than porting it yourself is going to depend on your ability to debug the code written by GPT4.
    - In this case, TypeScript can read itself, but I had zero to read and check. Is it an advantage to be able to port from a language you can't read?

Python the following TypeScript code
[https://github.com/meganii/sandbox-github-actions-scheduler/blob/main/index.ts](https://github.com/meganii/sandbox-github-actions-scheduler/blob/main/index.ts)

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Convert following TypeScript to Python: ...


-----
<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>Here's the TypeScript code converted to Python:
[https://github.com/nishio/gpt4_translation_example/commit/ff49c64881de59214536fdb5a6588454864b6b10](https://github.com/nishio/gpt4_translation_example/commit/ff49c64881de59214536fdb5a6588454864b6b10)

This Python script uses asyncio and aiohttp for handling asynchronous tasks and HTTP requests, respectively. You might need to install the aiohttp library using the following command:

`$ pip install aiohttp`

---
but well, I'll make a venv.
`$ python3 -mvenv venv`
`$ . venv/bin/activate`
`$ pip install aiohttp`

----
Execution.
:

```
  File "/Users/nishio/etude-github-actions/main.py", line 58
    print(f"[page {j}@scrapbox-external-backup] start fetching "/{project}/{titles[j].title}"")
          ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
SyntaxError: invalid syntax. Perhaps you forgot a comma?
```


fix1
[https://github.com/nishio/gpt4_translation_example/commit/6d89f04c19d27d89ab3fac410e6d7c654f616ab4](https://github.com/nishio/gpt4_translation_example/commit/6d89f04c19d27d89ab3fac410e6d7c654f616ab4)

-----
:

```
aiohttp.client_exceptions.ContentTypeError: 0, message='Attempt to decode JSON with unexpected mimetype
```

Oops, error.
Let's just put in the appropriate error message for now.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
:

```
File "/Users/nishio/etude-github-actions/main.py", line 87, in <module>
    asyncio.run(main())

aiohttp.client_exceptions.ContentTypeError: 0, message='Attempt to decode JSON with unexpected mimetype
```


<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>
The error you encountered is caused by the aiohttp library expecting the response content type to be application/json. However, the API response may have a different content type. To fix this issue, you can update the fetch function to ignore the content type when attempting to decode the JSON response.

Replace the existing fetch function with the following:

python

```
async def fetch(url):
    async with aiohttp.ClientSession() as session:
        async with session.get(url) as response:
            return await response.json(content_type=None)
```


This modification will allow the fetch function to decode the JSON response without considering the content type.

impressions
- It's not going to fix itself.
- ![image](https://gyazo.com/3dc6fe724108e0bfa1010465fc2910c5/thumb/1000)
- Hmmm, I doubt this fix is appropriate.

-----
Character code problem? (PS: False guess)
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
For `return await response.json()`, specify it is UTF-8
<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>
The response.json() method uses the charset specified in the HTTP response's Content-Type header to decode the response text. If the server sends a response with the correct Content-Type header that includes the charset, the response should be decoded correctly. However, if you want to ensure that the response is always decoded as UTF-8, you can modify the fetch function to read the response bytes and decode them using UTF-8 explicitly.

Replace the existing fetch function with the following:

:

```
async def fetch(url):
    async with aiohttp.ClientSession() as session:
        async with session.get(url) as response:
            response_bytes = await response.read()
            response_text = response_bytes.decode('utf-8')
            return json.loads(response_text)
```

This modification will explicitly decode the response using UTF-8 before parsing it as JSON.

impressions
- I couldn't solve it, but I printed response_bytes anyway and got b'The requested page was not found'.
- I made it skip if the result is this and it started going.
- Output problematic URLs to see when this happens
- → Page titles contain periods or slashes!

Okay, so it's like this: a porting error caused by the different default behavior between TypeScript and Python.
python

```
>>> from urllib.parse import quote
>>> quote("aaa.bbb/fff")
'aaa.bbb/fff'
```


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>How to quote period and slash in URI segment?
<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>
To percent-encode special characters like period (.) and slash (/) in a URI segment, you can use Python's urllib.parse.quote() function and provide a custom string of safe characters. By default, the quote() function considers period (.) and slash (/) as safe characters, so they won't be percent-encoded. To override this behavior, you can pass an empty string as the safe parameter:

python

```
from urllib.parse import quote

uri_segment = "example.com/path"
encoded_segment = quote(uri_segment, safe='')

print(encoded_segment)
```


Output:

:

```
example%2Ecom%2Fpath
```


In this example, both the period (.) and slash (/) are percent-encoded. You can customize the safe parameter to include any characters that you want to keep unencoded.

fix 2
[https://github.com/nishio/gpt4_translation_example/commit/993f07457a7ffd52b4dc10b7517a75cce05f5126](https://github.com/nishio/gpt4_translation_example/commit/993f07457a7ffd52b4dc10b7517a75cce05f5126)
Motion!
----
Refactoring
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Refactor following codes. Make long string templates constants. Use namedtuple for the data class.
<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>
I've refactored the code to use namedtuple for the data class and moved long string templates into constants:
...
I've replaced the TitlePage class with a namedtuple for better simplicity and performance. Additionally, the URL_TEMPLATE and LIMIT_PARAM constants have been introduced to improve code readability.
[https://github.com/nishio/gpt4_translation_example/commit/8f54713b4637ba39f896ef7981627aafed3f60b2](https://github.com/nishio/gpt4_translation_example/commit/8f54713b4637ba39f896ef7981627aafed3f60b2)

-----
The bug was planted in the refactoring w
[https://github.com/nishio/gpt4_translation_example/commit/53eeb191a428a47fb95e19a7b4cfb9b658caee90](https://github.com/nishio/gpt4_translation_example/commit/53eeb191a428a47fb95e19a7b4cfb9b658caee90)

---
This page is auto-translated from [/nishio/GPT-4でPythonに移植](https://scrapbox.io/nishio/GPT-4でPythonに移植) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.