
- every agent can be cloud-infrastructure aware (providing context)
    - MCP resources - read only form
    - MCP tools - actions that manipulate the data
    - HF - free MCP course https://www.marktechpost.com/2025/05/15/hugging-face-introduces-a-free-model-context-protocol-mcp-course-a-developers-guide-to-build-and-deploy-context-aware-ai-agents-and-applications/
  - A2A - pure communication layer - read protocol by Google - https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/ #read
	  - messages in JSONs (request, response), async callbacks, messges can contain files, docs, multimedia
	  - agent card (name, version, skills)
	  - artifact - result of the task
	  - security - oauth, keys
	  - each agent will typically run on its own port or endpoint
	  - sample clients and even a2a demo https://github.com/a2aproject/a2a-samples #try
  - list of MCP servers https://www.kdnuggets.com/32-mcp-servers-you-need-to-check-out-now
  - opensource MCP servers including Telegram, Youtube, Postgre, Figma: https://github.com/modelcontextprotocol/servers?ref=blog.min.io
  - Remote GitHub MCP Server is now in public preview in VS Code or Visual Studio, after authenticating with PAT or OAuth2.0 AI can start using tools
  