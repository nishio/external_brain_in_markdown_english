---
title: "Where to read the learned model"
---

In model_fn in model_fn_builder
python

```
if init_checkpoint:
  (assignment_map, initialized_variable_names
   ) = modeling.get_assignment_map_from_checkpoint(tvars, init_checkpoint)
```

I'm doing it.
- `tvars = tf.trainable_variables()`
- `init_vars = tf.train.list_variables(init_checkpoint)`
- Writing name→name mapping to assignment_map for each element in init_vars that is included in tvars
    - The comment says `"""Compute the union of the current variables and checkpoint variables.""` Isn't that Intersect, not Union?
- Why are we doing this?
    - This allows you to read both Pretrained and Fine-tuned models without worrying about

Then there are some branches where you have to put an adapter for the [[TPU]], but basically
python

```
tf.train.init_from_checkpoint(init_checkpoint, assignment_map)
```


- [tf.compat.v1.train.init_from_checkpoint  |  TensorFlow Core r2.0](https://www.tensorflow.org/api_docs/python/tf/compat/v1/train/init_from_checkpoint)
    - The first argument is a file name, etc.
    - assignment_map describes which variables map to which variables

- initialized_variable_names seems to be used only for log display

---
This page is auto-translated from [/nishio/学習済みモデルはどこで読むか](https://scrapbox.io/nishio/学習済みモデルはどこで読むか) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.