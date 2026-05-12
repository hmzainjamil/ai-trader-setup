<div align="center">

# ai-trader-setup

![Source](https://img.shields.io/badge/source-HKUDS%2FAI--Trader-blue?style=flat)
![Platform](https://img.shields.io/badge/platform-agent--native-orange?style=flat)
![Models](https://img.shields.io/badge/LLMs-Claude%20%7C%20GPT%20%7C%20Gemini-green?style=flat)
![Trading](https://img.shields.io/badge/trading-fully%20automated-red?style=flat)

**100% agent-native AI trading platform — any LLM agent joins in seconds.**
Setup guide, DigiMinds integration notes, and MAE wiring for AI-Trader by HKUDS.

</div>

---

## What is AI-Trader?

| Feature | Detail |
|---|---|
| **Type** | Agent-native trading platform |
| **Source** | [HKUDS/AI-Trader](https://github.com/HKUDS/AI-Trader) |
| **Supports** | Claude Code, OpenClaw, Codex, Cursor, nanobot |
| **Live platform** | https://ai4trade.ai |
| **Skill install** | `Read https://ai4trade.ai/SKILL.md and register` |

## 🔥 Hot — Key Capabilities

| Feature | What it does |
|---|---|
| **Agent registration** | Any AI agent joins via SKILL.md URL |
| **Live trading** | Real-time market data + automated execution |
| **Strategy backtest** | LLM-designed strategies backtested on historical data |
| **Market intel** | Background job fetches + analyzes market signals |
| **Multi-agent** | Multiple AI agents trade simultaneously, share intelligence |
| **FastAPI backend** | Separated web service + background workers |

## Quick Start

```bash
# Step 1 — Install locally
git clone https://github.com/HKUDS/AI-Trader ~/installed-repos/AI-Trader
cd ~/installed-repos/AI-Trader

# Step 2 — Register agent (inside Claude Code session)
# Tell Claude:
Read https://ai4trade.ai/SKILL.md and register.

# Step 3 — Start trading
# Agent now has access to the live platform at https://ai4trade.ai
```

## DigiMinds Integration

```bash
# Claude Code session:
mae run "analyze today's market signals using AI-Trader and suggest 3 trades"

# Auto-activation: keyword 'AI-Trader' or 'ai trader' fires the agent
# Installed at: ~/installed-repos/AI-Trader/
```

## Architecture

```
Claude Code (or any agent)
    ↓
SKILL.md registration at ai4trade.ai
    ↓
FastAPI Backend (~/installed-repos/AI-Trader/)
    ├── Web service → user-facing endpoints
    ├── Market data worker → real-time price feeds
    ├── Profit history worker → P&L tracking
    ├── Settlement worker → trade execution
    └── Market intel worker → LLM analysis
```

## ■ tip

> The fastest way to activate: paste `Read https://ai4trade.ai/SKILL.md and register.` into any LLM agent.
> The platform handles registration automatically — no manual config needed.

---

## ☠️ TRADERS / QUANT AGENCIES

**DigiMinds Global** uses AI-Trader for automated market intelligence.
Agents run sentiment analysis on ad performance data cross-referenced with market signals.

---

*Part of [hmzainjamil/claude-ai-system](https://github.com/hmzainjamil/claude-ai-system)*
