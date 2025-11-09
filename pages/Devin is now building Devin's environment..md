---
title: "Devin is now building Devin's environment."
---

[[Devin]] is now building Devin's environment.
- I gave him the [[Team Mirai Action Board]] repository and asked, "What do I do?" I asked him, "What should I do?" and he read the README and did everything!
It's a Roo Code-like style that asks for approve, but I completed the whole thing without any problems.

Below is a summary of the logs
<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
Main workflow performed by Devin (brief summary)
1. survey of repositories
    - Verified that it has been `git pulled`, read the directory structure and `package.json` to identify it as a Next.js + Supabase backend project.
2. check for necessary tools
    - Refer to README and determine that Node.js, Docker, and Supabase CLI are required for setup.
- Preparation of environment variables
    - Create `.env.local` by copying `.env.example` and prepare only a vessel for confidential information (the value will be entered by the user later).
4. installation of dependencies
    - Node and Docker were determined to have already been installed.
    - Tried and deployed Supabase CLI using multiple methods (npm/apt/official scripts/GitHub Release binaries).
    - Install package dependencies with `npm install`.
5. maintenance command registration
    - Set up `npm install` as a command for dependency update.
- Lint setting
    - Detects `biome:check:write` script and registers it as a Lint command.
7. test setup
    - Run `npm test` (unit test) to confirm success and register it as a test command.
8. presentation of local startup procedures
    - Explain how to run the development server, including the assumption that Supabase will be started.
9. additions and clean-up
    - Additional notes are omitted due to the extensive README.
    - Remove temporary files created by Supabase CLI deployment and return git status to clean.
10. declaration of setup completion
    - Reported that the above steps were saved as a snapshot and ready to be reused in the next Devin session.
In short, the process of generating environment variable templates, CLI/dependent package installation, Lint/testing/maintenance of startup procedures, and repository cleanup were all performed automatically in a single step.

---
This page is auto-translated from [/nishio/DevinがDevinの環境構築をするようになった](https://scrapbox.io/nishio/DevinがDevinの環境構築をするようになった) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.