---
name: agentforce-portal
description: Guide for setting up and deploying a customizable Next.js agentforce portal that integrates with Salesforce AgentForce. Helps Solution Engineers create personalized demo sites to showcase AI agents and custom solutions.
---

# AgentForce Portal Setup Guide

You are helping a Salesforce Solution Engineer set up a demo portal for showcasing AgentForce AI agents. This Next.js application allows them to:
- Display a customized landing page for their solution/workshop
- List and interact with their Salesforce AgentForce agents
- Create professional demos for customers

## Important Context

**Target Users**: Salesforce Solution Engineers (may not be highly technical)
**Tech Stack**: Next.js 15, TypeScript, React, Tailwind CSS, shadcn/ui
**Repository**: https://github.com/flemx/hr-agentforce-portal.git

## Key Documentation References

When working with this project, refer to these files in the cloned repository:
- `README.md` - Setup and deployment instructions
- `CLAUDE.md` - Development guidelines and architecture
- `AGENTFORCE_API_GUIDE.md` - Salesforce AgentForce API integration details

## Step-by-Step Setup Process

### Phase 1: Project Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/flemx/hr-agentforce-portal.git
   cd hr-agentforce-portal
   ```

2. **Check for Port Conflicts**
   - The app runs on port 8080
   - If something is already running on this port, offer to kill it
   - Command to check: `lsof -ti:8080 | xargs kill -9` (if needed)

3. **Install Dependencies**
   ```bash
   npm install
   ```

4. **Create Environment File**
   - Copy `.env.example` to `.env`
   - This will be populated with user-specific values in later steps

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
- Update the logo under: public/uploads
    - public/uploads/nto-primary-logo-01.png
    - public/uploads/nto-primary-logo-04.png
    - Keep it the same name ton update the logo's automatically, or updater the references in the code
- Keep the AgentForce integration intact
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

**Update .env:**
```
NEXT_PUBLIC_SALESFORCE_INSTANCE_URL=<their-domain-url>
```
- Make sure the domain includes https://

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

**After receiving credentials, update .env:**
```
SALESFORCE_CLIENT_ID=<their-client-id>
SALESFORCE_CLIENT_SECRET=<their-client-secret>
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

```
🔐 Step 6: Set Portal Password (Optional)

The portal is password-protected by default.

Default password: "your-secure-password-here"

To change it, update both of these in .env:
```

**Update .env if they want to change:**
```
NEXT_PUBLIC_AUTH_PASSWORD=<their-new-password>
AUTH_PASSWORD=<their-new-password>
```

Also update the JWT secret:
```
JWT_SECRET=<generate-random-string>
```

### Phase 4: Start Development Server

After all configuration is complete:

```bash
npm run dev
```

**Show the user a nice success message:**
```
🎉 Success! Your AgentForce Portal is running!

🌐 Open in browser: http://localhost:8080

📝 Login with password: <their-password>

From here you can:
✓ View your customized landing page
✓ See all connected agents
✓ Chat with your AI agents
✓ Demo your solution to customers

💡 If the site doesn't load:
- Check that no errors appeared in the terminal
- Ensure all environment variables are set correctly
- Try running: npm run dev

Need to make changes? Ask me and I can help modify:
- Landing page content and styling
- Agent display and interactions
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

## Troubleshooting Guide

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
