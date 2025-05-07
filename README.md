# Nody

**Connect your tools to AI—securely, visually, and at scale.**

**Nody** is a developer-first platform designed to manage and deploy Model Context Protocol (MCP) servers and toolsets. It enables seamless composition and deployment of your internal tools, APIs, and enterprise services to AI agents through an intuitive visual interface—no more hand-coding complex JSON configs. 

🌐 Try it out: [https://mcp.nody.dev](https://mcp.nody.dev)

🚀 Get started: [mcp.nody.dev/getting-started](mcp.nody.dev/getting-started)

## 🔧 Key Features 

- MCP Composer<br/>
  A powerful visual interface for composing, editing, and managing MCP servers and tool collections. 
- Tool Personalization<br/>
  Customize metadata, inputs, outputs, and documentation to optimize tool context for AI agents. 
- Stick & Scale<br/>
  Seamlessly expand MCPs by adding new tools without reconfiguring your stack.
- Enterprise Security _(Coming soon)_ <br/>
  Role-based access control and full audit logging across all MCP servers. 
- MCP Sharing _(Coming soon)_ <br/>
  Publish and share MCP configurations via public or private repositories with attribution. 

## 🏗️ Architecture 

- Graph-based backend using Neo4j for tool and relationship modeling. 
- Distributed execution layer powered by a Node.js runtime environment. 
- Orchestration and automation through [Olympe](https://www.olympe.io/) technology.

## 📖 How to use

Once your custom MCP is built on [Nody](mcp.nody.dev), you'll get a JSON content to copy into your favorite MCP client that looks like this:

```JSON
{
  "mcpServers": {
    "<custom mcp name>": {
      "command": "npx",
      "args": [
        "-y",
        "@olympeio/nody-vmcp@latest"
      ],
      "env": {
        "NODY_VMCP": "<custom MCP unique id>",
        "NODY_KEY": "<your very own secret encryption key>" // OPTIONAL, used when authenticated, required to use secret values
      }
    }
  }
}
```

This will start the Nody MCP and load the list of tools that you inserted in the MCP edition panel.

### Override descriptions

To create an MCP tailored to your needs and provide clearer context to AI agents, you can customize the name and description of each tool in your Custom MCP. This schema helps AI models understand the available tools while allowing fine-tuned descriptions beyond vendor defaults.

### Requirements

Nody VMCP package is an NPM package that requires NodeJS 18+ to work properly.

You can check what version is installed on your machine with 
```shell
node --version
```

You can download and install the latest version from the [official website](https://nodejs.org/en/download).

## 💬 Community & Support 

Have a feature request or found a bug? Create a post in our [community forum](https://forum.olympe.io/) and upvote ideas you’d like us to prioritize. We value your feedback! 

## 🧩 Where You Can Use Nody MCPs 

Nody MCPs are fully **MCP-compliant** and can be deployed to **any platform or client that supports the Model Context Protocol**. Below is a sample of popular environments where Nody-powered MCPs are already being used or integrated: 

### 🤖 Chatbots 

Plug Nody MCPs directly into LLM chat interfaces to extend capabilities: 

- **Claude** (Anthropic)
- **ChatGPT** (OpenAI) 
- **Mistral-based apps**
- **Custom LLM UIs** using frameworks like LangChain or Semantic Kernel 

### 💻 Coding Assistants 

Enhance developer productivity by integrating tools into AI-enhanced IDEs: 

- **VSCode**
- **Cursor**
- **Zed, JetBrains IDEs** (planned)

### 🧠 Agentic Platforms 

Deploy tool-rich contexts into agent frameworks and workflow engines: 

- AgentForce 
- n8n
- LangGraph, Autogen, and other multi-agent orchestration platforms 

## 🔗 Related Links 

- [Official MCP Documentation](https://modelcontextprotocol.io)
- [Nody on NPM](https://www.npmjs.com/package/@olympeio/nody-vmcp)

 
