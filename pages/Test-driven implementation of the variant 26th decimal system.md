---
title: "Test-driven implementation of the variant 26th decimal system"
---

1, 2, 3, ... , 26, 27, 28, ... for a, b, c, ..., z, aa, ab, ... , z, aa, ab, ... to a, b, c, ..., z, aa, ab, ...
[https://atcoder.jp/contests/abc171/tasks/abc171_c](https://atcoder.jp/contests/abc171/tasks/abc171_c)
- Since there is a space character other than a-z, of course it is not in 26th decimal, and since there is no space character in the middle of the number, it is not in 27th decimal, either.
- I developed it based on the "fact" of test cases and their success or failure, rather than based on a vague "interpretation" that "it must be 26 decimal digits".
- I think this test-driven story is rather interesting, so let's summarize it before I forget

complete form
python

```
def solve(N):
    q = N
    ret = ""
    while True:
        q, r = divmod(q - 1, 26)
        ret = ascii_lowercase[r] + ret
        if q == 0:
            print(ret)
            return
```

I didn't write this code from the beginning.

At first I thought, "This problem is easy to test, so let's make it test-driven," so I put up a snippet that calls [[doctest]].
python

```
from string import ascii_lowercase


def solve(N):
    """
    """


def main():
    N = int(input())
    solve(N)


def _test():
    import doctest
    doctest.testmod()


if __name__ == "__main__":
    import sys
    argv = sys.argv
    if len(sys.argv) == 1:
        # no option
        main()
    elif sys.argv[1] == "-t":
        _test()
    else:
        input = open(sys.argv[1]).buffer.readline
```


First, write a test case
python

```
def solve(N):
    """
    >>> solve(1)
    a
    """
```


Naturally, the test will fail.
python

```
$ python3 c2.py -t
**********************************************************************
File "c2.py", line 6, in __main__.solve
Failed example:
    solve(1)
Expected:
    a
Got nothing
**********************************************************************
1 items had failures:
   1 of   1 in __main__.solve
***Test Failed*** 1 failures.
```


Write code that passes tests
python

```
def solve(N):
    """
    >>> solve(1)
    a
    """
    print(ascii_lowercase[N - 1])
```


Run the test to confirm it is OK (doctest does not display anything when it is OK).

Add a test case
python

```
def solve(N):
    """
    >>> solve(1)
    a
    >>> solve(27)
    aa
    """
    print(ascii_lowercase[N - 1])
```


Naturally, the test will fail.
See what kind of failures you have.
I'm getting `IndexError: string index out of range` after reading the 27th of only 26 strings.
python

```
$ python3 c2.py -t
**********************************************************************
File "c2.py", line 8, in __main__.solve
Failed example:
    solve(27)
Exception raised:
    Traceback (most recent call last):
      File ".../doctest.py", line 1329, in __run
        compileflags, 1), test.globs)
      File "<doctest __main__.solve[1]>", line 1, in <module>
        solve(27)
      File "c2.py", line 11, in solve
        print(ascii_lowercase[N - 1])
    IndexError: string index out of range
**********************************************************************
1 items had failures:
   1 of   2 in __main__.solve
***Test Failed*** 1 failures.
```


Then let's just calculate the quotient divided by 26 and the remainder.
python

```
def solve(N):
    """
    >>> solve(1)
    a
    >>> solve(27)
    aa
    """
    q, r = divmod(N - 1, 26)
    print(ascii_lowercase[r])
```


The error message changed, and it was not a runtime error, but rather that the value output was wrong.
Let's fix this.
python

```
$ python3 c2.py -t
**********************************************************************
File "c2.py", line 8, in __main__.solve
Failed example:
    solve(27)
Expected:
    aa
Got:
    a
**********************************************************************
1 items had failures:
   1 of   2 in __main__.solve
***Test Failed*** 1 failures.
```


I haven't used the quotient I calculated earlier, so I'll use it anyway.
python

```
def solve(N):
    """
    >>> solve(1)
    a
    >>> solve(27)
    aa
    """
    q, r = divmod(N - 1, 26)
    ret = ascii_lowercase[r]
    if q == 0:
        print(ret)
    else:
        print(ascii_lowercase[q] + ret)
```


Failure that it should be aa but it is ba (foreshadowing 1)
python

```
$ python3 c2.py -t
**********************************************************************
File "c2.py", line 8, in __main__.solve
Failed example:
    solve(27)
Expected:
    aa
Got:
    ba
**********************************************************************
1 items had failures:
   1 of   2 in __main__.solve
***Test Failed*** 1 failures.
```


The number was reduced by 1 to make it more consistent.
python

```
def solve(N):
    """
    >>> solve(1)
    a
    >>> solve(27)
    aa
    """
    q, r = divmod(N - 1, 26)
    ret = ascii_lowercase[r]
    if q == 0:
        print(ret)
    else:
        print(ascii_lowercase[q - 1] + ret)

```


Test OK
Add a new test case.
python

```
def solve(N):
    """
    >>> solve(1)
    a
    >>> solve(27)
    aa
    >>> solve(703)
    aaa
    """
    q, r = divmod(N - 1, 26)
    ret = ascii_lowercase[r]
    if q == 0:
        print(ret)
    else:
        print(ascii_lowercase[q - 1] + ret)
```


Naturally, it will fail.
This error message `IndexError: string index out of range` is the one I saw earlier, let's fix it the same way.
python

```
$ python3 c2.py -t
**********************************************************************
File "c2.py", line 10, in __main__.solve
Failed example:
    solve(703)
Exception raised:
    Traceback (most recent call last):
      File ".../doctest.py", line 1329, in __run
        compileflags, 1), test.globs)
      File "<doctest __main__.solve[2]>", line 1, in <module>
        solve(703)
      File "c2.py", line 18, in solve
        print(ascii_lowercase[q - 1] + ret)
    IndexError: string index out of range
**********************************************************************
1 items had failures:
   1 of   3 in __main__.solve
***Test Failed*** 1 failures.
```


I copied and pasted the code I wrote earlier and modified it the same way.
python

```
def solve(N):
    """
    >>> solve(1)
    a
    >>> solve(27)
    aa
    >>> solve(703)
    aaa
    """
    q, r = divmod(N - 1, 26)
    ret = ascii_lowercase[r]
    if q == 0:
        print(ret)
    else:
        q, r = divmod(q - 1, 26)
        ret = ascii_lowercase[r] + ret
        if q == 0:
            print(ret)
        else:
            q, r = divmod(q - 1, 26)
            ret = ascii_lowercase[r] + ret
            print(ret)
```


Test OK
The same thing continues after the fourth digit, so let's rewrite it using a loop.
python

```
def solve(N):
    """
    >>> solve(1)
    a
    >>> solve(27)
    aa
    >>> solve(703)
    aaa
    """
    q = N
    while True:
        q, r = divmod(q - 1, 26)
        ret = ascii_lowercase[r]
        if q == 0:
            print(ret)
            break
```


Fail when rewritten and tested.
python

```
$ python3 c2.py -t
**********************************************************************
File "c2.py", line 8, in __main__.solve
Failed example:
    solve(27)
Expected:
    aa
Got:
    a
**********************************************************************
File "c2.py", line 10, in __main__.solve
Failed example:
    solve(703)
Expected:
    aaa
Got:
    a
**********************************************************************
1 items had failures:
   2 of   3 in __main__.solve
***Test Failed*** 2 failures.
```


Forgot to extend the string. Correction.
python

```
def solve(N):
    """
    >>> solve(1)
    a
    >>> solve(27)
    aa
    >>> solve(703)
    aaa
    """
    q = N
    ret = ""
    while True:
        q, r = divmod(q - 1, 26)
        ret = ascii_lowercase[r] + ret
        if q == 0:
            print(ret)
            break
```


Test OK
Now submitted.

digression
- I got ba in the middle (foreshadowing 1), but that was the correct 26th decimal.
    - Even in decimal notation, the first number to have two digits is 10, not 00.
    - This problem is different from the 26th decimal because it has to be aa, not ba.
    - I see people on Twitter trying to make an N-decimal library and lamenting that they couldn't implement the 26th decimal system correctly, but that's not what this problem is asking for in the first place.
    - Interpretation is skewed.
- If you do test-driven [[fact-based development]], it's hard to get distorted by interpretation.

---
This page is auto-translated from [/nishio/テストドリブンで変形26進法の実装](https://scrapbox.io/nishio/テストドリブンで変形26進法の実装) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.