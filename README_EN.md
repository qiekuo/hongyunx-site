# HongyunX Agent Website

**English** | [中文](README.md)

Official website and documentation site source repository for HongyunX Agent.

---

## About HongyunX Agent

> **Build with AI. Deliver at enterprise scale.**

HongyunX Agent is an enterprise-grade, AI Agent-driven next-generation intelligent collaboration platform. It integrates the Agent engineering of Claude Code, cloud parallelism of Codex, immersive IDE experience of Cursor, localization of Trae, and repository-level cognition of Qoder into a unified tool. Available in **CLI + Desktop Client + Web/API** forms, supporting public cloud, private, and hybrid deployment models.

### Dual-Mode Architecture

HongyunX Agent supports two working modes that users can switch freely:

| Mode | Positioning | Use Cases | Core Capabilities |
|------|-------------|-----------|-------------------|
| **General Assistant** | Universal AI Assistant | Daily conversations, Q&A, data analysis, document writing, life assistant | NLU, knowledge reasoning, data queries, content generation |
| **Coding Assistant** | Professional Coding Assistant | Code writing, debugging, refactoring, code review, project management | Code understanding, tool invocation, sandbox execution, version control |

```bash
# Mode switching
hyx [normal]> /mode general    # Switch to General Assistant mode
hyx [normal]> /mode coding     # Switch to Coding Assistant mode
hyx [normal]> /mode auto       # Auto-detect mode (default)
```

---

## Feature Highlights

### 🛠️ Work & Programming

| Feature | Description |
|---------|-------------|
| **CLI/GUI Dual-Form Same-Core** | Same Rust Core Engine — CLI for developers, GUI for team management |
| **Multi-Model Routing** | Support for Anthropic Claude, OpenAI GPT, Alibaba DashScope, with automatic fallback |
| **Native MCP Protocol** | Model Context Protocol client for seamless external tool integration |
| **Sandbox Execution** | L0-L3 four-level security isolation for safe code execution |
| **Worktree Isolation** | Git Worktree-level parallel task isolation to avoid conflicts |
| **Sub-Agent Parallelism** | Sub-agents execute in parallel, automatic decomposition of complex tasks |
| **Repo Wiki Cognition** | Full repository indexing and semantic understanding, cross-file correlation |
| **Quest Long-Task Mode** | Background autonomous execution of long-cycle tasks with checkpoint resume |
| **Tab Inline Completion** | IDE-level code completion experience |
| **Composer/Builder Mode** | Visual orchestration of multi-step workflows |

### 🌐 Life & General

| Feature | Description |
|---------|-------------|
| **Knowledge Q&A** | Answer various knowledge questions with explanations and suggestions |
| **Data Analysis** | Query real-time data (metal prices, stocks, industry data, etc.) |
| **Document Writing** | Write articles, reports, emails, translation and polishing |
| **Scheduled Tasks (Cron)** | Built-in scheduling engine for timed AI tasks or scripts |
| **WeChat Adapter** | Send messages via WeChat, connecting to China's IM ecosystem |
| **Creative Generation** | Brainstorming, creative writing, content planning |
| **Life Assistant** | Schedule management, reminders, suggestions, and daily assistance |

### 🏢 Enterprise Capabilities

| Feature | Description |
|---------|-------------|
| **SSO / RBAC** | Single Sign-On and Role-Based Access Control as first-class citizens from Day 1 |
| **Audit Logs** | Complete operation audit trail for compliance requirements |
| **Quota Management** | Token usage limits and cost control |
| **Private Deployment** | Support for on-premises, private cloud, and hybrid deployment — code stays within enterprise boundaries |
| **Xinchuang Ecosystem** | Complete localization path, supporting domestic OS and databases |
| **A2A Collaboration** | Agent-to-Agent protocol for multi-agent collaborative work |

### 🔌 Extensibility

| Feature | Description |
|---------|-------------|
| **Skills Packages** | Pluggable capability packages, community sharing and customization |
| **Hooks System** | Lifecycle hooks for custom trigger logic |
| **Extension Marketplace** | Third-party extension installation and management, supporting GitHub/Git/local sources |
| **Open Plugin Architecture** | Skill / MCP / Hook three-layer plugin system with open protocols |

---

## Interaction Forms

### CLI (`hyx`)

The command-line interface is the core interaction method of HongyunX Agent, providing a complete TUI experience.

```bash
# Start TUI interactive mode
cd /your/project
hyx

# Single conversation mode
hyx chat "Read the README and suggest an improvement"

# Pipe input
cat README.md | hyx chat "Summarize this file"

# Specify model
hyx chat --model claude-sonnet-4-6 "Write a sorting algorithm"
```

**TUI Interface Layout:**

```
┌─ ⚡ HongyunX Agent CLI ───────────────────────────────────────────────────────┐
│ Sessions │ Tools │ MCP │ Keys                                          │
├──────────┼─────────────────────────────────────────────────────────────┤
│ Session  │  ⚡ HongyunX Agent CLI                                             │
│ List     │                                                             │
│          │  Work Mode: BUILD — Default execution mode                  │
│          │                                                             │
│          │  You  Please help me refactor this code                     │
│          │                                                             │
│          │  AI   Sure, let me take a look at this code...              │
├──────────┤─────────────────────────────────────────────────────────────┤
│ > _                                              │ Enter Send          │
├──────────────────────────────────────────────────┴─────────────────────┤
│ BUILD  [s] Settings [t] Theme [B] Sidebar [Tab] Panels [q] Quit       │
└────────────────────────────────────────────────────────────────────────┘
```

**Four Working Modes:**

| Mode | Color | Description | Permissions |
|------|-------|-------------|-------------|
| **BUILD** | 🟠 Orange | Default execution mode | Full read/write/execute permissions |
| **PLAN** | 🟢 Green | Read-only planning mode | Read and plan file edits only |
| **COMPOSE** | 🟣 Purple | Orchestration mode | Access to compose-skills (TDD, debugging) |
| **MAX** | 🔴 Pink | Experimental mode | Parallel inference (requires configuration) |

**Common Shortcuts:**

| Shortcut | Function |
|----------|----------|
| `Ctrl+C` | Exit application |
| `Ctrl+P` | Open command palette |
| `Ctrl+B` | Toggle sidebar |
| `Ctrl+X` | Switch work mode |
| `Ctrl+N` | New session |
| `Enter` | Send message |
| `Shift+Enter` | New line |

### GUI (Desktop Client)

Cross-platform desktop client built with Tauri, providing visual configuration and immersive experience.

- **Visual Configuration**: Graphical settings interface, no manual JSON editing required
- **Session Management**: Intuitive session list and history
- **Tool Status**: Real-time display of tool and MCP server connection status
- **Theme Switching**: Support for light/dark themes
- **System Tray**: Background resident operation, quick wake-up

### Web/API

RESTful API and WebSocket interfaces for integration with existing systems.

```bash
# Start API service
hyx serve

# API endpoint examples
POST /api/chat          # Chat interface
GET  /api/sessions      # Session list
POST /api/cron          # Create scheduled task
```

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| **Core Engine** | Rust (workspace architecture) |
| **CLI** | Rust + Ratatui (TUI) |
| **Desktop** | Tauri + React/Vue |
| **Frontend** | Modern Web (TypeScript) |
| **Protocol** | MCP (Model Context Protocol) |
| **Deployment** | GitHub Pages / Docker / Private |

---

## Competitive Comparison

| Capability | Claude Code | Codex | Cursor | Trae | Qoder | **HongyunX Agent** |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| Agent Kernel | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Sub-Agent Parallel | ✅ | 🟡 | 🟡 | ❌ | 🟡 | ✅ |
| Cloud Task Parallel | 🟡 | ✅ | ✅ | ❌ | 🟡 | ✅ |
| Native MCP Protocol | ✅ | 🟡 | ✅ | 🟡 | 🟡 | ✅ |
| Skills Packages | ✅ | ❌ | 🟡 | ❌ | ❌ | ✅ |
| Hooks System | ✅ | ❌ | ❌ | ❌ | ❌ | ✅ |
| Cross-Session Memory | ✅ | 🟡 | 🟡 | 🟡 | ✅ | ✅ |
| Repo Wiki Cognition | 🟡 | ❌ | 🟡 | ❌ | ✅ | ✅ |
| Quest Long-Task Mode | 🟡 | ✅ | 🟡 | ❌ | ✅ | ✅ |
| Tab Inline Completion | ❌ | ❌ | ✅ | ✅ | 🟡 | ✅ |
| Composer/Builder Mode | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ |
| Multi-Model Routing | 🟡 | ❌ | ✅ | ✅ | ✅ | ✅ |
| Sandbox Execution | ✅ | ✅ | 🟡 | 🟡 | 🟡 | ✅ |
| Worktree Isolation | ✅ | 🟡 | ❌ | ❌ | ❌ | ✅ |
| A2A Collaboration | 🟡 | ❌ | ❌ | ❌ | ❌ | ✅ |
| Private Deployment | 🟡 | ❌ | ❌ | ✅ | ✅ | ✅ |
| Domestic Model Support | ❌ | ❌ | 🟡 | ✅ | ✅ | ✅ |
| SSO/RBAC/Audit | ❌ | ❌ | 🟡 | 🟡 | 🟡 | ✅ |
| Desktop GUI Config | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ |

> ✅ = Native support | 🟡 = Partial support | ❌ = Not supported

**HongyunX Agent Differentiators:**

1. **「All-in-One」**: All 19 capability dimensions ✅ — unique in the industry
2. **「Enterprise-First」**: SSO/RBAC/Audit/Quota as first-class citizens from Day 1
3. **「Sovereign-Ready」**: Complete localization path (Xinchuang ecosystem, domestic models, offline deployment)
4. **「CLI ⇄ GUI Dual-Form Same-Core」**: Same kernel — CLI for developers, GUI for team management
5. **「Open Plugin Architecture」**: Skill / MCP / Hook three-layer plugin system with open protocols

---

## Repository Structure

```
hongyunx-site/
├── README.md          # Chinese documentation
├── README_EN.md       # English documentation (this file)
├── docs/              # Documentation assets
├── assets/            # Static assets (logos, images, etc.)
└── _config.yml        # Site configuration
```

---

## Quick Start

### Installation

```bash
# 1. Install Rust toolchain
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
# Windows: winget install Rustlang.Rustup

# 2. Clone the project
git clone https://github.com/hongyunx/hongyunx.git
cd hongyunx

# 3. Build
cargo build --release

# 4. Configure API Key (choose one)
export ANTHROPIC_API_KEY=sk-ant-...    # Claude
export OPENAI_API_KEY=sk-...           # GPT
export DASHSCOPE_API_KEY=sk-...        # Qwen

# 5. Initialize workspace
cd /your/project
hyx init

# 6. Start chatting
hyx chat "Read the README and suggest an improvement"
```

### First Run

```bash
# Navigate to your project directory
cd /path/to/your/project

# Start TUI interactive mode
hyx

# Or ask directly (single mode)
hyx chat "Help me analyze this project structure"

# View help
hyx --help
```

---

## Related Links

- **Main Project Repository**: [HongyunX Agent](https://github.com/qiekuo/hongyunx)
- **User Guide**: [HongyunX Agent Documentation](https://qiekuo.github.io/hongyunx-site/#/docs)

---

## License

Apache-2.0
