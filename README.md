# ai-trader-setup
HKUDS AI-Trader + LLM stock trading agent setup and DigiMinds integration

![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat&labelColor=555&logo=python)
![LLM](https://img.shields.io/badge/LLM-Trading_Agent-gold?style=flat&labelColor=555)
![Finance](https://img.shields.io/badge/Finance-Stock_Analysis-green?style=flat&labelColor=555)
![Claude](https://img.shields.io/badge/Claude-Code-cc785c?style=flat&labelColor=555)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat&labelColor=555)

[Concepts](#-concepts) · [How It Works](#️-how-it-works) · [Install](#-install) · [Strategies](#-trading-strategies) · [Tips](#-tips-and-tricks-10) · [Startups](#️-startups--businesses)

---

## 🧠 CONCEPTS

| Feature | Location | Description |
|---------|----------|-------------|
| [**AI-Trader Core**](AI-Trader/) | `AI-Trader/` | HKUDS LLM-powered equity analysis + signal generation |
| [**LLM Analysis**](AI-Trader/src/) | `src/analysis.py` | GPT/Claude analyzes earnings, news, filings for trade signals |
| [**DigiMinds Integration**](digiminds-bridge/) | `digiminds-bridge/` | Wires AI-Trader signals into DigiMinds ops dashboard |
| [**Position Sizing**](AI-Trader/src/) | `src/risk.py` | Kelly criterion + max drawdown guard |
| [**Multi-source Data**](AI-Trader/src/) | `src/data.py` | Yahoo Finance + SEC filings + news sentiment |
| [**Signal Dashboard**](AI-Trader/dashboard/) | `dashboard/` | Real-time signal viewer + backtest results |

### 🔥 Hot

| Feature | Location | Description |
|---------|----------|-------------|
| [**LLM Earnings Analysis**](AI-Trader/src/) | `src/earnings.py` | Claude reads full earnings call transcript → bull/bear thesis |
| [**News Sentiment**](AI-Trader/src/) | `src/sentiment.py` | Real-time news → LLM sentiment score → trade signal |
| [**Zero-human signals**](AI-Trader/) | `run.py` | Daily pre-market scan runs automatically at 8 AM |

---

## ⚙️ HOW IT WORKS

```
8:00 AM — pre-market scan fires
         ↓
Data pull: Yahoo Finance + SEC EDGAR + news APIs
         ↓
LLM analysis (Claude/GPT):
  ├── Earnings transcript → bull/bear thesis
  ├── News headlines → sentiment score (-1 to +1)
  ├── Technical indicators → momentum signal
  └── Filing analysis → risk flags
         ↓
Signal aggregation → BUY / SELL / HOLD + confidence
         ↓
Dashboard update + DigiMinds notification
```

> ⚠️ Educational tool — not financial advice. Paper trade before live.

---

## 🚀 INSTALL

```bash
git clone https://github.com/hmzainjamil/ai-trader-setup
cd ai-trader-setup
pip install yfinance openai anthropic pandas numpy ta
cp .env.example .env
# Add: OPENAI_API_KEY, ANTHROPIC_API_KEY, NEWS_API_KEY
python3 run.py --paper-trade
```

---

## 📈 TRADING STRATEGIES

| Strategy | Description | Win Rate (backtest) |
|---|---|---|
| Earnings Surprise | LLM reads transcript → size vs expectations | ~62% |
| News Momentum | Sentiment surge + volume → momentum entry | ~58% |
| Filing Alert | 10-K/10-Q risk language → pre-announce exit | ~71% |
| Technical + LLM | TA signal confirmed by LLM thesis | ~65% |

---

## 💡 TIPS AND TRICKS (10)

[setup](#tips-setup) · [signals](#tips-signals) · [risk](#tips-risk) · [llm](#tips-llm)

<a id="tips-setup"></a>■ **Setup (2)**

| Tip | Source |
|-----|--------|
| Paper trade for 30 days before live — validate signal quality on your watchlist | [HMZ](https://github.com/hmzainjamil) |
| Use DeepSeek for analysis (cheap) + Claude for final thesis verification (accurate) | [DigiMinds](https://github.com/hmzainjamil) |

<a id="tips-signals"></a>■ **Signals (3)**

| Tip | Source |
|-----|--------|
| Earnings surprise beats all signals — combine LLM thesis with actual vs estimate delta | [HMZ](https://github.com/hmzainjamil) |
| News sentiment lag: market moves in 15min, you need signal in <5min to be useful | [DigiMinds](https://github.com/hmzainjamil) |
| Confirmation rule: require 2/3 signals (LLM + TA + sentiment) before entry | [HMZ](https://github.com/hmzainjamil) |

<a id="tips-risk"></a>■ **Risk (3)**

| Tip | Source |
|-----|--------|
| Max 2% per trade Kelly — LLM signals are ~65% accurate, not 90% | [HMZ](https://github.com/hmzainjamil) |
| Hard stop -5% on any position — LLMs can hallucinate confident wrong thesis | [DigiMinds](https://github.com/hmzainjamil) |
| Never trade earnings day — hold until day+2 when transcript analysis is complete | [HMZ](https://github.com/hmzainjamil) |

<a id="tips-llm"></a>■ **LLM Analysis (2)**

| Tip | Source |
|-----|--------|
| Prompt: "Summarize bull case, bear case, and risk factors in 3 bullets each" | [HMZ](https://github.com/hmzainjamil) |
| Structured output: ask LLM to return JSON `{signal, confidence, thesis, risks}` | [DigiMinds](https://github.com/hmzainjamil) |

---

## ☠️ STARTUPS / BUSINESSES

| This Repo / Feature | Replaced |
|-|-|
| **LLM earnings analysis** | [Motley Fool](https://fool.com), [Seeking Alpha](https://seekingalpha.com) premium |
| **News sentiment signals** | [Bloomberg Terminal](https://bloomberg.com/professional), [Refinitiv](https://refinitiv.com) |
| **Auto trade signals** | [Trade Ideas](https://trade-ideas.com), [Benzinga Pro](https://benzinga.com/pro) |
| **Filing analysis** | [Calcbench](https://calcbench.com), [Sentieo](https://sentieo.com) |

---

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=hmzainjamil/ai-trader-setup&type=Date)](https://star-history.com/#hmzainjamil/ai-trader-setup&Date)

---

<div align="center">
Built by <a href="https://github.com/hmzainjamil">HMZ</a> · LLM-powered equity analysis — educational use only
</div>
