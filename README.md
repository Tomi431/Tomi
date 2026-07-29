# 📦 Amazon Seller MCP Playbook

<p align="center"><em>Copy-pasteable MCP playbooks for Amazon sellers — no engineering required.</em></p>

<p align="center">
  <strong>Amazon</strong> · <strong>Walmart</strong> · <strong>TikTok Shop</strong> · <strong>Shopee</strong> · <strong>TEMU</strong> · <strong>1688</strong>
</p>

> **Run a marketplace intelligence workflow in your AI agent. No spreadsheet. No tab-switching. No dashboards.**
>
> Agent-agnostic, MCP-native guides. Works with **Claude Code, Codex, Cursor, OpenClaw, Hermes, Pi** — any MCP-compatible AI agent.
> 6 working playbooks. Amazon · Walmart · TikTok Shop · 1688 · Shopee · TEMU.
>
> **Talk to your AI. Get the answer.**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Agent-Agnostic](https://img.shields.io/badge/Agent-Claude%20%7C%20Codex%20%7C%20Cursor%20%7C%20OpenClaw-purple)]()
[![MCP](https://img.shields.io/badge/MCP-native-orange)]()
[![Platforms](https://img.shields.io/badge/Platforms-6-blue)]()
[![Updated](https://img.shields.io/badge/Updated-2026--07--29-brightgreen)]()

---

## ⚡ Quick Start

### 1. Pick a playbook
Open the article that matches your immediate need. They're written as standalone guides — no reading order required.

### 2. Install the underlying tool
Most guides use **Sorftime** for marketplace data. Free signup at [open-intl.sorftime.com](https://open-intl.sorftime.com). MCP key ready in 2 minutes.

### 3. Copy the prompt into your AI agent
```bash
# Example: Article 06 — Mine Amazon Reviews for Product Ideas
> "Use the Sorftime MCP tools to pull all 4-star reviews for ASIN B0758XHPP4,
>  extract common feature requests, and cluster them into 3 product idea themes."
```

---

## 🤔 Why This Exists

Most Amazon sellers know what they want to ask ("What's the margin on this product?" "Is this keyword worth targeting?"). But the path to the answer is:

```
Before:  open 5 tabs → login to SaaS → click through filters → export CSV → paste into Sheets → write formulas → scroll → decide
        (15–45 minutes per question)

After:   "What's the margin on ASIN B08N5WRWNW at $29.99 with $8.50 cost?"
         → answer in 20 seconds
```

These playbooks cut the loop. Every guide is **a single copy-paste prompt + a working tool** — built for sellers who want to ship, not configure.

---

## 📚 The 6 Playbooks

| # | Playbook | What You Get | Read Time |
|---|----------|--------------|-----------|
| 01 | [Automating Weekly Product Research With Claude and MCP](./posts/01-automating-product-research.md) | A recurring Monday-morning product scan, fully automated | 8 min |
| 02 | [No Terminal? No Problem — How Non-Technical Amazon Sellers Can Use MCP Today](./posts/02-no-terminal-mcp.md) | Use MCP from Cursor in 3 minutes, zero command-line | 5 min |
| 03 | [Calculate Amazon Profit in Seconds — Not Hours — With Your AI Agent](./posts/03-calculate-amazon-profit.md) | Run any profit scenario with FBA fees, returns, ads | 6 min |
| 04 | [Spot Seasonal Trends Before Your Competitors — Data-Driven Timing With MCP](./posts/04-spot-seasonal-trends.md) | Find the 4-week window when demand spikes | 7 min |
| 05 | [From Spreadsheets to MCP — Build a Seller Data Pipeline in 5 Minutes](./posts/05-seller-data-pipeline.md) | Replace your weekly spreadsheet with a one-line prompt | 9 min |
| 06 | [Mine Amazon Reviews for Product Ideas — Automatically With AI](./posts/06-mine-amazon-reviews.md) | Pull thousands of reviews, cluster into product ideas | 10 min |

---

## 🤖 Agent-Friendly by Design

> **Same playbook, six different agents — Claude Code, Codex, Cursor, OpenClaw, Hermes, Pi.**

These playbooks are written as **agent-agnostic** from the first sentence. No Claude-specific prompts. No Cursor-only tricks. Every guide:

- **Speaks MCP** — uses the standard Model Context Protocol, no proprietary plumbing
- **Auto-detects environment** — works on macOS, Linux, Windows
- **Bilingual** — supports English and Chinese queries in the same playbook
- **Self-contained** — install once, run anywhere

| Agent / IDE | Setup Time | How |
|-------------|-----------|-----|
| **Claude Code** | < 3 min | `mcporter` auto-detection |
| **Codex (OpenAI)** | < 5 min | MCP server import |
| **Cursor** | < 3 min | MCP config snippet |
| **OpenClaw** | < 3 min | Native skill directory |
| **Hermes** | < 5 min | MCP JSON config |
| **Pi (Inflection)** | < 5 min | MCP endpoint registration |
| **Any MCP Agent** | < 5 min | Standard `tools/list` → `tools/call` |

---

## 🆚 How This Compares

| | Other Seller Guides | **Amazon Seller MCP Playbook** |
|---|---------------------|-------------------------------|
| **Format** | 2,000-word blog posts | **Copy-pasteable prompts** |
| **Tooling** | Generic ChatGPT tips | **Real MCP server queries** |
| **Data source** | Hypothetical examples | **Live Sorftime data** |
| **Agents** | One agent only | **6 agents, same prompt** |
| **Update cycle** | Annual rewrites | **Continuous playbook additions** |
| **Cost** | Free reads, no actual tool | **Free playbook + free Sorftime tier** |
| **Learning curve** | Read 10 articles | **Pick one, run it today** |

---

## 💬 Example Conversation

### Run a profit scenario

> **You**: "I'm sourcing yoga mats at $8.50/piece. I want to sell at $29.99, weight 1.2lb. Should I?"
>
> **Agent**: *[Calls Sorftime Profit Calculator with FBA fee estimate]*
> "Gross margin: 38%. Break-even: 9 units/day. Return rate sensitivity: profit stays positive up to 12% returns. Verdict: viable — proceed."

### Find a Blue Ocean product

> **You**: "Find blue ocean products in kitchen storage on Amazon US. I'm a beginner with $5K budget."
>
> **Agent**: *[Scans Hidden Profit Index, filters by low competition, beginner-friendly categories]*
> "Here are 5 opportunities with low brand concentration, <500 reviews on top listings, healthy margins. #1: Under-sink organizers — 15K monthly searches, only 3 competitors with >100 reviews."

### Pull competitor intelligence

> **You**: "Analyze ASIN B08N5WRWNW — give me their traffic keywords and pricing strategy."
>
> **Agent**: *[Calls ProductDetail, TrafficTerms, CompetitorKeywords]*
> "Gaiam Yoga Block — 40K monthly sales, 4.7 stars, $18.99. Top 3 traffic keywords: 'yoga block' (52K), 'yoga blocks 2 pack' (28K), 'cork yoga block' (15K). FBA fee: $12.82. Threat: medium."

---

## 🌍 Tools Behind These Playbooks

| Tool | Role | Why It's First |
|------|------|----------------|
| **[Sorftime](https://sorftime.com)** | Marketplace data layer | 86 MCP tools, 160+ dimensions, free tier |
| Claude Code | AI agent | First-class MCP support |
| Cursor | AI editor | Native MCP sidebar |
| OpenAI Codex | AI agent | MCP server import |
| OpenClaw | AI agent | Skill directory auto-detect |
| Pi | AI agent | MCP endpoint support |

---

## 🙋 FAQ

**Q: Which playbook should I start with?**
If you only have 5 minutes, read **02 (No Terminal)** — it gets you running in Cursor. If you have 30 minutes, **05 (Data Pipeline)** — biggest immediate ROI.

**Q: Do I need to pay for anything?**
No. Every playbook works with **Sorftime's free tier**. The MCP key is free.

**Q: Will these work with my AI agent?**
If your agent speaks MCP, yes. The 6 supported agents are listed above. Custom agents work too via standard MCP protocol.

**Q: What if my prompt fails?**
Each article ends with a **Troubleshooting** section. Most failures are MCP key misconfig — fix takes 30 seconds.

**Q: Why GitHub Pages?**
Because the playbooks are versioned. Every commit is a deploy. Every diff is a changelog. Every issue is a feature request.

**Q: Is this the same as the Sorftime Seller Agent?**
This is the **content layer**. The Seller Agent is the **tool layer**. Same source of truth, different audience — playbooks for sellers, tools for engineers.

---

## 📄 License

MIT © [Tomi431](https://github.com/Tomi431) · Sorftime market team

---

*Built for sellers. By sellers.*
