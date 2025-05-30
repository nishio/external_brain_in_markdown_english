---
title: "Receiving JSON in a messy way with FastAPI"
---

[[FastAPI]] accepts information from the path `"/items/{item_id}"`, query parameters `?q=foobar`, and JSON loaded in the request body as arguments to the handler.
This is sorted based on type hint information and is also used for automatic generation of API documentation.
This may have its merits, of course, but this time I was trying to create an outlet to receive webhooks from other services, so I thought, "I don't know the exact type of JSON sent in the request body, and it would be tedious to look it up and describe it accurately, so I'd like to receive it in a crude manner and observe what values are coming from it. I thought, "I don't know the exact type of JSON sent in the request body.

Conclusion.
python

```
from fastapi import Body
(…snip…)
@app.post("/")
async def root(body=Body(...)):
	print(body)
```


explanation

[doc](https://fastapi.tiangolo.com/tutorial/body/#request-body-path-query-parametershttps://fastapi.tiangolo.com/tutorial/body/#request-body-path-query-parameters)
> The function parameters will be recognized as follows:
>  If the parameter is also declared in the path, it will be used as a path parameter.
>  If the parameter is of a singular type (like int, float, str, bool, etc) it will be interpreted as a query parameter.
>  If the parameter is declared to be of the type of a Pydantic model, it will be interpreted as a request body.

So if you want to receive a value from the request body, it must be Pydantic
There are times when that is not a good idea, and the documentation explains it, for example, when integer values are coming in
> Without Pydantic
>  If you don't want to use Pydantic models, you can also use Body parameters. See the docs for [Body - Multiple Parameters: Singular values in body](https://fastapi.tiangolo.com/tutorial/body-multiple-params/#singular-values-in-body).

The sample in the document is explained in the case of multiple Pydantic arguments, so it does not directly match our purpose here.
Important specifications
- If there is a single Pydantic argument, the entire request body goes into that argument
- If there is more than one Pydantic in the argument, the value obtained from the request body by the key of the variable name goes into each argument.
In this case, there is only one Pydantic, so the whole thing goes into the argument body.

---
This page is auto-translated from [/nishio/FastAPIで雑にJSONを受け取る](https://scrapbox.io/nishio/FastAPIで雑にJSONを受け取る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.