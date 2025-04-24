---
title: "MCP server built 2025-02-04"
---

from  [[Diary 2025-02-03]]
MCP server built 2025-02-04

2/3
I was having a conversation with o3 about what I wanted to do, but also how to design it for future expansion.
- 1: Implement the functionality I need in a command line Python script and call it with a hotkey.
- 2: Build an HTTP server that can call those tools.
I see.
So whether you use MCP or not, the direction is the same.
I still think you should touch the MCP server architecture (aside from whether it's still MCP in the future).

2/4
Observe the irregular processes that my clients (me) go through on a daily basis.
Find the common steps that are repeated in it,
Then, it is made into a tool so that it can be easily called (this is where [[input/output standardization]] and documentation is done).
Then create an API server that calls it (this is where you can do the [[service discovery]] thing).
AI agents use discovery of what tools are available


I have a [[MCP server]] that runs Python scripts,
I was able to call from both [[Roo Code]] and [[Claude Desktop]],
Theoretically, they could do whatever they wanted.
- [[my-tools]]


Rather than releasing this MCP server as a general-purpose "something others use" and maintain it.
It's better to make it your own and verbalize your knowledge as code, like "I keep my papers here in Dropbox".
I think it would be more productive as a "me + AI agent."
People who use generic tools end up doing "highly abstract system descriptions" that customize those generic tools to their own situation.


It's a matter of creating your own MCP server, something you can just tell Roo Code that you want to create and they'll make it for you,
If you tell them in natural language, "I want to add this kind of functionality to the server," they will create it for you.
It's kind of like the existence of "[[glue code]]" is changing.


2025-02-04
[Debugging - Model Context Protocol](https://modelcontextprotocol.io/docs/tools/debugging)
[Inspector - Model Context Protocol](https://modelcontextprotocol.io/docs/tools/inspector)
<img src='https://scrapbox.io/api/pages/nishio-en/GPT/icon' alt='GPT.icon' height="19.5"/>
- Claude Desktop automatically launches servers as child processes when the application is launched, based on the startup commands (e.g., "node" and "npx") for each MCP server described in the configuration file (claude_desktop_config.json).
- In other words, users do not need to manually start individual servers, but Claude Desktop itself reads the configuration information and establishes and manages the connection by communicating with the server via the MCP protocol through standard input/output (STDIO) and other means.

[[cosense-mcp-server]]
[yosider/cosense-mcp-server: A MCP Server for Cosense](https://github.com/yosider/cosense-mcp-server)
I started tinkering with the
- There is an instruction ListResources to get a list of resources and an instruction ReadResource to get a resource.
- Similarly, there are ListTools and CallTools
I had Devin add a write function with reference to [[write_cosense]].
- [https://github.com/nishio/cosense-mcp-server/pull/1](https://github.com/nishio/cosense-mcp-server/pull/1)
- I tried to add a write function to the MCP server based on the write script to Cosense I made the other day, but debugging the MCP server was tricky to begin with, so AI bugged it and there was nothing I could do about it. w
    - I ended up experimenting with smaller units myself.
- The concept is not very difficult, but it can die without error logging.
- It's like a toaster that makes an error but disappears before you can read it properly, or something awful like that.

As for write
These tools can first be called from the command line

As for read.
- Top 100 cases acquired
- Keyword search by project
- Keyword search without specifying a PROJECT
- Follow a link from a specific page to read it.
    - The one I did with [[concatPages]].

---
This page is auto-translated from [/nishio/MCPサーバを作った2025-02-04](https://scrapbox.io/nishio/MCPサーバを作った2025-02-04) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.