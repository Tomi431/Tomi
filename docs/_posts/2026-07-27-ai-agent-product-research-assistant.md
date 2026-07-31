---
layout: default
title: "How to Turn Your AI Agent Into an Amazon Product Research Assistant"
date: 2026-07-27
tags: [MCP, Amazon, AI, ecommerce]
---


You are a seller. It is Monday morning. You need to find your next product.

You open your browser. One tab for search volume data. Another for category rankings. A third for competitor listings — you are cross-referencing prices, review counts, and BSR trends manually. You copy numbers into a spreadsheet. You flip back to another tool to check FBA fee estimates. Thirty minutes later, you have looked at maybe four or five products, and you are not sure about any of them.

This is the default workflow for most Amazon sellers. It works, but it is slow, repetitive, and prone to missed signals. Every minute spent tab-switching is a minute not spent making decisions.

What if, instead of digging through dashboards yourself, you could ask your AI agent a single question and get back an analyzed shortlist — with category data, competition levels, profit estimates, and risk flags — in under a minute.

That is what the **sorftime-seller-agent** does. It is an open-source MCP (Model Context Protocol) tool that connects any compatible AI agent directly to Amazon marketplace data. Instead of you hunting for information across tools, your AI agent queries the data for you, structures the results, and surfaces what matters.

---

## What MCP Actually Means Here

MCP is a protocol that lets AI agents call external tools — databases, APIs, filesystems — without a human copying and pasting between them. Think of it as giving your AI agent a set of hands.

When you install sorftime-seller-agent, you give your AI agent access to marketplace intelligence tools. Your agent can query product search results, pull category reports, analyze keyword data, calculate FBA fees, and check historical trends — all through function calls, not browser tabs.

It works with any MCP-compatible agent: Claude Code, Codex CLI, Cursor, and OpenClaw. If your AI tool supports MCP, it can use sorftime-seller-agent.

---

## How It Looks in Practice

You are researching the kitchen storage category on Amazon US. Instead of the multi-tab manual routine, you type:

```
Find blue ocean products in kitchen storage on Amazon US.
Identify ones with low brand concentration, strong demand, and manageable competition for a new seller.
```
![Blue ocean product discovery output in kitchen storage](/Tomi/assets/images/A1.png)
*Example output: top blue-ocean picks in kitchen storage ranked by Hidden Profit Index, with profit estimates and risk flags.*


Your AI agent calls the relevant tools — `product_search`, `category_report`, `keyword_detail`, `potential_product` — and returns something like:

- **Top opportunities in kitchen storage**, ranked by the proprietary Invisible Profit Index, which weights demand density against competitive intensity
- **Brand concentration warnings** on subcategories where three brands control more than 40% of sales
- **Risk flags** for products in price wars, seasonal traps, or categories with high return rates
- **FBA fee estimates** and breakeven calculations for each candidate
- **Traffic term analysis** showing which keywords competitors rely on and where gaps exist

What used to take 15 to 30 minutes of manual cross-referencing now takes roughly 20 seconds.

---

## Setting It Up

Installation takes one command.

```bash
git clone https://github.com/DannylydST/sorftime-seller-agent && cd sorftime-seller-agent && python3 scripts/install.py
```

The installer handles virtual environment setup, dependency installation, and MCP configuration. You will be prompted for your Sorftime MCP key — get one free at [open-intl.sorftime.com](https://open-intl.sorftime.com). The key is stored locally and never leaves your machine.

Once installed, configure your AI agent to load the MCP server. For Claude Code, add this to your MCP configuration:

```json
{
  "mcpServers": {
    "sorftime-seller-agent": {
      "command": "python3",
      "args": ["-m", "sorftime_mcp"],
      "env": {
        "SORFTIME_MCP_KEY": "your-key-here"
      }
    }
  }
}
```

After that, you are ready. Ask your AI agent anything about Amazon marketplace data, and it can answer with real-time analysis instead of training-data guesses.

---

## What Is Under the Hood

The tool exposes 86 analysis functions across six marketplaces — Amazon, Walmart, TikTok Shop, Shopee, TEMU, and 1688 — covering more than 160 analysis dimensions. These include:

- **Product search and detail** — ASIN-level data, variation breakdowns, review mining, traffic terms
- **Category intelligence** — full category reports, node-level rankings, historical trends
- **Keyword analysis** — search volume, competition intensity, long-tail extensions, organic position tracking
- **Competitor profiling** — brand concentration, listing quality gaps, review velocity, pricing strategy
- **Profit calculation** — FBA fee estimates, breakeven analysis, return rate sensitivity
- **Market opportunity scoring** — the Invisible Profit Index ranks products by demand-to-competition ratio across entire categories

The tool does not make decisions for you. It provides structured data and analysis so you can make informed ones. Amazon is a complex marketplace — margins, seasonality, category restrictions, and competition dynamics all interact in ways no single metric can capture. The goal is not to replace seller judgment but to eliminate the tedious data-gathering that eats up the time you should be spending on strategy.

---

## Before and After

| Step | Manual Workflow | With sorftime-seller-agent |
|------|----------------|---------------------------|
| Find products in a category | Browse Amazon, scroll through listings, manually note ASINs | "Search kitchen storage on Amazon US and rank by opportunity" |
| Check competition | Open each listing, count reviews, estimate sales, check brand presence | Your AI returns brand concentration %, review velocity, and competitive intensity in one pass |
| Analyze keywords | Use a keyword tool, export CSV, cross-reference with listings | "What keywords are driving traffic for these top 5 ASINs, and where are the gaps" |
| Estimate profit | Manually input weight, dimensions, price into an FBA calculator | "Calculate breakeven for this product at $24.99 with $8.50 COGS and 1.2 lbs" |
| Total time per product | 15 to 30 minutes | Under 60 seconds |

---

## What It Does Not Do

The sorftime-seller-agent does not promise to find winning products. It does not guarantee revenue, forecast exact sales, or eliminate business risk. It is a data access and analysis tool. The quality of your decisions still depends on your understanding of your market, your supply chain, and your customers.

It is also worth noting that marketplace data has inherent limitations. Sales estimates are modeled, not reported. Category data reflects snapshots, not real-time streams. The tool surfaces what is available and flags what is uncertain — the rest is on you.

---

## Try It

The sorftime-seller-agent is open source and free to start. Clone the repository, run the installer, and ask your AI agent its first question.

```bash
git clone https://github.com/DannylydST/sorftime-seller-agent && cd sorftime-seller-agent && python3 scripts/install.py
```

Then ask your AI:

```
Find blue ocean products in [your category] on Amazon US.
```

A free MCP key is available at [open-intl.sorftime.com](https://open-intl.sorftime.com). No credit card required.

---

## References

[1] Sorftime Seller Agent GitHub Repository — https://github.com/DannylydST/sorftime-seller-agent
[2] Sorftime International MCP Portal — https://open-intl.sorftime.com
[3] Model Context Protocol Specification — https://modelcontextprotocol.io
---
