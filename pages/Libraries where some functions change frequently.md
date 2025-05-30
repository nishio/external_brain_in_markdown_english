---
title: "Libraries where some functions change frequently"
---

- There is a script A that runs on the command line and is operated interactively by the user.
- A function B is called from within A
    - Specifically, the creation of feature vectors
    - This is a trial-and-error process where the user of Script A rewrites it in a grueling way.
- The whole can be imported and used as a module
    - The purpose of script A is to make this module learn, and rewriting function B is also to improve it as a module
    - The phase of using Script A and the phase of using it interactively on the command line can overlap.
In this situation, I thought, "I'll rewrite the "B" part so hard that I might as well put it in a separate file," but what should be in the form of importing what?

Proposal 0: Separate cli.py for command line execution and user.py for user tinkering
- User executes cli.py
- User edits user.py
- import user from cli
- If the CLI is dead enough, users do not need to read the contents, nor do they need to have it for each project, so it is a good idea to centralize it.
- But until they wither, it's better to have them all in one place than to carelessly spread them out.

When you run a file in a package as a script, you cannot do a relative import from that file to any other file in the package, because the file does not think it is in the package.
:

```
.
└── foo
    ├── A.py
    ├── B.py
    ├── __init__.py
```

In this situation, if `import B` is written in A.py, `$ python A.py` is OK, but `python -c "import foo.A"` will not find B. Conversely, if it says `import .B`, `$ python A.py` is NG.

In the end, I decided to put the executable script outside the module
:

```
.
├── LICENSE
├── README.md
├── cli.py
├── ppoi
│   ├── main.py
│   ├── negative.txt
│   ├── neutral.txt
│   ├── positive.txt
│   ├── unknown.txt
│   └── user.py
└── samples
    └── unknown.txt
```




Proposal 1: Register function B from the user's favorite script user.py, and then call the CLI function to use it.
user.py

```
import ppoi

@ppoi.add_feature
def B(x):
	return 1

if __name__ == "__main__":
	ppoi.main()
```

In this case, this user.py needs to be executed even if it is imported and used as a module, so the API as a module (even if it is not used in this script) needs to be done `from ppoi import to_bool, to_prob` or something.

In this case, ppoi does not have to be in the project

Proposal 2: Call a function with a definite name in `ppoi user.py`. ppoi imports user.py and accesses the function with the specific name.

---
This page is auto-translated from [/nishio/一部の関数が頻繁に変更されるライブラリ](https://scrapbox.io/nishio/一部の関数が頻繁に変更されるライブラリ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.