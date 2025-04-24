---
title: "Code sharing between actions in Github Actions"
---

[[Ask GPT4 about technology]].
I have a code I want to share with multiple actions, what do you think I should do? I asked him, and he said this would be fine.
:

```
- name: Run Script 1
  run: |
    # Add the library to the PYTHONPATH so that you can import it
    export PYTHONPATH=$PYTHONPATH:$GITHUB_WORKSPACE/shared_lib
    python .github/actions/script1.py

- name: Run Script 2
  run: |
    # Again, add the library to the PYTHONPATH
    export PYTHONPATH=$PYTHONPATH:$GITHUB_WORKSPACE/shared_lib
    python .github/actions/script2.py
```


One export is fine, right? I asked, and it was one time.
:

```

 # Set environment variables for all steps in this job
 env:
   PYTHONPATH: ${{ github.workspace }}/shared_lib
```


That's not good enough, right? I asked.

:

```
    # Retrieve and update PYTHONPATH for all steps in this job
    env:
      ORIGINAL_PYTHONPATH: ${{ steps.setup.outputs.pythonpath }}
      PYTHONPATH: ${{ steps.setup.outputs.pythonpath }}:${{ github.workspace }}/shared_lib

    steps:
    - name: Get original PYTHONPATH
      id: setup
      run: echo "::set-output name=pythonpath::$(python -c 'import sys; print(":".join(sys.path))')"
```


Hmmm, not so good.

---
This page is auto-translated from [/nishio/Github Actionsのアクション間でコード共有](https://scrapbox.io/nishio/Github Actionsのアクション間でコード共有) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.