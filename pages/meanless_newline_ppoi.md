---
title: "meanless_newline_ppoi"
---

work memo
- clone [ppoi
- Renamed to `meanless_newline_ppoi`.
- > Unjudged input must be placed in unknowns.txt before execution
    - Suddenly the staircase is a lot bigger.
    - This time, we have a situation that "When I convert PDF to text, it is divided into lines, and I want to merge them, but there are some that should be merged and some that should not".
    - I want to "remove what looks like meaningless line breaks."
lines

```
['Part I. u3000 Introduction', '', 'Originally there was not a single word filosofiva [philosophia] even in Greece, but the word filosofoV = Weisheitsfreund appeared in Herakleitos [Herakleitos, ca. 540-ca. 480B.C.].  ', 'The word filosofoV = Weisheitsfreund first appeared in Herakleitos, ca. 540-ca. 480B.C.', 'It is said to have come from Pythagoras, but that is a mistake. By the way, the word that forms the source of today's Philosophie comes from Herodotus (484-ca. 425B.C.), the father of history, who used the word filosofei:n,'' which, as mentioned above, is a form of the verb "to seek wisdom," and is also used by the philosophers of today, ', '', '', '6', '', 'Then it was transformed into the noun form filosofiva 〈愛知〉. The word "philosophia" was first used in the broad sense of "love of wisdom" or "pursuit of intellectual education," but through the Sophists and Socrates (Sokrates, 470/69-399B.C.) it gradually became limited to "study,''' '', "to study,''' and "to study. to study', '','' through the Sophists and Socrates [Sokrates, 470/69-399B.C.]. In the Sophists and Socrates, however, the word sophie', '', 'a' still included the ancient meaning of technical intelligence. It is not until Plato that it becomes wisdom in a purely spiritual sense. , '', 'Plato distinguished two kinds of knowledge. One is ejpisthvmh = Erkenntnis, knowledge, and the other is dovxa = Meinung, opinion. The former, or episteme, is true knowledge, true', 'knowledge of the real, Plato's so-called Idea. Idea is the eternal, immutable, true existence.', '', '']
```

py

```
import json
data = open("Introduction to Philosophy.txt").read()
data = data.split("\x0c")
# print(len(data))
unknowns = []
for page in data:
    lines = ["SOP"] + page.split("\n") + ["EOP"]
    for i in range(len(lines) - 3):
        unknowns.append(json.dumps({
            "i": i,
            "neg_i": len(lines) - i - 4,
            "lines": lines[i:i+4],
        }, ensure_ascii=False))

with open("unknowns.txt", "w") as f:
    f.write("\n".join(unknowns))
```

- `%run meanless_newline_ppoi/cli.py`
    - `ImportError: cannot import name 'clock' from 'time' (unknown location)`
- `%run meanless_newline_ppoi/cli.py --initialize`
    - `Enter at least one positive examples (empty to exit)`
    - `{"i": 10, "neg_i": 15, "lines": ["", "What is philosophy? It is difficult to give a simple answer to this question. Philosophy has been around for a long time and predates the individual "," "special sciences. Philosophy has undergone many changes throughout history and will continue to develop in the future."]}`
- I'm having them enter it in text format, which is hard to do.
    - Didn't we fix this...
- `FileNotFoundError: [Errno 2] No such file or directory: '/Users/nishio/scaffold_network/kitaro/meanless_newline_ppoi/ppoi/unknown.txt'`
    - You should check this first and warn them.
    - Placement, with or without UNKNOWNS s
:

```
%run meanless_newline_ppoi/cli.py --interactive
{"i": 0, "neg_i": 28, "lines": ["SOP", "One feels less pleasure when it becomes a habit, etc. Marshall's ("Pain," "Pleasure and Aesthetics," 1894 [Pain, Pleasure, and Aesthetics]) and other works are probably from this standpoint. From a psychological point of view, there is no other way to explain it. But the pleasure given by beauty and goodness is not merely a physical pleasure and a single "]}: 0.5001
negative(z), neutral(x), positive(c), quit(q)>
```

- It's working.
    - Improved display
    - Hey, I think I made it so that the user can customize how it is displayed...
    - [[ppoi improvement plan]]
        - [[ppoi improvement 2021-02-05]]
    - > "Where's the latest code?" so I pushed the current code anyway.
    - Where.
    - The last update before the repository we're looking at now is 2018.
    - Uh, it's in the keichobot repository.
    - [[Motion Extraction Work Memo #6018e017aff09e0000f60b4e]]
        - > Let's edit it rather than use it as it is.
        - Oh, I see what you mean.

liquidation
- Active learning is convenient for cases in which a human being cannot clearly verbalize the conditional expression of an if statement at this time, but can determine true or false by looking at the case study.
- I wrote the code for active learning two or three times from scratch, and then I thought, "It's inefficient to make it from scratch every time, so I want to put it all together," so I created ppoi.
    - But as a tool structure, the current ppoi is not appropriate.
    - So when using it in keichobot, it was not flexible enough to "copy and rewrite", and it was not reflected in the main repository.

2022-04-05

Not sure what the correct structure is, so copy and rewrite again this time
Interactive learning has come around.
- Downsampling changed from 5 seconds to 1 second.
`$ python3 -m ppoi.main --cross-val  `
Accuracy: 0.80 (+/- 0.18)

2022-04-06

In this case, we need the whole page, not each line, to create the features
- These things change from case to case, which is why it's so difficult to design in general...

---
This page is auto-translated from [/nishio/meanless_newline_ppoi](https://scrapbox.io/nishio/meanless_newline_ppoi) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.