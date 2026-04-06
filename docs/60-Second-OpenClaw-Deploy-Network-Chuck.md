# 60 Second OpenClaw Deploy - Network Chuck

**频道**：Network Chuck | **视频链接**：https://youtu.be/XmSxfFrkcDs

---

## 这期在讲什么

Network Chuck 演示如何在 **60 秒内**把 OpenClaw 部署到 Telegram 上，不需要 Mac Mini，不需要 VPS，纯免费。他推荐用 **Kiloclaw**（OpenClaw 官方托管版）来实现这个速度。

---

## 核心亮点

### Kiloclaw 是什么

**Kiloclaw = OpenClaw 的完全托管托管版本**，由 OpenClaw 官方提供：
- 不需要自己配置服务器
- 不用折腾安全更新和监控
- 500+ 模型可选
- 定价透明：按模型提供商的成本来，不加价
- 集中管理所有模型的用量

> ⚠️ **不要把 Claude Code Max 账号接到 OpenClaw** — Anthropic 已经开始封禁这种用法，违反服务条款。

---

## 实操步骤（60 秒完成）

**第一步：创建 Telegram Bot**
1. 在 Telegram 搜索 **BotFather**（带蓝色认证的才是真的）
2. 发送 `/newbot`
3. 给 Bot 起名 → 设置用户名
4. 复制 BotFather 给的 **Token**

**第二步：在 Kiloclaw 创建实例**
1. 选择使用的模型（推荐用已有的 ChatGPT Pro 订阅，更划算）
2. 选择 Channel → Telegram
3. 粘贴 Bot Token
4. 点击创建

**第三步：配对**
1. 进入 Settings → Pairing Requests
2. 批准pending的配对请求
3. 完成 ✅

---

## 他的三个真实用法

### 用法 1：每日简报（早间惯例）

**场景**：以前每天早上在手机上刷 5-6 个 App（收入数据、客服邮箱、社交媒体），容易陷入 doom scrolling。

**解决**：OpenClaw 每天早上自动在 Telegram 推送：
- App 收入数据
- 客服工单摘要
- 关注的社交媒体动态

> "现在起床只看一条消息，几分钟就 catch up。这真的救了我的注意力。"

### 用法 2：手机远程修 Bug

**场景**：他在外面时，Chrome 插件突然收到 Bug 报告。

**以前**：要么赶回家，要么在外面焦虑一整天。

**现在**：掏出手机 Telegram → 发给 OpenClaw → 它找到问题、修好、跑测试、push commit，全部从手机完成。

> "我现在可以 brainstorm、build、fix 全从手机做，不限地点。"

### 用法 3：800 个免费用户转化

**场景**：800 个注册了但从没付费的用户。

**解决**：给 OpenClaw 建了一个 cron job，自动起草邮件序列，发给这些用户推动升级。

**结果**：真的有转化，带来了一些收入。

> "这种任务我可以做一次，然后它永远跑下去。省下大量时间和注意力。"

---

## 安全提醒

1. **只安装你审查过的 Skills** — ClaWHub 上有恶意 Skills 会偷 SSH Key
2. **最小权限原则** — 开始时限制访问，需要时再逐步开放
3. **不要用便宜模型** — 便宜模型没有足够的防御 guardrails，容易被 prompt injection 攻击

> "Prompt injection 有 91% 成功率。用更好的模型（Opus > Sonnet > Haiku）来防御。"

---

## 他的判断

> **"It's very early days for OpenClaw. Everyone is still figuring things out. And personally, I think this is the worst it's ever going to be."**

---

## 一句话总结

> **用 Kiloclaw，60 秒内把你的个人 AI Agent 接到 Telegram，24/7 不知疲倦地帮你干活。**

---

*总结时间：2026-04-07*
