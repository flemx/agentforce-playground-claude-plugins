# Salesforce AgentForce Plugin Marketplace

> **Experimental playground for Salesforce AgentForce integrations with Claude Code**

A curated collection of plugins, skills, and tools designed to supercharge Salesforce Solution Engineers and developers working with AgentForce AI agents. This marketplace provides ready-to-use integrations, automation tools, and demo capabilities for Claude Code.

---

## 🎯 What is This?

This is a **Plugin Marketplace** for [Claude Code](https://code.claude.com) — a specialized collection of Salesforce and AgentForce-related plugins that extend Claude Code's capabilities for working with Salesforce ecosystems.

### Why a Marketplace?

Plugin marketplaces allow you to share reusable plugins with your team or organization. Instead of manually installing plugins on each machine, you can:

- 📦 **Share once, use everywhere** — Publish plugins to a central repository
- 🔄 **Auto-sync** — Team members automatically get access to all marketplace plugins
- 🚀 **Rapid deployment** — Solution Engineers can quickly set up demos and proof-of-concepts
- 🧪 **Experiment safely** — Test experimental features in a controlled environment

Learn more about plugin marketplaces in the [official documentation](https://code.claude.com/docs/en/plugin-marketplaces).

---

## 🎪 What's Inside

### Current Plugins

#### 1. **AgentForce Plugin** (`agentforce`)

A comprehensive plugin for Salesforce AgentForce development and demonstrations.

**What it includes:**

- **Skills:**
  - `agentforce-portal` — Automated setup and deployment of a customizable Next.js portal for showcasing AgentForce AI agents

- **MCP Servers:**
  - **Heroku MCP** — Deploy apps to Heroku directly from Claude Code
  - **Salesforce DX MCP** — Interact with Salesforce orgs, metadata, data, users, and run Apex tests

**Perfect for:**
- Solution Engineers building customer demos
- Developers prototyping AgentForce integrations
- Teams exploring AgentForce capabilities

---

## 🚀 Getting Started

### Prerequisites

- [Claude Code](https://code.claude.com) installed
- [Salesforce CLI](https://developer.salesforce.com/tools/salesforcecli) (for Salesforce DX MCP)
- [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli) (for Heroku deployments)

### Installation

#### Option 1: Clone This Marketplace

```bash
git clone https://github.com/your-org/agentforce-playground.git
cd agentforce-playground
```

Then add this marketplace to your Claude Code settings.

#### Option 2: Add Individual Plugins

Navigate to the plugin you want:

```bash
cd agentforce
```

And follow the plugin-specific installation instructions.

---

## 📚 Plugin Documentation

### AgentForce Portal Setup (`agentforce-portal` skill)

The `agentforce-portal` skill automates the entire process of setting up a personalized demo portal for showcasing Salesforce AgentForce AI agents.

**What it does:**

1. ✅ Checks and installs prerequisites (Node.js, Git)
2. ✅ Clones and sets up the Next.js portal application
3. ✅ Configures Salesforce integration automatically
4. ✅ Customizes the landing page based on your requirements
5. ✅ Starts the development server

**Usage:**

```
# In Claude Code, invoke the skill:
Use the agentforce-portal skill to set up my demo
```

**Features:**
- 🤖 **Fully automated** — Minimal user intervention required
- 🎨 **Customizable** — Personalize landing pages, logos, and branding
- 🔗 **Salesforce integrated** — Connects directly to your Salesforce org and agents
- 🚀 **Deploy ready** — Includes Heroku deployment support

**What you'll need:**
- Salesforce org with AgentForce agents configured
- Domain URL from your Salesforce org
- Connected App credentials (Client ID & Secret)

For detailed documentation, see [`agentforce/skills/agentforce-portal/SKILL.md`](agentforce/skills/agentforce-portal/SKILL.md)

---

## 🔧 MCP Servers Included

### Heroku MCP

Deploy and manage Heroku applications directly from Claude Code.

**Available commands:**
- Create new Heroku apps
- Deploy applications
- Manage environment variables
- View logs and status

### Salesforce DX MCP

Comprehensive Salesforce development toolkit.

**Available toolsets:**
- **Orgs** — Manage Salesforce orgs and authentication
- **Metadata** — Deploy and retrieve metadata
- **Data** — Import/export data
- **Users** — Manage users and permissions

**Special tools:**
- `run_apex_test` — Execute Apex tests from Claude Code

---

## 🎯 Use Cases

### For Solution Engineers

- **Quick Demos** — Set up a branded AgentForce portal in minutes
- **Customer Workshops** — Create personalized demo environments
- **Proof of Concepts** — Rapidly prototype AgentForce solutions

### For Developers

- **Local Development** — Full Salesforce DX integration
- **Deployment Automation** — One-command Heroku deployments
- **Testing** — Run Apex tests without leaving your editor

### For Teams

- **Shared Playground** — Experiment with new AgentForce features
- **Knowledge Sharing** — Standardized setup processes
- **Best Practices** — Curated tools and workflows

---

## 🛠️ Plugin Structure

```
agentforce-playground/
├── README.md                          # This file
├── agentforce/                        # Main AgentForce plugin
│   ├── .claude-plugin/
│   │   └── plugin.json               # Plugin metadata
│   ├── .mcp.json                     # MCP server configurations
│   └── skills/
│       └── agentforce-portal/
│           └── SKILL.md              # Portal setup skill
└── [future-plugins]/                 # Additional plugins coming soon
```

---

## 🧪 Experimental & Demo Features

> ⚠️ **Note:** This is an experimental playground. Plugins and features may change as we explore new AgentForce capabilities.

**Current experiments:**
- Automated portal setup with intelligent customization
- Streamlined Salesforce authentication flows
- One-click Heroku deployments

**Coming soon:**
- AgentForce API testing utilities
- Conversation flow builders
- Multi-agent orchestration tools
- Custom agent templates

---

## 📖 Learn More

### Claude Code Resources

- [Plugin Marketplaces Documentation](https://code.claude.com/docs/en/plugin-marketplaces)
- [Creating Custom Skills](https://code.claude.com/docs/en/skills)
- [MCP Server Integration](https://code.claude.com/docs/en/mcp)

### Salesforce Resources

- [AgentForce Documentation](https://help.salesforce.com/s/articleView?id=sf.einstein_agentforce_overview.htm)
- [Salesforce DX Developer Guide](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/)
- [AgentForce API Guide](https://developer.salesforce.com/docs/einstein/genai/guide/agent-api.html)

---

## 🤝 Contributing

This is an experimental playground! Contributions, ideas, and feedback are welcome.

### Adding a New Plugin

1. Create a new directory for your plugin
2. Add `.claude-plugin/plugin.json` with metadata
3. Include any skills, MCP servers, or tools
4. Document usage in a README or SKILL.md file

### Improving Existing Plugins

1. Fork this repository
2. Make your improvements
3. Test thoroughly in Claude Code
4. Submit a pull request with documentation

---

## 📝 License

[Your License Here]

---

## 👤 Author

**Damien Fleminks**

---

## 🙏 Acknowledgments

- Built for the Salesforce Solution Engineering community
- Powered by [Claude Code](https://code.claude.com)
- Inspired by the potential of AgentForce AI

---

## 🐛 Issues & Support

Found a bug or have a feature request?

- Open an issue in this repository
- Contact the plugin maintainer
- Check the [Claude Code documentation](https://code.claude.com/docs)

---

## 🔮 Roadmap

- [ ] Add more AgentForce integration patterns
- [ ] Create skills for common Salesforce workflows
- [ ] Build agent conversation testing tools
- [ ] Add support for Salesforce sandbox management
- [ ] Create templates for custom agent types
- [ ] Integrate with Salesforce Analytics

---

**Happy building with AgentForce! 🚀**
