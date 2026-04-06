# OpenClaw + OpenCode + Free Models - Network Chuck

**频道**：Network Chuck | **视频链接**：https://youtu.be/kIWMLL0S8X8

---

## 这期在讲什么

Network Chuck 演示如何把 **OpenClaw + OpenCode** 结合起来，用 **Google Antighravity（免费模型 Gemini/Opus）** 驱动，同时用 **Agent Trust Hub** 做安全扫描，得到一套完全免费、开源、安全的 AI coding workflow。

---

## 核心架构

```
OpenClaw（大脑/总指挥）
    ↓ 路由任务
OpenCode（执行者/AI 编程 Agent）
    ↓
Google Antighravity（免费模型：Gemini 3、Opus 4.6）
```

**OpenClaw = 规划 + 编排**
**OpenCode = 执行 + 写代码**

---

## 安全问题：ClaWHub 有多危险

> **"There are 8,000 instances sitting exposed directly in the internet on default ports and nearly 50% of it are community-built skills that contain malicious instructions."**

| 风险 | 真实案例 |
|------|----------|
| 偷加密货币钱包 | Skills 表面正常，背后偷助记词 |
| 偷信用卡信息 | 伪装成正常工具，实际抓取卡号 |
| 偷身份证号 | 通过恶意代码渗出敏感数据 |

**核心问题**：Skill 看起来安全，代码里藏恶意指令。

---

## 解决方案：Agent Trust Hub

**Agent Trust Hub** = 自动检测 Skills 是否有威胁的工具

功能：
- 输入 ClaWHub Skill URL → 自动扫描
- 检测：下载外部脚本、执行安装命令、写敏感文件等高危行为
- 输出风险等级报告（Low / Medium / High / Critical）

**使用方式**：
1. 复制 Skill URL
2. 粘贴到 Agent Trust Hub
3. 查看风险报告
4. 确认安全后再安装

> Network Chuck 实测：**找到一个恶意 Skill**，会从外部网站下载安装脚本——如果没有 Trust Hub 扫描，直接中招。

---

## 免费模型方案：Google Antighravity

**Google Antighravity 是什么**

Google 官方插件，让 OpenClaw 和 OpenCode 都能用：
- **Gemini 3**（最新最强）
- **Opus 4.6**
- 完全免费（有 Google 账号就行）

**启用方式**：
```bash
openclaw plugins enable google-antighravity-o
```

**为什么不用 API Key**：
- 不花钱
- 不绑定特定 provider
- 可以随时切换模型

> ⚠️ **不要把 Claude Code Max 账号接到 OpenClaw** — Anthropic 已经开始封禁这种用法。

---

## 实操步骤

### 1. 安装 OpenClaw
```bash
# 需要 Node.js 22+
npm install -g openclaw
```

### 2. 启用 Google Antighravity（免费模型）
```bash
openclaw plugins enable google-antighravity-o
# 然后用 Google 账号登录授权
```

### 3. OpenClaw 引导配置
```bash
openclaw onboarding install daemon
```
会提示你选择：
- Provider（选 Google Antighravity）
- Message Router（Telegram/Discord 等）
- 安全设置

### 4. 安装 OpenCode（独立 AI 编程 Agent）
```bash
# OpenCode 是开源的 AI coding agent
npm install -g opencode
```

### 5. 给 OpenClaw 安装 OpenCode Controller Skill
```bash
openclaw skills add <skill-url-from-clawhub>
```

**安全前置：**
1. 去 Agent Trust Hub 扫描 Skill URL
2. 确认为 Low Risk 后再安装

安装完成后，OpenClaw 的 Skills 列表里会出现 `open-code-controller`。

### 6. 设置完成，开始协作

```
你 → OpenClaw（说需求）
    ↓
OpenClaw（规划 + 路由）
    ↓
OpenCode（执行代码任务）
    ↓
Google Antighravity（提供智能）
```

---

## Demo：自动搭建 CRM Dashboard

**输入**：在 OpenClaw 里说"帮我创建一个 CRM Dashboard，用 Node.js/React"

**OpenClaw 做了什么**：
1. 拆解任务
2. 派发 OpenCode sub-agent
3. OpenCode 自动：创建项目 → 安装依赖 → 写代码 → 启动 Dev Server

**结果**：一个完整的 CRM Dashboard，包含预设的颜色方案和功能，直接可用。

---

## 能做什么

| 任务类型 | OpenClaw 做的 | OpenCode 执行的 |
|----------|---------------|----------------|
| 搭建项目脚手架 | 解析需求、派发任务 | 创建文件、安装依赖 |
| Bug 修复 | 检测问题、调度调试 Agent | 分析代码、写入修复 |
| API 检查 | 监控异常、触发任务 | 运行测试、写报告 |
| 自动化 Cron | 定时触发 | 执行重复性编码任务 |

---

## 金句

> **"OpenClaw is the brain. OpenCode is the execution layer that handles the coding."**

> **"Execution has become commoditized. System design is the new bottleneck."**

---

## 一句话总结

> **OpenClaw（大脑）+ OpenCode（执行）+ Google Antighravity（免费智能）+ Agent Trust Hub（安全扫描）= 完全免费、开源、安全的 AI coding workflow，不需要任何 API Key。**

---

*总结时间：2026-04-07*
