---
title: "End Design Active Learning"
---

- [[End Design]]

Is this a good place to end up?" The line uses a binary classification with the environment as an argument to determine if it is appropriate to pose the question "Is this a good place to end up?

Duplicate the environment at each point in time from the log with deepcopy and use it as an argument.
python

```
def get_unknowns():
    IS_SINGLE = True
    if IS_SINGLE:
        TARGETS = [f"{CACHEDIR}/y3mJfH67rbHpvTp9yfY6.json"]
    else:
        TARGETS = glob.glob(f"{CACHEDIR}/*.json")

    for path in TARGETS:
        environment.init_for_web("test", is_local=True)
        testenv = load("test", local=True)
        data = open(path).read()
        replay_env = Env(name="replay", is_local=True).fromJSON(data)
        testenv.keyphrase_extraction_type = "replay"
        testenv.replay_env = replay_env

        for i, (user, text) in enumerate(replay_env.log):
            if user == 1:
                r = keicho.connect_web("", "test", text, testenv)
                r = json.loads(r)["text"]
                yield deepcopy(testenv)
```


Active learning questions are now being asked.
:

```
0: What would you like to see happen in this conversation?
1: I'd like to talk and sort out whether to write an explanation at this point or implement a feedback button first, because I'm thinking about what to do.
0: Is this a good place to end up?
score: 0.5000
negative(z), neutral(x), positive(c), quit(q)>
```

This is, of course, because "at this stage, 'is this a good place to end up?' is not good", so NEGATIVE

Try it.
- Currently not very good.
- Consideration of why
    - Currently, active learning is no different from random because we don't know what to use as features in the first place.
    - It takes a lot of time and effort if it is presented randomly, because we look at the flow of the dialogue and decide if it is appropriate to end it at this point in time.


---
This page is auto-translated from [/nishio/終わりのデザイン能動学習](https://scrapbox.io/nishio/終わりのデザイン能動学習) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.