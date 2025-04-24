---
title: "Torch"
---

- Torch
    - [http://torch.ch/docs/getting-started.html](http://torch.ch/docs/getting-started.html)
    - I installed this, but I needed to put in PyTorch, not this.

- `$ pip3 install torch`
- > Successfully installed torch-0.4.1


:

```
x.index_fill_?
Docstring:
index_fill_(dim, index, val) -> Tensor

Fills the elements of the :attr:`self` tensor with value :attr:`val` by
selecting the indices in the order given in :attr:`index`.

Args:
    dim (int): dimension along which to index
    index (LongTensor): indices of :attr:`self` tensor to fill in
    val (float): the value to fill with

Example::
    >>> x = torch.tensor([[1, 2, 3], [4, 5, 6], [7, 8, 9]], dtype=torch.float)
    >>> index = torch.tensor([0, 2])
    >>> x.index_fill_(1, index, -1)
    tensor([[-1.,  2., -1.],
            [-1.,  5., -1.],
            [-1.,  8., -1.]])
Type:      builtin_function_or_method
```

Error if index is an empty Tensor

> Expected object of type torch.FloatTensor but found type torch.LongTensor


:

```
scatter_(dim, index, src) -> Tensor

Args:
    dim (int): the axis along which to index
    index (LongTensor): the indices of elements to scatter
    src (Tensor or float): the source element(s) to scatter
```



---
This page is auto-translated from [/nishio/Torch](https://scrapbox.io/nishio/Torch) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.