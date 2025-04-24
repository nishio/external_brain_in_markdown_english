---
title: "self-caution"
---

I used to think of [[attention mechanism]] as an RNN, "keep the past hidden states and calculate the attention intensity based on them...", because [[Transformer]], which achieved its results using only the attention mechanism, is not an RNN, Mental models that assume RNNs are wrong.

The concept of "self-attention" that is not "source-target attention" does not ring a bell when RNNs are implicitly assumed, so we need to forget about it for a moment.

Self-attention makes itself the source and target.
- The attention used in the Transformer decoder is self-attention is the input source receives input from the lower layers of the decoder
    - In this case, it is more like [[CNN]] rather than RNN
    - It doesn't recurrent at all, so if you have the old "caution mechanism" explanation in your head that says, "Save the past hidden layer values..." you need to forget it because it's confusing.
    - It is more straightforward to think of it as a development of CNN, since it uses an attention mechanism for input from layers below you.
    - Image-derived CNNs perform convolution with fixed weights from surrounding points based on the assumption that the influence of a point on the surrounding points will be strong and the influence of the surrounding points on the point will be constant.
    - The convolution size is fixed, but the self-attention mechanism extends it to the entire input. It becomes an input of indefinite length.
    - The reason why this is possible is that the general mechanism of attention mechanisms is that the attention weights are determined by a function of the inputs. Unlike CNNs, which have a fixed weight matrix, the number of inputs can be arbitrary.

---
This page is auto-translated from [/nishio/自己注意](https://scrapbox.io/nishio/自己注意) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.