# Nody

<p style="text-align: center;">
  <img src="https://mcp.nody.dev/assets/nody-logo.svg" alt="Nody" width="96"/><br/>
  <b>One MCP Server to TOOL them all!</b>
</p>

Nody is a developer-first platform for managing and deploying Model Context Protocol (MCP) servers and toolsets. Nody technology maintains the tools collections in a knowledge graph. Nody clients exposing tools to your AI Agents request the knowledge graph to discover what tool should ben installed and exposed.

# Overview
Nody provides a powerful MCP Composer for creating and managing custom MCP servers. It enables you to personalize each tool's name and description to add context, helping agents use them with fewer tokens. It manages the configurations and secrets of MCP servers in one secure place, making it easier to deploy and scale your AI toolsets efficiently.

# Features

- **MCP Composer**  
  A powerful visual interface for composing, editing, and managing MCP server tools into collections built around specific use cases.

- **Tool Customization**  
  Customize tool names and descriptions to optimize context for AI agents based on your desired use cases.

- **Configure Agents Once**  
  Configure agents once and maintain tool collections and their descriptions through a centralized UI. No need to reconfigure agents later.

- **Secure Configuration Storage**  
  Secret values (API keys, tokens, etc.) are encrypted and stored securely. The encryption key is stored in a Vault accessible only by you.

- **Monitor Execution of Collections**  
  Track the execution of your collections and tools to know whether they're running properly.

- **Add Servers to Catalog**  
  Extend your catalog by adding servers already deployed on NPM or UV public registries. Define the required configuration parameters and secrets to run them securely.

# How to Use

Once your Nody client is composed at [Nody](https://mcp.nody.dev), click the `Run it` button to get installation instructions.

Example of a Nody client configuration to add to your favorite MCP client:

```json
{
  "mcpServers": {
    "<Nody client name>": {
      "command": "npx",
      "args": [
        "-y",
        "@olympeio/nody-vmcp@latest"
      ],
      "env": {
        "NODY_CLIENT_ID": "<Nody client id>", // REQUIRED, your Nody client ID
        "NODY_USER_KEY": "<your very own secret encryption key>" // OPTIONAL, used when authenticated, required to decrypt secret values
      }
    }
  }
}
```

This starts the Nody client and loads the list of tools included in the collection with the configured customizations.

## Requirements

The Nody VMCP package is an NPM package that requires Node.js 18+ to work properly.

Check your installed Node.js version with:
```shell
node --version
```
Download the latest version from the [official website](https://nodejs.org/en/download).

# Roadmap
Planned features and improvements:

- **Enterprise Security**  
  Use your enterprise vault to store encryption keys. Enterprise-grade governance for AI tooling.

- **Collection Sharing (Templates)**  
  Publish and share MCP configurations through public or private repositories with attribution.

- **Code Your Own Tools**  
  Write and test your tools directly in Nody without needing to publish them on NPM, UV, or Docker.

- **Integration of Existing APIs**  
  Integrate APIs from your IT landscape into AI agents by wrapping them as MCP tools and composing them into collections.

- **Add Docker and Local Servers**  
  Add servers not deployed on NPM or UV registries, including local or Docker-based servers, and use them in the MCP Composer.

# Architecture

Nody clients are lightweight runtimes built on top of the Olympe Technology: a knowledge graph stored in a dedicated graph database describes the compositions of tools in collections, custom MCP and names and descriptions overrides. Nody Clients are distributed and connected to a centralized orchestrator providing required graph portions for the execution of the tools. Updates on tools and collections are notified in real time thanks to our event driven distributed archtitecture.

# Links

- [Nody](https://mcp.nody.dev)
- [Official MCP Documentation](https://modelcontextprotocol.io)
- [Nody on NPM](https://www.npmjs.com/package/@olympeio/nody-vmcp)

# License
Copyright (C) Olympe S.A. - All Rights Reserved
Unauthorized copying of any of the files contained in this project, via any medium is strictly prohibited
Proprietary and confidential
