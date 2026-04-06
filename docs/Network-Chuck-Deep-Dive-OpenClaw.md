# Network Chuck 深度体验 OpenClaw

**频道**：Network Chuck | **视频链接**：https://youtu.be/T-HZHO_PQPY

---

## 这期在讲什么

Network Chuck 深度上手 OpenClaw，从安装到配置到安全到实际使用场景，给出了他的真实评价。

---

## OpenClaw 是什么

**一个 AI Gateway（网关）**，运行在你自己机器上的 Node.js 服务，连接三样东西：

1. **AI 模型** — 不绑定 provider，支持 OpenAI、Anthropic、本地模型（Ollama）
2. **Channels（渠道）** — Telegram、Discord、Slack 等，AI 主动找你用的平台
3. **Memory（记忆）** — 长期记忆、短期记忆、日记式记录

**第四个核心能力：Tools（工具）** — 你给 AI 什么工具，它就能在那个机器上操作

---

## 实操要点（5分钟快速上手）

**1. 安装到云服务器（Hostinger VPS）**
```
hostinger.com/ncopenclaw → VPS → KVM2 → coupon code network chuck
```

**2. 一行命令安装 OpenClaw**
```bash
curl https://openclaw.ai/install.sh | sh
```

**3. 配置 AI 模型** — 选 OpenAI（用已有 ChatGPT Pro 订阅更划算）

**4. 配置 Channel** — Telegram Bot（@BotFather 创建）

**5. 启动 TUI 或 Web UI**

---

## 能做什么（Demo 场景）

| 场景 | OpenClaw 做的事 |
|------|----------------|
| 新闻简报 | 自动抓 YouTube、Reddit、Hacker News，按你的兴趣筛选并评分 |
| IT 工程师 | 自动监控服务器 CPU/RAM/安全日志，生成 Dashboard |
| 个人助理 | 检查邮件、用日语打电话预约餐厅 |
| 创建 Word 简历 | 直接生成 docx 文件 |
| 定时任务 | 每 30 分钟提醒喝水，每天早 8 点新闻推送 |

**底层就是 cron 定时任务 + 心跳机制**，不是魔法，就是 scheduled task。

---

## Memory 是怎么工作的

```
~/openclaw/workspace/
├── soul.md        # 核心人格定义
├── identity.md    # 身份信息（你填的）
├── memory.md      # 长期记忆
└── memory/        # 日记式文件夹（按天记录）
```

告诉它"Gengar 是我的 favorite Pokemon"→ 它会自动更新 soul + identity + memory + 当天日记。**不是黑箱，你可以直接看到文件。**

---

## 安全配置

**必须做：**
```bash
openclaw security audit        # 检查安全配置
openclaw security audit --fix  # 自动修复
```

**三个关键配置：**
- `tools.profile` — full（全功能）/ coding（限制）
- `tools.exec` — full / allow-list / ask
- `red lines` — 在 agents.md 里定义 AI 的红线

**Red Lines 示例：**
- 红线（禁止）：不询问就删数据、不经确认执行破坏性命令
- 黄线（记录但不阻止）：改防火墙规则、运行 docker

**12% 的 ClaWHub skills 被发现含恶意软件，务必 VirusTotal 验证！**

---

## Network Chuck 怎么用 OpenClaw

1. **IT 部门** — 1 个 CTO + 多个专业 Agent（网络/存储/系统工程师），Slack 沟通，有 ticketing 系统
2. **个人助理 Hermione** — 查邮件、用日语打电话预约
3. **健身教练 Arnold** — 辅助减脂计划

**他不用来做严肃编程工作** — 那是 Claude Code 的活。

---

## 真实评价

> **"Is it groundbreaking? No. A lot of this has been done before. But it packaged everything together and made it accessible."**

- 不是技术突破，是**产品化突破**
- Jensen Huang 称它为"个人 AI 的操作系统"
- 大公司（Nvidia、Anthropic）都在做自己的版本
- **隐患**：OpenClaw 早期安全性很差，技能市场 malware 问题严重

**结论：**
- 好玩，值得探索
- 不要忽略安全配置
- 对比 Claude Code：OpenClaw 偏向"助理/自动化"，Claude Code 偏向"编程研究/脚本"
- 两者可以配合用

---

## 一句话总结

> **OpenClaw = 你给 AI 一台电脑 + 一套工具 + 一个平台，让它成为真正的数字员工，而不只是聊天机器人。**

---

*总结时间：2026-04-07*
