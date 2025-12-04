---
name: agentforce-portal
description: Guide for setting up and deploying a customizable Next.js agentforce portal that integrates with Salesforce AgentForce. Helps Solution Engineers create personalized demo sites to showcase AI agents and custom solutions.
---

# AgentForce Portal Setup Guide

You are helping a Salesforce Solution Engineer set up a demo portal for showcasing AgentForce AI agents. This Next.js application allows them to:
- Display a customized landing page for their solution/workshop
- List and interact with their Salesforce AgentForce agents
- Create professional demos for customers

## 🚀 Getting Started - What to Expect

**Before we begin, let the user know:**
```
Welcome! I'll help you set up your AgentForce Portal step-by-step.

📋 What we'll do together:
1. Install any missing tools (Node.js, Git) - 1-3 minutes
2. Set up the project files - 2-4 minutes
3. Customize your landing page - 5-10 minutes
4. Connect to your Salesforce org - 5-20 minutes
5. Launch your portal! - 2 minutes

⏱️ Total time: About 10-45 minutes

💡 Tips:
- I'll explain everything in simple terms
- You can ask me to slow down or clarify anything
- We'll verify each step before moving forward
- Don't worry if you're not technical - I've got you!

📱 What you'll need:
- Your Salesforce login credentials
- Admin access to your Salesforce org
- About 45 minutes of focused time

Ready to get started?

First, let me check if you have the required tools installed...
```

## Important Context

**Target Users**: Salesforce Solution Engineers (may not be highly technical)
**Tech Stack**: Next.js 15, TypeScript, React, Tailwind CSS, shadcn/ui
**Repository**: https://github.com/flemx/hr-agentforce-portal.git

## 🤖 Automation-First Approach

**IMPORTANT: You should do the work, not just instruct the user!**

This skill is designed to be hands-off for the user. Your role is to:

1. **Check and Install** - Automatically detect and install missing dependencies
2. **Clone and Setup** - Run all git and npm commands yourself
3. **Configure Files** - Use the Edit tool to update .env automatically
4. **Start Services** - Launch the dev server in the background
5. **Monitor Progress** - Check outputs and confirm success

**Only ask the user for:**
- Information you cannot obtain yourself (Salesforce credentials, domain, preferences)
- Permission before installing software or killing processes
- Decisions about customization and branding

**Never ask the user for:**
- Where to install the project (use current working directory)
- Whether to run commands (just run them)
- File paths or locations (figure them out automatically)

**Example Flow:**
```
❌ Bad: "Where would you like to install the project?"
✅ Good: "📁 Creating portal in current directory..." [uses pwd, then clones]

❌ Bad: "Please run: npm install"
✅ Good: "📦 Installing dependencies..." [runs npm install]

❌ Bad: "Update your .env file with this value"
✅ Good: "✅ Updated .env with your domain" [uses Edit tool]

❌ Bad: "You need to install Node.js from nodejs.org"
✅ Good: "📦 Installing Node.js via Homebrew..." [runs brew install]
```

**Be proactive, be helpful, do the work!**

## Key Documentation References

When working with this project, refer to these files in the cloned repository:
- `README.md` - Setup and deployment instructions
- `CLAUDE.md` - Development guidelines and architecture
- `AGENTFORCE_API_GUIDE.md` - Salesforce AgentForce API integration details

## Prerequisites Check

**BEFORE starting the setup, automatically check if the user has the required tools installed.**

### Automatic Prerequisites Check

**You should automatically check for and install missing dependencies:**

1. **Check for Node.js** (version 18 or higher)
   ```bash
   node --version
   ```
   - If the command fails or version is < 18, Node.js needs to be installed

2. **Check for Git**
   ```bash
   git --version
   ```
   - If the command fails, Git needs to be installed

3. **Detect Operating System**
   ```bash
   uname -s  # For Mac/Linux
   # Or check for Windows
   ```

### Installation Process (Do This Automatically)

**If prerequisites are missing, ask the user for permission to install them, then proceed:**

```
I need to check if you have the required tools installed.

Let me verify Node.js and Git...
```

#### For macOS Systems

**If on macOS, check for Homebrew first, then install what's needed:**

1. **Check for Homebrew:**
   ```bash
   which brew
   ```

2. **If Homebrew is NOT installed:**
   ```
   I notice Homebrew isn't installed. Homebrew is a package manager that will help us install Node.js and Git easily.

   Can I install Homebrew for you? This will take about 2-3 minutes.
   ```

   **If user agrees, install Homebrew:**
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

   Note: The installation may prompt for the user's password. Tell them:
   ```
   📝 Note: The installation will ask for your Mac password. This is normal and safe!
   Please enter your password when prompted.
   ```

3. **Install Node.js if missing:**
   ```bash
   brew install node
   ```

   Show progress:
   ```
   📦 Installing Node.js via Homebrew...
   This will take 1-2 minutes.
   ```

4. **Install Git if missing:**
   ```bash
   brew install git
   ```

   Show progress:
   ```
   📦 Installing Git via Homebrew...
   ```

5. **Verify installations:**
   ```bash
   node --version && npm --version && git --version
   ```

   Show success message:
   ```
   ✅ All tools installed successfully!
   - Node.js: v[version]
   - npm: v[version]
   - Git: v[version]

   Ready to proceed with the portal setup!
   ```

#### For Windows Systems

**For Windows users, you'll need to guide them to manual installation:**

```
I noticed you're on Windows. I need to install Node.js and Git for you.

Unfortunately, I can't automatically install these on Windows, but I can guide you:

For Node.js:
1. I'll open this link for you: https://nodejs.org/en/download
2. Download the "LTS" version for Windows (.msi)
3. Run the installer and use default settings
4. Once installed, come back here and let me know!

For Git:
1. I'll open this link for you: https://git-scm.com/download/win
2. Download and run the installer
3. Use default settings (just click Next through everything)
4. Once installed, let me know!

After you've installed both, I'll verify they're working and we can continue.
```

**After user confirms installation, verify:**
```bash
node --version && npm --version && git --version
```

#### For Linux Systems

**If on Linux, use the system package manager:**

```bash
# Detect Linux distribution
cat /etc/os-release
```

**For Ubuntu/Debian:**
```bash
sudo apt update
sudo apt install -y nodejs npm git
```

**For Fedora/RHEL:**
```bash
sudo dnf install -y nodejs npm git
```

**For Arch:**
```bash
sudo pacman -S nodejs npm git
```

Show progress:
```
📦 Installing Node.js and Git via your system package manager...
```

**Verify installations:**
```bash
node --version && npm --version && git --version
```

### After All Prerequisites are Ready

**Once all checks pass:**
```
✅ Perfect! All required tools are installed:
✓ Node.js v[version]
✓ npm v[version]
✓ Git v[version]

Now let's set up your AgentForce Portal!
```

## Step-by-Step Setup Process

### Phase 1: Project Setup

**Automatically handle the project setup - do everything for the user:**

1. **Use Current Working Directory**

   **DO NOT ask where to install. Use the current directory where Claude Code is open.**

   Check the current directory:
   ```bash
   pwd
   ```

   Inform the user:
   ```
   📁 I'll create your portal in the current directory:
   [show current path]
   ```

   If the current directory seems unusual or is in a system folder, you can suggest:
   ```
   Note: Your portal will be created here. This looks good!
   ```

2. **Clone the Repository Automatically**

   ```
   📥 Cloning the AgentForce Portal repository...
   ```

   ```bash
   git clone https://github.com/flemx/hr-agentforce-portal.git
   cd hr-agentforce-portal
   ```

   Confirm success:
   ```
   ✅ Repository cloned successfully!
   📂 Location: [show full path using pwd]
   ```

3. **Check for Port Conflicts Automatically**

   Check if port 8080 is in use:
   ```bash
   lsof -ti:8080
   ```

   If something is running:
   ```
   ⚠️ I found something already running on port 8080.

   Should I stop it so we can use that port for your portal?
   (I can restart it later if needed)
   ```

   If user agrees:
   ```bash
   lsof -ti:8080 | xargs kill -9
   ```

   ```
   ✅ Port 8080 is now available!
   ```

4. **Install Dependencies Automatically**

   ```
   📦 Installing project dependencies...
   This will take 1-2 minutes. Please wait...
   ```

   ```bash
   npm install
   ```

   Show success:
   ```
   ✅ Dependencies installed successfully!
   - Project is ready to customize
   ```

5. **Create Environment File Automatically**

   ```
   📝 Creating environment configuration file...
   ```

   ```bash
   cp .env.example .env
   ```

   Verify and show status:
   ```bash
   ls -la .env
   ```

   ```
   ✅ Environment file created!

   This file (.env) will store your Salesforce connection details.
   I'll help you fill it in during the next steps.
   ```

6. **Start Development Server Immediately**

   ```
   🚀 Starting your AgentForce Portal...

   You can start testing the portal right away while we customize it!
   ```

   ```bash
   npm run dev
   ```

   Note: Use the Bash tool with `run_in_background: true` so the server runs in the background and the user can continue to interact.

   Monitor the output to confirm the server started successfully. Look for messages like:
   - "Ready" or "started server on"
   - The local URL (should be http://localhost:8080)

   **Once server is running, show the user immediate access:**
   ```
   ✅ Portal is now running!

   🌐 Open in browser: http://localhost:8080
   🔐 Login password: your-secure-password-here

   The portal is live with default settings. You can explore it now while we personalize it together!
   ```

**After Phase 1 Completion:**
```
🎉 Project setup complete!

✓ Repository cloned
✓ Dependencies installed
✓ Environment file created
✓ Port 8080 available
✓ Development server running

🌐 Your portal: http://localhost:8080
🔐 Password: your-secure-password-here

Next, let's personalize your landing page!
```

### Phase 2: Personalization

**Ask the user to provide details for their landing page:**

Create a welcoming, conversational interaction:
```
I'll help you create a personalized landing page for your solution!

Please share:
1. What is the main purpose of this demo? (e.g., "HR Solution Workshop", "Customer Service AI Demo")
2. Would you like to:
   - Provide a summary/description I can use?
   - Upload any documents about the solution?
   - Have me generate content based on your description?
   - Showcase solution use cases on the landing page ?

3. Any specific branding elements? (colors, company info / website, etc.)
4. Share the inage URL of a logo we can use from the company you want to demo
5. Share any documentation such as PDF documents if you want to share this with the customner and include on the page

```

**After receiving their input:**
- Modify the landing page components (primarily in `src/app/page.tsx` or similar)
- Update text, descriptions, and any visual elements to match their use case
-  Make sure to update opn the main landing page the: Hero, change the Workshop Highlights with a new title and content based on requirememnts, update the Presentation of September 16, 2025 section if they want to offer a download, otherwise leave this section out
- Update the logo if this is shared:
    - search for references on:  nto-primary-logo-04.png and nto-primary-logo-01.png and update with the new logo url you found, from a public url or locally in the poroject dir
- Ensure to update the bradning and company names etc on all pages and remove the NTO / HR references: landing page (root: /), login page (/login), agent portal (/agents)
=- Keep the AgentForce integration intact
- Ensure the customization feels personal and professional

### Phase 3: Salesforce Integration

This is the most complex part - guide users carefully with visual formatting.

#### 3.1 Get Salesforce Org Domain

Ask the user:
```
📋 Step 1: Get Your Salesforce Org Domain

To connect to your Salesforce org, I need your domain URL.

How to find it:
1. Log into your Salesforce org
2. Click the ⚙️ gear icon → Setup
3. In the Quick Find box, type "My Domain"
4. Click on "My Domain"
5. Copy the URL shown under "Current My Domain URL"
   (It looks like: https://yourcompany.my.salesforce.com)

Please paste your domain URL here:
```

**After receiving the domain, automatically update .env:**

Ensure the domain includes https://, then use the Edit tool to update .env:
```bash
# Find the line and update it
# From: NEXT_PUBLIC_SALESFORCE_INSTANCE_URL=your-salesforce-instance-url
# To: NEXT_PUBLIC_SALESFORCE_INSTANCE_URL=https://theircompany.my.salesforce.com
```

Use the Edit tool to replace the value in the .env file.

Confirm to user:
```
✅ Updated Salesforce instance URL in .env
🔗 Domain: [their-domain-url]
```

#### 3.2 Create Connected App

This is multi-step - break it down clearly:
- Only follow these steps if they don't have the connected app details ready (client id / secret), ask for these first so we can update .env directly

```
📱 Step 2: Create a Salesforce Connected App

We need to create a Connected App to allow the portal to access your agents.

**Part A: Navigate to Your Agent**
1. Open your AgentForce agent in Agent Builder
2. Go to the "Connections" tab
3. Under "Connections", click "Add"
4. Select Connection Type: "API"
5. Click "New Connected App"

**Part B: Initial Configuration**
Before clicking "New Connected App", you'll see two checkboxes - enable both:
✓ "Allow access to External Client App consumer secrets via REST API"
✓ "Use connected apps to integrate third-party apps with Salesforce through APIs..."

Now click "New Connected App"

**Part C: Connected App Settings**
Fill in the form:

Basic Information:
- Connected App Name: "agentforce" (or your preferred name)
- API Name: (auto-filled)
- Contact Email: <your email>

API (Enable OAuth Settings):
✓ Check "Enable OAuth Settings"

Callback URL:
- Add: https://login.salesforce.com

Selected OAuth Scopes (add these 4):
- Access the Salesforce API Platform (sfap_api)
- Manage user data via APIs (api)
- Perform requests at any time (refresh_token, offline_access)
- Access chatbot services (chatbot_api)

Under "API (Enable OAuth Settings)" - ONLY check these 2:
✓ Enable Client Credentials Flow
✓ Issue JSON Web Token (JWT)-based access tokens for named users

⚠️ IMPORTANT: Deselect everything else under this section

Click "Save"

**Part D: Get Client Credentials**
After saving:
1. You'll see the Connected App details page
2. Click "Manage Consumer Details" button
3. Verify your identity (you may get a verification code via email)
4. Copy the "Consumer Key" (Client ID)
5. Copy the "Consumer Secret" (Client Secret)
6. ⚠️ Keep these secure - you'll need them in a moment

Please provide your Client ID and Client Secret:
```

**After receiving credentials, automatically update .env:**

Use the Edit tool to update both values in the .env file:
```bash
# Update Client ID
# From: SALESFORCE_CLIENT_ID=your-salesforce-client-id-here
# To: SALESFORCE_CLIENT_ID=[their-actual-client-id]

# Update Client Secret
# From: SALESFORCE_CLIENT_SECRET=your-salesforce-client-secret-here
# To: SALESFORCE_CLIENT_SECRET=[their-actual-client-secret]
```

Confirm to user:
```
✅ Updated Salesforce credentials in .env
🔑 Client ID: [first 10 chars]...
🔐 Client Secret: [first 5 chars]...
```

#### 3.3 Configure Connected App Policies

```
⚙️ Step 3: Configure Connected App Policies

Back on the Connected App detail page:

1. Click the "Manage" button
2. Click "Edit Policies"
3. Find "IP Relaxation" dropdown
4. Change to: "Relax IP restrictions"
5. Under "Client Credentials Flow" section
6. Add your own Admin user
7. Click "Save"

✅ Your Connected App is now configured!
```

#### 3.4 Connect App to Agents

```
🔌 Step 4: Connect Your Agents

For EACH agent you want accessible in the portal:

1. Open the agent in Agent Builder
2. Go to "Connections" tab
3. Click "Add"
4. Choose Connection Type: "API"
5. Click "Add" again
6. Enter any name (e.g., "Portal Connection")
7. In "Connected App" field, start typing the name of your Connected App
   (The one you created - e.g., "agentforce")
8. Select it from the dropdown
9. Click "Save"

✅ This agent is now accessible via the AgentForce API!

Repeat for all agents you want in the portal.

💡 Tip: If you have issues, check Setup → App Manager to find your Connected App config
```

#### 3.5 CORS Configuration

```
🌐 Step 5: Configure CORS

To allow the portal to make API calls:

1. In Setup, search for "CORS"
2. Click "CORS"
3. Click "New"
4. Add this URL: http://localhost:8080
5. Click "Save"

⚠️ Note: If you deploy this portal publicly (e.g., to Heroku),
you'll need to come back and add the deployed URL here too.
```

#### 3.6 Set Authentication Password (Optional)

Ask the user:
```
🔐 Step 6: Set Portal Password (Optional)

The portal is password-protected by default.

Default password: "your-secure-password-here"

Would you like to:
1. Keep the default password
2. Set a custom password

If you choose custom, what password would you like?
```

**If they want a custom password, automatically update .env:**

Use the Edit tool to update both password fields and generate a JWT secret:
```bash
# Generate a random JWT secret
# You can use: openssl rand -base64 32 or similar

# Update both password fields in .env
# NEXT_PUBLIC_AUTH_PASSWORD=[their-new-password]
# AUTH_PASSWORD=[their-new-password]
# JWT_SECRET=[generated-random-string]
```

Confirm to user and remind about server restart:
```
✅ Updated portal password in .env
🔒 New password: [their-password]
🔑 JWT secret: Generated and saved

Remember this password - you'll need it to log into the portal!

🔄 Restarting the development server to apply changes...
```

**Restart the dev server to apply the new password:**

Kill the existing server process and restart:
```bash
# Kill the existing dev server
lsof -ti:8080 | xargs kill -9

# Start the dev server again
npm run dev
```

Note: Use the Bash tool with `run_in_background: true` so the server runs in the background.

**Confirm the restart:**
```
✅ Server restarted with new password!

🌐 Portal: http://localhost:8080
🔐 New password: [their-password]
```

### Phase 4: Final Configuration Complete

**After all Salesforce configuration is complete, show the user a success message:**

```
🎉 Success! Your AgentForce Portal is fully configured!

🌐 Portal URL: http://localhost:8080
🔐 Login password: <their-password>

✅ What's configured:
✓ Customized landing page
✓ Salesforce org connected
✓ AgentForce agents linked
✓ CORS enabled
✓ Authentication secured

From here you can:
✓ View your customized landing page
✓ See all connected agents
✓ Chat with your AI agents
✓ Demo your solution to customers

💡 If the site doesn't load properly:
- Check that no errors appeared in the terminal
- Ensure all environment variables are set correctly in .env
- Verify your Salesforce Connected App settings
- Check CORS is configured for http://localhost:8080

Need to make changes? Ask me and I can help modify:
- Landing page content and styling
- Agent display and interactions
- Environment variables
- Any custom features you need

📚 For development guidance, see:
- README.md in the project root
- CLAUDE.md for architecture details
- AGENTFORCE_API_GUIDE.md for API integration
```

### Phase 5: Deployment (Optional)

If the user wants to deploy publicly:

```
🚀 Deploy to Heroku

Requirements:
- Heroku account (free tier works)
- Latest Heroku CLI installed

I can help deploy using the Heroku MCP integration:
1. Create a new Heroku app
2. Set environment variables
3. Deploy your portal
4. Get a public URL

Would you like me to proceed with deployment?

⚠️ Remember: After deployment, add the Heroku URL to your Salesforce CORS settings!
```

**If they agree:**
- Use the `mcp__heroku__create_app` tool to create a new Heroku app
- Use `mcp__heroku__deploy_to_heroku` tool to deploy
- Guide them to update CORS settings with the new URL

## Automation Summary

**You should automatically handle these tasks without user intervention:**

✅ **Prerequisites**
- Check for Node.js and Git
- Install via Homebrew (Mac) or system package manager (Linux)
- Guide Windows users to download and install

✅ **Project Setup**
- Use current working directory (no questions asked)
- Clone the repository
- Navigate to project directory
- Install npm dependencies
- Create .env file
- Check and free port 8080 if needed

✅ **Configuration**
- Update Salesforce instance URL in .env
- Update Client ID and Secret in .env
- Generate and set JWT secret
- Update password fields if custom password chosen

✅ **Start Server**
- Run npm run dev in background
- Monitor for successful start
- Provide user with access URL

**What requires user input:**
- Providing Salesforce org domain
- Creating Connected App in Salesforce (manual in SF UI)
- Providing Client ID and Secret
- Configuring Connected App policies (manual in SF UI)
- Connecting agents (manual in SF UI)
- Adding CORS entry (manual in SF UI)
- Choosing custom password (optional)
- Customization preferences for landing page

**Key principle: Automate everything you can, only ask for what you must.**

## Troubleshooting Guide

### Prerequisites Issues

**Issue 0: Command Not Found Errors**

If the user sees `command not found: node` or `command not found: git`:
```
❌ Command Not Found

This means Node.js or Git isn't installed (or Terminal needs to be restarted).

Steps to fix:
1. Close Terminal completely
2. Reopen Terminal
3. Try the command again: node --version

If it still doesn't work:
- Reinstall Node.js or Git following the Prerequisites section above
- Make sure you completed the installation fully
- Mac users: If you installed with Homebrew, run: brew doctor
```

**Homebrew Installation Issues:**
```
If Homebrew installation hangs or fails:
- Make sure you have a stable internet connection
- Try running the install command again
- You may need to enter your Mac password when prompted
- Check Xcode Command Line Tools are installed:
  xcode-select --install
```

**Node.js Version Issues:**
```
If node --version shows a version lower than 18:

Update Node.js:
# With Homebrew
brew upgrade node

# Or download latest from nodejs.org
```

### Common Issues

**Issue 1: Port 8080 Already in Use**
```bash
# Kill process on port 8080
lsof -ti:8080 | xargs kill -9
# Then restart
npm run dev
```

**Issue 2: Agents Not Showing Up**
- Verify Connected App is created correctly
- Check that agents have the Connected App connection added
- Ensure CORS is configured for localhost:8080
- Check Client ID and Secret in .env

**Issue 3: Authentication Issues**
- Verify both AUTH_PASSWORD values match in .env
- Check JWT_SECRET is set
- Try logging out and back in

**Issue 4: Salesforce API Errors**
- Verify instance URL is correct
- Check Connected App policies include your user
- Ensure IP Relaxation is set to "Relax IP restrictions"

**Issue 5: Development Server Won't Start**
```bash
# Clean install
rm -rf node_modules package-lock.json
npm install
npm run dev
```

## Making Customizations

### Updating Landing Page
- Main landing page: `src/app/page.tsx`
- Components: `src/components/`
- Styling: Tailwind CSS classes or `src/styles/`

### Modifying Agent Display
- Agent list component: Look for agent-related components in `src/components/`
- Agent chat interface: Likely in `src/components/AgentChat.tsx`

### Adding Features
- Refer to `AGENTFORCE_API_GUIDE.md` for API capabilities
- Use `CLAUDE.md` for architecture guidance
- Follow Next.js 15 App Router patterns

## Project Structure

```
hr-agentforce-portal/
├── src/
│   ├── app/              # Next.js app directory (routes)
│   ├── components/       # React components
│   │   ├── AgentChat.tsx         # Main chat interface
│   │   ├── ToolOutputCard.tsx    # Tool output display
│   │   └── ...
│   ├── utils/
│   │   ├── agentforceApi.ts      # Salesforce API integration
│   │   └── ...
│   └── middleware.ts     # Auth middleware
├── public/               # Static assets
├── .env                 # Environment configuration
├── .env.example         # Template
├── README.md            # Setup instructions
├── CLAUDE.md            # Development guide
└── AGENTFORCE_API_GUIDE.md  # API documentation
```

## Key Technologies

- **Next.js 15**: App Router for routing and SSR
- **TypeScript**: Type safety
- **React**: UI components
- **Tailwind CSS**: Styling
- **shadcn/ui**: Component library
- **TanStack Query**: Data fetching
- **JWT**: Authentication
- **Salesforce AgentForce API**: AI agent integration

## Important Guidelines

### User Experience
- **Be patient and clear**: Users may not be technical
- **Visual formatting**: Use emojis and clear section headers
- **Step-by-step**: Never rush through configuration
- **Verify success**: Always confirm each step worked before moving on
- **Provide examples**: Show what URLs/values should look like

### Security Reminders
- Never commit `.env` files
- Keep client secrets secure
- Use strong JWT secrets
- Update CORS only for trusted domains
- Change default password

### Best Practices
- Test locally before deploying
- Keep dependencies updated
- Follow Next.js and React patterns
- Use TypeScript for new code
- Maintain clean component structure

## When Things Go Wrong

If the user reports issues:
1. **Read error messages carefully** - they often tell you exactly what's wrong
2. **Check .env file** - most issues are misconfigured environment variables
3. **Verify Salesforce setup** - Connected App and CORS are common culprits
4. **Restart dev server** - `npm run dev` often fixes caching issues
5. **Check the terminal output** - Next.js provides detailed error logs

## Remember

- This tool is for **Solution Engineers creating demos**
- Make the process **as simple as possible**
- Provide **clear visual instructions**
- Always **test that things work** before moving to the next step
- Be **encouraging and supportive** - setup can be complex
- **Offer to help** with any customizations they need

The goal is to get them a working, personalized portal they can use to showcase their AgentForce solutions to customers!
