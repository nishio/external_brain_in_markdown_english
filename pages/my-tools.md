---
title: "my-tools"
---

MCP server to make my detailed automation tools available to AI agents as well.
private [https://github.com/nishio/my-tools](https://github.com/nishio/my-tools)
public [https://github.com/nishio/my-tools-mcp-server-public-preview](https://github.com/nishio/my-tools-mcp-server-public-preview)


2025-02-03
Create an MCP server
`$ mkdir my-tools`
`$ code my-tools`

add a tool
![image](https://gyazo.com/7717f93b75e0462be4ecbfe7286fa51a/thumb/1000)
As an experiment to call a local Python script, I'm going to make one that returns the current time when called.

Create MCP server
`$ npx @modelcontextprotocol/create-server time-server`
![image](https://gyazo.com/792ff0f0146383efe296bc993f010cf9/thumb/1000)

Since you have already built the MCP server, the next step is to add a tool that calls a Python script to this server. Edit the server's configuration file to add a tool that calls the Python script.
index.ts

```typescript
{
  name: "get_current_time",
  description: "Get the current time",
  inputSchema: {
    type: "object",
    properties: {},
    required: []
  }
}
```

I see
index.ts

```typescript
server.setRequestHandler(CallToolRequestSchema, async (request) => {
  switch (request.params.name) {
    case "get_current_time": {
      const { execSync } = require('node:child_process');
      const output = execSync('python3 current_time.py').toString().trim();
      return {
        content: [{
          type: "text",
          text: `Current time is: ${output}`
        }]
      };
    }

    default:
      throw new Error("Unknown tool");
  }
});
```

I see

![image](https://gyazo.com/9397c9b24c534d50c529db5fec707ebd/thumb/1000)

:

```
{
  "mcpServers": {
    "time-server": {
      "command": "node",
      "args": ["/Users/nishio/my-tools/time-server/build/index.js"],
      "env": {}
    }
  }
}
```


I am getting an error that the current_time.py script cannot be found. This is because the path to the script is not specified correctly; you need to specify the correct path when executing the script in execSync. The file is

![image](https://gyazo.com/3a91e72799336db50aecf8261f59ff20/thumb/1000)
I was able to do it!

![image](https://gyazo.com/31d89cd40a903e3d3687d2d8887c1f3d/thumb/1000)


Claude Desktop
![image](https://gyazo.com/05d47ace4d2c281ddeee0252ba078ae5/thumb/1000)
![image](https://gyazo.com/74a210bcf027356e5f02ac546d375ec3/thumb/1000)
ready, able

Now that I understand the logic, I'll figure out what to do in the future.
I don't want to have to create and configure a new server every time I make a small tool, so I'd like to have a server called my-tools, which is like a toolbox for all sorts of things.

`$ npx @modelcontextprotocol/create-server mcp-server`
and move the time-retrieval function of time-server to mcp-server

I was able to do it.

I think it would be more productive for "me + AI agent" to make this MCP server dedicated to myself and verbalize my knowledge as code, such as "I put my papers here in Dropbox", instead of publishing and maintaining this MCP server as a generic "others use it too".
- People who use generic tools end up doing "highly abstract system descriptions" that customize those generic tools to their own situation.
- For my personal use, it's twice as hard to generalize it and then specialize it for myself.
- Currently, the script is also an absolute path including my username.
- So I pushed it to private repo.
- On the other hand, I don't have any specific confidential information at this time, so I've put that in a separate public disclosure.

---
This page is auto-translated from [/nishio/my-tools](https://scrapbox.io/nishio/my-tools) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.