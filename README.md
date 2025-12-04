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

## ⚡ Quick Start

**Want to jump right in?**

1. Open Claude Code in VSCode
2. Run: `/plugin marketplace add https://github.com/flemx/agentforce-playground-claude-plugins.git`
3. Run: `/plugin` → Browse and install plugins → Select **"agentforce"**
4. Say: `Create an AgentForce portal`

That's it! Claude Code will set up everything automatically. 🎉

[See detailed installation instructions below](#-getting-started)

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

- [Claude Code](https://code.claude.com) installed (VSCode extension)
- [Salesforce CLI](https://developer.salesforce.com/tools/salesforcecli) (for Salesforce DX MCP)
- [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli) (for Heroku deployments)

### Installation

Follow these three simple steps to get started:

```
1️⃣ Add Marketplace  →  2️⃣ Install Plugin  →  3️⃣ Use Skills
```

#### Step 1: Add the Marketplace

Open Claude Code in VSCode and add this marketplace:

```
/plugin marketplace add https://github.com/flemx/agentforce-playground-claude-plugins.git
```

This connects Claude Code to this plugin marketplace, making all plugins available for installation.

#### Step 2: Install the AgentForce Plugin

Browse and install the plugin:

```
/plugin
```

Then:
1. Select **"Browse and install plugins"**
2. Find **"agentforce"** in the list
3. Click to install

#### Step 3: Start Using It!

Once installed, you can immediately start using the skills:

```
Create an AgentForce portal
```

Or invoke the skill directly:

```
Use the agentforce-portal skill to set up my demo
```

Claude Code will automatically handle the setup, from checking dependencies to launching your portal! 🚀

### What Gets Installed

When you install the AgentForce plugin, you get:

✅ **Skills:**
- `agentforce-portal` — Automated portal setup

✅ **MCP Servers:**
- Heroku MCP — Deploy to Heroku
- Salesforce DX MCP — Salesforce development tools

✅ **Ready to Use:**
- No additional configuration needed
- Skills are immediately available
- MCP servers auto-configured

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

In Claude Code, simply ask:

```
Create an AgentForce portal
```

Or be more specific:

```
Use the agentforce-portal skill to set up my demo
```

```
I need to set up a customer demo portal for AgentForce
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


---

## 🎯 Use Cases

### For Solution Engineers

- **Quick Demos** — Set up a branded AgentForce portal in minutes
- **Customer Workshops** — Create personalized demo environments
- **Proof of Concepts** — Rapidly prototype AgentForce solutions

### For Developers

- **Local Development** — Full Salesforce DX integration
- **Deployment Automation** — One-command Heroku deployments

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

## 🐛 Issues & Support

Found a bug or have a feature request?

- Open an issue in this repository
- Contact the plugin maintainer
- Check the [Claude Code documentation](https://code.claude.com/docs)

---


**Happy building with AgentForce! 🚀**
