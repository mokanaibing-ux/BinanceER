# BinanceER
币安用户的链上急救室 — 专注问题诊断与实时处置的 AI Agent
# BinanceER — 币安用户的链上急救室

> 专注问题诊断与实时处置的 AI Agent

## 简介

BinanceER 是基于 OpenClaw + Binance Skills Hub 构建的币安急救 AI Agent。当币安用户遇到提币未到账、误操作订单、账号被盗、合约爆仓等紧急情况时，BinanceER 用三色急救等级制度快速分诊，调用真实币安技能包数据诊断，给出小白能照做的处置步骤。

**不预测行情，只解决问题。**

## 技术规格

- **Claw**：OpenClaw 2026.3.13
- **模型**：openrouter/anthropic/claude-sonnet-4.5
- **技能包**：Binance Skills Hub 全量 12 个技能

## 核心功能

| 场景 | 功能 | 技能 |
|------|------|------|
| 🚨 提币未到账 | 链上状态查询+处置方案 | address-insight |
| 💸 误操作订单 | 撤单判断+止损方案 | spot |
| 🔐 账号安全紧急 | 立即冻结+2FA重置 | spot |
| 📉 杠杆合约意外 | 爆仓价计算+平仓建议 | derivatives |
| 🔍 代币安全核查 | 合约审计+三色结论 | query-token-audit |
| 🏥 账号安全体检 | 安全评分+修复建议 | spot |

## 急救等级制度

- 🔴 **红色警报**：账号安全/资金异常 — 立即处理（0-5分钟）
- 🟡 **黄色预警**：提币未到/交易问题 — 尽快处理（30分钟内）
- 🟢 **绿色提示**：操作疑问/功能咨询 — 按步骤处理

## 快速部署
```bash
# 1. 安装OpenClaw
npm install -g openclaw

# 2. 克隆币安技能包
git clone https://github.com/binance/binance-skills-hub /tmp/binance-skills
sudo cp -r /tmp/binance-skills/skills/* /usr/local/lib/node_modules/openclaw/skills/

# 3. 复制SOUL.md
cp SOUL.md ~/.openclaw/SOUL.md

# 4. 启动
openclaw gateway run --auth none
```

## 作者

恐高的灰白 · 基于 OpenClaw 2026.3.13 + Binance Skills Hub + Claude Sonnet 4.5
