# 🐛 AI Bug Triage Agent
**with AutoGen Multi-Agent System**

🌐 **See the Live Application**: [https://ai-bug-triage-agent.vercel.app/](https://ai-bug-triage-agent.vercel.app/)

> **Automate bug triage with AI-powered agents. Get severity classification, reproduction steps, and fix suggestions—instantly and accurately.** ⚡

---

## ✨ Features

### 🎯 **Core Functionality**
- 🤖 **Multi-Agent Workflow** - Three specialized AI agents working together: Triage, Reproducer, and Fix Suggester
- 📋 **Severity Classification** - Automatic severity assessment (Critical, High, Medium, Low) with confidence scoring
- 🔍 **Smart Labeling** - AI-generated labels (frontend, backend, performance, security, etc.)
- 🔄 **Reproduction Steps** - Detailed, step-by-step instructions to reproduce bugs
- 💡 **Fix Suggestions** - Comprehensive fix strategies with patch outlines and risk assessments
- 🔗 **Linear/Jira Integration** - Connect to Linear and Jira APIs for ticket synchronization
- 📊 **Performance Metrics** - Track agent performance, success rates, and time-to-completion

### 🎨 **Beautiful UI/UX**
- ✨ **Modern 2025 Design** - Clean, intuitive interface with glassmorphism effects
- 🌙 **Dark Mode** - Full theme support with smooth transitions
- 📱 **Fully Responsive** - Optimized for desktop, tablet, and mobile devices
- ♿ **Accessible** - WCAG AA compliant with proper touch targets (44px minimum)
- 🎯 **Intuitive Interface** - User-friendly design with clear navigation

### 🎮 **Playground Features**
- 🧪 **Interactive Testing** - Test agent workflows before deploying to production
- 📝 **Template System** - Pre-filled templates for common bug scenarios
- 🔄 **Agent Replay** - Step-by-step replay of agent conversations with controls
- 💬 **AI Chat Assistant** - Context-aware AI helper for guidance and troubleshooting
- 💡 **Smart Suggestions** - AI-powered suggestions to improve bug reports
- 📊 **Real-Time Streaming** - Watch agents work in real-time with Server-Sent Events

### 📊 **Dashboard Features**
- 📈 **Performance Analytics** - Severity distribution, success rates, and agent comparison charts
- 🔴 **Live Agent Status** - Real-time view of active agents and their current jobs
- 📝 **Activity Feed** - Recent agent activities and workflow completions
- 🔍 **Job History** - Complete history of all agent runs with search and filtering
- 📋 **Share Results** - Generate shareable links for agent results

### 🚀 **Advanced Features**
- 🔄 **Real-Time Updates** - Server-Sent Events for live agent progress
- 💾 **Persistent History** - All results saved to Supabase database
- 🎚️ **Customizable** - Configurable agent models, max rounds, and workflow parameters
- 🔐 **Secure** - Environment-based configuration with proper secret management
- ⚡ **Fast** - Optimized with Redis caching for external API calls

---

## 🏗️ Tech Stack

### **Backend** 🐍
- **FastAPI** - Modern Python web framework with async support
- **AutoGen** - Microsoft's multi-agent conversation framework
- **OpenAI API** - GPT-4.1-mini for agent intelligence
- **Python 3.11+** - Latest features and performance

### **Frontend** ⚛️
- **Next.js 15.1** - React 19 with App Router
- **TypeScript** - Type-safe development
- **Tailwind CSS** - Utility-first styling
- **shadcn/ui** - Beautiful, accessible component library
- **Lucide Icons** - Modern icon set
- **Recharts** - Data visualization for metrics

### **Database & Cache** 💾
- **Supabase** - PostgreSQL with real-time capabilities (schema: `bugtriage`)
- **Upstash Redis** - Serverless job queue & caching (prefix: `bugtriage`)

### **External APIs** 🔌
- **Linear API** - Bug tracking and project management
- **Jira API** - Issue tracking and workflow management
- **OpenAI API** - AI model for agent intelligence

### **Deployment** 🚀
- **Railway** - Backend API service deployment
- **Vercel** - Frontend web application deployment

---


### 🏠 Homepage
*Beautiful landing page with clear value proposition and feature highlights*

### 🎮 Playground
*Interactive interface for testing agent workflows with real-time streaming*

### 📊 Dashboard
*Comprehensive dashboard with performance metrics, live agent status, and activity feed*

---

## 📖 User Guide

### 🎮 Using the Playground

1. **Enter Bug Report**
   - Type or paste your bug description in the text area
   - Use templates for common scenarios (UI bugs, API errors, performance issues)
   - Get AI-powered suggestions to improve your bug report

2. **Run Agent Workflow**
   - Click **"Run"** to start the multi-agent workflow
   - Watch real-time progress as agents collaborate
   - View streaming updates in the conversation view

3. **Review Results**
   - **Triage Results**: Severity, labels, key signals, suggested owner
   - **Reproduction Steps**: Detailed steps with environment assumptions
   - **Fix Suggestions**: Strategy, patch outline, files to modify, risks

4. **Replay Conversations**
   - Click **"Replay"** on any completed job
   - Step through the agent conversation with playback controls
   - Understand how agents collaborated to reach conclusions

### 📊 Using the Dashboard

1. **View Performance Metrics**
   - Overall success rate and total jobs processed
   - Severity distribution chart
   - Time-to-completion trends
   - Agent comparison metrics

2. **Monitor Live Agents**
   - Real-time status of Triage, Reproducer, and Fix Suggester agents
   - Current job being processed
   - Jobs processed count

3. **Review Activity Feed**
   - Recent agent activities
   - Workflow completions
   - Status updates

4. **Search History**
   - Filter jobs by status, severity, or date
   - Search by bug description
   - View detailed results for any job

### 💬 Using the Chat Assistant

1. **Open Chat**
   - Click the floating chat button (bottom-right)
   - Ask questions about the application or agent workflows

2. **Get Help**
   - "How do I run a new bug report?"
   - "What does 'high severity' mean?"
   - "How do I use the reproduction steps?"
   - "Explain the TriageAgent capabilities"

3. **Context-Aware Responses**
   - The assistant knows your current page
   - Provides relevant suggestions based on context

---

## 🎨 Customization

### Theme Options
- ☀️ **Light Mode** - Clean, bright interface
- 🌙 **Dark Mode** - Easy on the eyes
- 🖥️ **System** - Follows OS preference

### Agent Configuration
- **Model Selection**: Configure via `AUTOGEN_MODEL` env var (default: `gpt-4.1-mini`)
- **Max Rounds**: Control conversation depth via `AUTOGEN_MAX_TURNS` (default: 8)
- **Rate Limiting**: Configure per-project/IP limits

### Template Management
- Create custom templates for your team's common bug patterns
- Save templates locally for quick access
- Share templates with your team

---


## 📝 Notes & Limitations

### AutoGen Considerations

- **Cost**: Each agent run makes multiple OpenAI API calls. Monitor usage and set budget limits.
- **Latency**: Multi-agent workflows can take 10-30 seconds depending on model and complexity.
- **Model Selection**: Default is `gpt-4.1-mini` for cost efficiency. Change via `AUTOGEN_MODEL` env var.
- **Rate Limits**: Consider implementing rate limiting per project/IP to control costs.

### External APIs

- **Linear**: Requires API key. Mock data returned if not configured.
- **Jira**: Requires base URL, email, and API token. Mock data returned if not configured.
- **Caching**: External API responses are cached for 3 minutes to reduce API calls.

### Database

- **Schema**: All tables are in the `bugtriage` schema. Ensure this schema exists in Supabase.
- **Migrations**: Run `db/000-init.sql` to create initial schema and tables.

### Security

- **API Keys**: Never commit `.env` files. Use Railway/Vercel environment variables for production.
- **CORS**: Configured to allow requests from the web app origin only.
- **Secrets**: All secrets loaded from environment variables, never hard-coded.

---

## 👨‍💻 Creator

**Created by Derril Filemon**

---

## 🙏 Acknowledgments

- **Microsoft AutoGen** - For the multi-agent conversation framework
- **OpenAI** - For GPT-4.1-mini API
- **Supabase** - For database & real-time capabilities
- **Upstash** - For Redis caching
- **Railway** - For backend deployment
- **Vercel** - For frontend deployment
- **shadcn/ui** - For beautiful components
- **Recharts** - For data visualization

---

## 📞 Support

- 📧 **Email**: support@ai-bug-triage-agent.com
- 🐛 **Issues**: [GitHub Issues](https://github.com/derril-tech/ai-bug-triage-agent/issues)
- 💬 **Discussions**: [GitHub Discussions](https://github.com/derril-tech/ai-bug-triage-agent/discussions)

---

<div align="center">

Made with ❤️ and ☕ by [Derril Filemon](https://github.com/derril-tech)

</div>
