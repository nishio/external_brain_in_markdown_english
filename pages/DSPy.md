---
title: "DSPy"
---

2025-04-13
[[LLM self-improving prompt optimization]].
<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4.5/icon' alt='GPT-4.5.icon' height="19.5"/>
As of 2025, the LLMs themselves have made the following progress in the automatic improvement of prompts (DSPy-like approaches)

- Subsequent development of DSPy.
    - DSPy is a system that automates prompt improvement, but now also includes [[Self-Refine]] and [[Reflexion]], which incorporate [[self-reflection]] and [[self-correction]].
    - Performance was greatly improved by having the models evaluate their own responses and come up with ideas for improvement.

- Limitations of self-reflection and self-correction.
    - Self-correction prompts are effective, but it is not easy for the model to find its own errors, and conversely, performance can deteriorate.
    - For this reason, research is underway to augment feedback with external information (e.g., search engines) and reinforcement learning.

- Utilization of self-reinforcement learning.
    - Widespread methods of giving feedback on one's answers and self-generating and fine-tuning that data (e.g., [[Google's SCoRe]]).
    - Meta and others have a self-evaluation mechanism (judges) in their models to achieve improved performance without additional human evaluation.

- Status of Practical Application.
    - DSPy has already been put into practical use by companies, greatly reducing the time and effort required to adjust prompts.
    - Self-improvement and self-correction capabilities are gradually beginning to be built into commercial LLMs.

It is predicted that this direction of "learning and improving the model itself" will continue to attract attention and will be further developed through external collaboration and more sophisticated self-assessment.
<img src='https://scrapbox.io/api/pages/nishio-en/DR/icon' alt='DR.icon' height="19.5"/>[https://chatgpt.com/share/67fc6ef4-d220-8011-8337-030850f6ed70](https://chatgpt.com/share/67fc6ef4-d220-8011-8337-030850f6ed70)

---
2024-05-02
[[stanfordnlp/dspy]]は [[Automated Prompt Engineering]] の有望なアプローチであり、将来的なLMプログラミングの方向性を示唆していると言えます。<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
What is DSPy?
- Python framework for building pipelines using language models (LM)
    - Declarative module definition
    - Pipeline construction by synthesizing modules
    - Automatic prompt optimization

Basic Concept of DSPy
- pipeline
    - Pipeline is a workflow that combines modules
    - Accomplishes complex tasks by connecting the output of one module as an input to another
- module
    - Module is a component that abstracts the LM call
- signature
    - Signatures interface with module inputs and outputs
- compiler
    - The compiler optimizes the pipeline
    - Improve overall pipeline performance by generating optimal prompts and adjusting parameters for each module

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
Specifically, in the tutorial, you'll see a signature like this
python

```
class BasicQA(dspy.Signature):
    """Answer questions with short factoid answers."""

    question = dspy.InputField()
    answer = dspy.OutputField(desc="often between 1 and 5 words")
```

This is converted internally into something called Template, which looks like this
py

```
(Pdb) print(template)
Template(Answer questions with short factoid answers., ['Question:', 'Answer:'])
```

This has __call__, so pass example
py

```
(Pdb) print(example)
{'demos': [], 'question': 'What is the nationality of the chef and restaurateur featured in Restaurant: Impossible?'}

(Pdb) print(template(example))
Answer questions with short factoid answers.

---

Follow the following format.

Question: ${question}
Answer: often between 1 and 5 words

---

Question: What is the nationality of the chef and restaurateur featured in Restaurant: Impossible?
Answer:
```


Adding a case study to exapmle.demos would look like this
py

```
(Pdb) example.demos.append({"question": "SAMPLE_QUESTION", "answer": "SAMPLE_ANSWER"})
(Pdb) print(template(example))
Answer questions with short factoid answers.

---

Follow the following format.

Question: ${question}
Answer: often between 1 and 5 words

---

Question: SAMPLE_QUESTION
Answer: SAMPLE_ANSWER

---

Question: What is the nationality of the chef and restaurateur featured in Restaurant: Impossible?
Answer:
```


This is the "Generate Prompt."
So what is "automatic prompt optimization"?
As the simplest example, here's what the tutorial does
py

```
teleprompter = BootstrapFewShot(metric=validate_context_and_answer)

# Compile!
compiled_rag = teleprompter.compile(RAG(), trainset=trainset)
```


BootstrapFewShot is what decides what to put on the exapmle.demos I mentioned earlier, and I call LabeledFewShot inside and randomly select k from the trainset.
- There are bayes and optuna in the repository.

Calculate the percentage of correct answers by what was not used in the demos (this is passed from outside the evaluation function in the metric above).
The one with the highest percentage of correct answers is chosen, which is read as "COMPILE".

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/><img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
This sequence of processes is called "compilation. In other words, we regard a prompt as a kind of "machine language," and the process of optimizing it is called compilation.

This idea is analogous to the emergence of [[C]] in the history of programming languages, which greatly streamlined programming as a [[high-level language]] that could be compiled against a variety of architectures. Similarly, frameworks such as DSPy have the potential to streamline application development with LLMs by automatically generating optimal prompts for various LLMs.

However, it is unclear at this time whether DSPy will become the new C language. After all, muddy but practical tends to become the de facto standard. (PS: When [[FORTRAN]] appeared, compilation was called [[Automatic Programming]]. Later, the later C language took market share.)

Another challenge in using DSPy is the definition of the evaluation function (metric). It is not easy to define an appropriate metric for each task. The skill to decompose customer needs into tasks for which metrics can be easily defined will be required.
Although LM could be used in the definition of the metric itself, the number of iterative executions would be high, resulting in high optimization pressure. Therefore, an efficient implementation that leverages existing natural language processing knowledge may be necessary.

In general, DSPy is a promising approach to automated prompt engineering and suggests future directions for LM programming. On the other hand, many practical challenges still remain, and it will be interesting to see how DSPy and other frameworks evolve.

relevance
    - [[Boundaries of LLM Renewal and Needs]]

---
This page is auto-translated from [/nishio/DSPy](https://scrapbox.io/nishio/DSPy) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.