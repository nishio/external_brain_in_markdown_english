---
title: "Cline Code Reading"
---

[https://github.com/cline/cline](https://github.com/cline/cline)
private [https://chatgpt.com/c/677f734a-45f8-8011-9dec-69a03aa86473](https://chatgpt.com/c/677f734a-45f8-8011-9dec-69a03aa86473)
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
- This code set is a set of UI logic for React apps running on the VSCode extension webview to let the "AI agent" perform actual development tasks (file operations, command execution, etc.). The VSCode extension enables actual operations (e.g., file editing, command execution, browser operations, etc.) by exchanging messages between the main body and React in the webview. The following is a more detailed explanation of how the logic is executed.

1. logic flow in ChatView
    - 1-1. handling user input (text & images)
        - When a user inputs and submits a text in the ChatTextArea component, the following process runs.
            - Text and image data are compiled and sent to the extension as vscode.postMessage({ type: "newTask", ... }) or askResponse. }) or askResponse to the extension (handleSendMessage in ChatView, handlePrimaryButtonClick when a button is pressed, etc.).
            - Upon receiving this, the extension starts and continues communication with the AI agent.
    - 1-2. receiving messages from extensions and drawing updates
        - The Webview side (App.tsx / ChatView) listens for messages via useEvent("message", ...) etc., and waits for a message,
            - API request started (api_req_started),.
            - Tool use (e.g. file editing) (tool),.
            - Command Execution (command),.
            - Browser Action (browser_action),.
            - Final result (completion_result)
        - and update React's state (e.g., clineMessages) when the information arrives.
        - Depending on the updated state, the ChatRow and BrowserSessionRow components are drawn as a list and reflected in the UI.
        - For example, the loading message is displayed when api_req_started is received, and the message is "completed" when api_req_failed or api_req_started with cost information (message to be retransmitted) is received. The "completion" message is displayed when api_req_started (with cost information) is received.

    - Concept of "Task" and Approve/Reject Flow
        - Within a single large task, AI will "suggest" actions such as "I want to edit a file," "I want to execute a command," or "I want to use a browser" (= ask message).
        - When these are received, ChatView will ask the user for permission by displaying an "Accept / Reject" button, etc. The user can then click on the "Accept" button to accept or decline the request.
        - When the button is pressed, the askResponse is sent to the extension, and the VSCode extension executes the process according to approval or rejection.
        - If the user is caught in a "mistake limit" or "auto approval limit," the logic allows the user to choose whether to continue or start a new task, etc. is also implemented in the same way, branching the screen based on the message type (e.g., ask = "mistake_limit_reached").

2. internal logic of file operations and command execution
- 2-1. tool (e.g. tool = "editedExistingFile") flow
    - AI passes instructions (e.g., diffs, contents of new files, etc.) as ask: "tool" or say: "tool" to indicate that the file should be edited in this way.
    - ChatRow side judges the value of tool.tool and displays UI according to editedExistingFile / newFileCreated / readFile / searchFiles etc.
    - When approval is required, a button is issued and the askResponse is sent with a click.
    - If approved, the extension itself will perform the actual file editing through the VSCode API (or do nothing if rejected).
- 2-2. command execution ( command )
    - The AI sends the message "I want to execute this command in the terminal.
    - On the UI, the command & output is displayed in ChatRow, and when the approval button is pressed, the command is executed in the terminal (or Shell) of the extension itself.
    - The standard output/standard error output during execution may be partially returned again in the form of api_req_started→command_output, which is then reflected and written to the real-time output.
- 2-3. browser operation( browser_action )
    - Using the BrowserSessionRow mechanism, AI successively suggests actions such as "accessing a specific site," "clicking," and "scrolling.
    - If we proceed with approval, the extension itself will control the headless browser, etc. to retrieve the captured text and send a "with screenshot" result message to the webview again to update the UI.

3. role of state management and context (ExtensionStateContext)
- 3-1. centralized management of all extensions status
    - The state (ExtensionState) that ExtensionStateContext holds in the extension is wrapped as a Context in React, and can be read and written by any component with useExtensionState().
    - for example
        - Selected API provider or model ID (apiConfiguration)
        - Past task history (taskHistory)
        - Theme Information (theme)
        - List of MCP related servers (mcpServers)
    - and others are concentrated here.
- 3-2. message-by-message branching
    - React side (handleMessage) receives message -> switch (message.type) to state, theme, workspaceUpdated, partialMessage, openRouterModels, mcpServers ...etc., and setState(...) and setMcpServers(...) respectively. and setMcpServers(...) respectively.
    - The updated Context state is passed on to ChatView, SettingsView, etc., and the UI is refreshed.

4. history management and checkpoints
- 4-1. HistoryView
    - A component that searches and displays past tasks (taskHistory).
        - Search (Fuzzy search) using Fuse.js to narrow down and sort the search results.
        - The selected task ID can be redisplayed by vscode.postMessage({ type: "showTaskWithId", ... }) to redisplay the task ID.
- 4-2. checkpoints (compare and restore differences)
    - Snapshots of the workspace can be taken at each stage of the process, and the CheckpointControls buttons can be used to "view differences at this point" and "restore to this point".
    - Logic that throws a checkpointDiff / checkpointRestore message to the extension at the push of a button, and the extension receives it and performs a Git diff or restore operation.

MCP (Model Context Protocol) server extensions
- 5-1. list of MCP server connections
    - Displayed in McpView component.
    - The MCP server (a local server providing additional tools) is activated and connected by the extension, and its status and the tools it provides can be viewed here.
    - When the AI uses "use_mcp_server" to call an external resource or tool, the authorization UI also comes up.
- List tools/resources in McpToolRow and McpResourceRow
    - If a tool such as "execute_command" is registered, AI can use it dynamically.
    - The VSCode side manages the server startup commands and connection destinations, and if there is an error, the VSCode side can press the reconnect button, etc.

summary
- The central flow is that the VSCode extension controls real files, commands, browsers, additional tools, etc., while receiving AI suggestions (Ask), approval/rejection, and execution results (Say) in sequence.
- On the React side, the state is managed centrally in the context, and the appropriate UI is updated each time a message is received. When a user performs a UI operation, a response is sent to the extension via postMessage, and the process proceeds.
- Chat (message flow), file operations and command execution, history and checkpoints, and MCP tool management are all realized through React components.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Where exactly is this code running the tool?
(Cline)
The src/core/Cline.ts file contains the logic to execute the tool. In particular, the following methods are relevant to tool execution
- executeCommandTool method (lines 1069-1144):.
    - This method provides tools for executing commands. It manages the terminal and processes the output of the command.
- presentAssistantMessage method (lines 1271-2691):.
    - This method handles assistant messages and manages tool use. In particular, the part that processes the tool_use block is where the tool is executed.
- recursivelyMakeClineRequests method (line 2693-3007):.
    - This method recursively processes requests from users and API requests involving the use of tools.
These methods are directly involved in tool execution, especially when processing tool_use blocks.


In response to the question of whether I use LSP.
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
As far as this set of code is concerned, it does not make direct use of the Language Server Protocol (LSP). For example, it does not include any code that "invokes an LSP client to obtain code analysis results" or "LSP communication such as hover or completion," but instead uses the following methods to exchange information.

File and directory information
- There are tool calls such as listFilesTopLevel and listFilesRecursive, which directly retrieve directory listings and file contents using VSCode-side APIs and file system APIs.

Obtaining differences (DIFFERENCES)
- The extension itself calculates diffs against snapshots ("Checkpoints") managed by Git or other means, and sends them back to Webview.
- The image is not the calculation of code differences by LSP, but the utilization of version control information such as Git.

Search or "Extract Definition List".
- The regular-expression search or text-based parsing descriptions that appear in searchFiles and listCodeDefinitionNames also read the text of the file directly on the extension side, not in LSP, and return information by regular-expression matching, for example.

Command execution and browser operation
- Information when executing terminal commands or operating a headless browser is not routed through the Language Server Protocol.
- It is not related to LSP, as it is communicated via proprietary messages (api_req_started, command, browser_action, etc.) between the extension itself and the webview.

No code completion or symbol information acquisition using LSP
This code is written for the purpose of AI agent operations (file reading/writing, command and browser operations, etc.) with VSCode extension functions, and there is no evidence of parsing ASTs or obtaining code completion information by LSP. Therefore, we conclude that it does not handle type information, reference information, or diagnostics (warnings/errors) such as those obtained by the Language Server Protocol.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'm making my own ASTs and getting definition information.

---
This page is auto-translated from [/nishio/Clineコードリーディング](https://scrapbox.io/nishio/Clineコードリーディング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.