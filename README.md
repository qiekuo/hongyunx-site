# HongyunX Agent 官网

[English](README_EN.md) | **中文**

HongyunX Agent 官方网站与文档站点源码仓库。

---

## 关于 HongyunX Agent

> **企业级 AI 编程协作平台，让智能协作贯穿完整交付链路。**

HongyunX Agent 是一个面向企业的、由 AI Agent 驱动的下一代智能协作平台。它将 Claude Code 的 Agent 工程化、Codex 的云端并行、Cursor 的沉浸式 IDE 体验、Trae 的国内化适配、Qoder 的仓库级认知能力融为一体，通过 **CLI + 桌面客户端 + Web/API** 三种形态，支持公有云、私有化、混合云三种部署模式。

### 双模式架构

HongyunX Agent 支持两种工作模式，用户可根据需求自由切换：

| 模式 | 定位 | 适用场景 | 核心能力 |
|------|------|----------|----------|
| **全能助手模式** | 通用 AI 助手 | 日常对话、知识问答、数据分析、文档撰写、生活助手 | 自然语言理解、知识推理、数据查询、内容生成 |
| **编码助手模式** | 专业编程助手 | 代码编写、调试、重构、代码审查、项目管理 | 代码理解、工具调用、沙箱执行、版本控制 |

```bash
# 模式切换
hyx [normal]> /mode general    # 切换到全能助手模式
hyx [normal]> /mode coding     # 切换到编码助手模式
hyx [normal]> /mode auto       # 自动识别模式（默认）
```

---

## 功能亮点

### 🛠️ 工作与编程

| 功能 | 说明 |
|------|------|
| **CLI/GUI 双形态同源** | 同一 Rust Core Engine，CLI 程序员爽，GUI 团队管理爽 |
| **多模型路由** | 支持 Anthropic Claude、OpenAI GPT、阿里 DashScope 等多家模型，自动降级 |
| **MCP 协议原生支持** | Model Context Protocol 客户端，无缝接入外部工具和服务 |
| **沙箱执行 (Sandbox)** | L0-L3 四级安全隔离，代码执行安全可控 |
| **Worktree 隔离** | Git Worktree 级别的并行任务隔离，避免冲突 |
| **Sub-Agent 并行** | 子代理并行执行，复杂任务自动拆解 |
| **Repo Wiki 仓库认知** | 全仓库索引与语义理解，跨文件关联分析 |
| **Quest 长任务模式** | 后台自主执行长周期任务，支持断点续传 |
| **Tab 内联补全** | IDE 级别的代码补全体验 |
| **Composer/Builder 模式** | 可视化编排多步骤工作流 |

### 🌐 生活与通用

| 功能 | 说明 |
|------|------|
| **知识问答** | 回答各类知识问题，提供解释和建议 |
| **数据分析** | 查询实时数据（金属价格、股票、行业数据等） |
| **文档撰写** | 撰写文章、报告、邮件、翻译润色 |
| **计划任务 (Cron)** | 内置调度引擎，支持定时执行 AI 任务或脚本 |
| **微信适配器** | 通过微信发送消息，打通国内即时通讯生态 |
| **创意生成** | 头脑风暴、创意写作、内容策划 |
| **生活助手** | 日程管理、提醒、建议等日常辅助 |

### 🏢 企业级能力

| 功能 | 说明 |
|------|------|
| **SSO / RBAC** | 单点登录与角色权限控制，从 Day 1 即为一等公民 |
| **审计日志** | 完整的操作审计追踪，满足合规要求 |
| **配额管控** | Token 用量限制与成本管控 |
| **私有化部署** | 支持本地、私有云、混合云部署，代码不出企业边界 |
| **信创生态** | 完整国产化路径，支持国产操作系统与数据库 |
| **A2A 协作** | Agent-to-Agent 协议，多智能体协同工作 |

### 🔌 扩展能力

| 功能 | 说明 |
|------|------|
| **Skills 技能包** | 可插拔的能力包，社区共享与自定义 |
| **Hooks 钩子系统** | 生命周期钩子，自定义触发逻辑 |
| **扩展市场** | 第三方扩展安装与管理，支持 GitHub/Git/本地源 |
| **Open Plugin Architecture** | Skill / MCP / Hook 三层插件体系全部开放协议 |

---

## 交互形态

### CLI (`hyx`)

命令行界面是 HongyunX Agent 的核心交互方式，提供完整的 TUI 体验。

```bash
# 启动 TUI 交互模式
cd /your/project
hyx

# 单次对话模式
hyx chat "请阅读 README 并提议一个改进点"

# 管道输入
cat README.md | hyx chat "请总结这个文件的内容"

# 指定模型
hyx chat --model claude-sonnet-4-6 "写一个排序算法"
```

**TUI 界面布局：**

```
┌─ ⚡ HongyunX Agent CLI ───────────────────────────────────────────────────────┐
│ Sessions │ Tools │ MCP │ Keys                                          │
├──────────┼─────────────────────────────────────────────────────────────┤
│ 会话列表 │  ⚡ HongyunX Agent CLI                                             │
│          │                                                             │
│          │  Work Mode: BUILD — Default execution mode                  │
│          │                                                             │
│          │  You  请帮我重构这段代码                                      │
│          │                                                             │
│          │  AI   好的，我来看看这段代码...                               │
├──────────┤─────────────────────────────────────────────────────────────┤
│ > _                                              │ Enter Send          │
├──────────────────────────────────────────────────┴─────────────────────┤
│ BUILD  [s] Settings [t] Theme [B] Sidebar [Tab] Panels [q] Quit       │
└────────────────────────────────────────────────────────────────────────┘
```

**四种工作模式：**

| 模式 | 颜色 | 说明 | 权限 |
|------|------|------|------|
| **BUILD** | 🟠 橙色 | 默认执行模式 | 完整读写执行权限 |
| **PLAN** | 🟢 绿色 | 只读规划模式 | 仅允许读取和计划文件编辑 |
| **COMPOSE** | 🟣 紫色 | 编排模式 | 可访问 compose-skills（TDD、调试） |
| **MAX** | 🔴 粉色 | 实验模式 | 并行推理（需配置启用） |

**常用快捷键：**

| 快捷键 | 功能 |
|--------|------|
| `Ctrl+C` | 退出应用 |
| `Ctrl+P` | 打开命令面板 |
| `Ctrl+B` | 切换侧边栏 |
| `Ctrl+X` | 切换工作模式 |
| `Ctrl+N` | 新建会话 |
| `Enter` | 发送消息 |
| `Shift+Enter` | 换行 |

### GUI (桌面客户端)

基于 Tauri 构建的跨平台桌面客户端，提供可视化配置与沉浸式体验。

- **可视化配置**：图形化设置界面，无需手动编辑 JSON
- **会话管理**：直观的会话列表与历史记录
- **工具状态**：实时显示工具与 MCP 服务器连接状态
- **主题切换**：支持亮色/暗色主题
- **系统托盘**：后台常驻运行，快捷唤醒

### Web/API

RESTful API 与 WebSocket 接口，支持集成到现有系统。

```bash
# 启动 API 服务
hyx serve

# API 端点示例
POST /api/chat          # 对话接口
GET  /api/sessions      # 会话列表
POST /api/cron          # 创建计划任务
```

---

## 技术栈

| 层级 | 技术选型 |
|------|----------|
| **Core Engine** | Rust (workspace 架构) |
| **CLI** | Rust + Ratatui (TUI) |
| **桌面端** | Tauri + React/Vue |
| **前端** | Modern Web (TypeScript) |
| **协议** | MCP (Model Context Protocol) |
| **部署** | GitHub Pages / Docker / 私有化 |

---

## 本仓库结构

```
hongyunx-site/
├── README.md          # 中文说明（本文件）
├── README_EN.md       # English documentation
├── docs/              # 文档资源
├── assets/            # 静态资源（logo、图片等）
└── _config.yml        # 站点配置
```

---

## 快速开始

### 安装

```bash
# 1. 安装 Rust 工具链
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
# Windows: winget install Rustlang.Rustup

# 2. 克隆项目
git clone https://github.com/hongyunx/hongyunx.git
cd hongyunx

# 3. 构建
cargo build --release

# 4. 配置 API Key（选择一个）
export ANTHROPIC_API_KEY=sk-ant-...    # Claude
export OPENAI_API_KEY=sk-...           # GPT
export DASHSCOPE_API_KEY=sk-...        # Qwen

# 5. 初始化工作区
cd /your/project
hyx init

# 6. 开始对话
hyx chat "请阅读 README 并提议一个改进点"
```

### 首次运行

```bash
# 进入项目目录
cd /path/to/your/project

# 启动 TUI 交互模式
hyx

# 或者直接提问（单次模式）
hyx chat "请帮我分析这个项目结构"

# 查看帮助
hyx --help
```

---

## 相关链接

- **主项目仓库**：[HongyunX Agent](https://github.com/qiekuo/hongyunx)
- **用户指南**：[HongyunX Agent 文档站](https://qiekuo.github.io/hongyunx-site/#/docs)

---

## 许可证

Apache-2.0
