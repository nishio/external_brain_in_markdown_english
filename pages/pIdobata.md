---
title: "pIdobata"
---

[[dev container]]

<img src='https://scrapbox.io/api/pages/nishio-en/Claude/icon' alt='Claude.icon' height="19.5"/>
This project already has a Docker Compose setup, but by using Dev Container, you can create a development environment that integrates VS Code and Docker.
Create a Dev Container configuration:
- Bash(mkdir -p .devcontainer)
- Write(.devcontainer/devcontainer.json)
- Write(.devcontainer/docker-compose.override.yml)
- Write(.devcontainer/README.md)

Dev Container configuration has been created. The usage is as follows
setup procedure
1. install the necessary tools
- Docker Desktop
- VS Code extension "Dev Containers" (ID: ms-vscode-remote.remote-containers)
- Set environment variables
cp .env.example .env # or .env.template
2. set necessary environment variables in .env file
- Start Dev Container
- Open a project in VS Code
- Cmd/Ctrl + Shift + P to open command palette
- Select "Dev Containers: Reopen in Container
The first time it takes a while to build, but after that you can access the service on the following ports
- Frontend: [http://localhost:5173](http://localhost:5173)
- Policy Frontend: [http://localhost:5174](http://localhost:5174)
- Admin: [http://localhost:5175](http://localhost:5175)
- APIs: 3000, 3001, 8000
Within the Dev Container, the VS Code terminal runs directly within the container, with integrated hot reloading and debugging.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
What does it mean to have both .env.example and .env.template?
- I'm not sure about .env.example, update .env.template to .env and everything else.
- Look at Azure Portal and figure out AZURE_OPENAI_API_VERSION and so on.

![image](https://gyazo.com/901c2100c09344d22b79ca5917d5769d/thumb/1000)
Nope.

---
This page is auto-translated from [/nishio/pIdobata](https://scrapbox.io/nishio/pIdobata) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.