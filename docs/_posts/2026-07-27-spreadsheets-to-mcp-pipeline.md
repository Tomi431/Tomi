---
layout: default
title: "From Spreadsheets to MCP — Build a Seller Data Pipeline in 5 Minutes"
date: 2026-07-27
tags: [MCP, Amazon, AI, ecommerce]
---

Every Monday you export CSVs from 3 tools, merge them in Excel, and spend 2 hours making sense of it. By Tuesday morning the data is already stale, and half the columns you pulled turn out to be irrelevant. The following week, the same cycle repeats.

This ritual costs more than time. Manual data pipelines introduce errors at every step — copy-paste mistakes, broken formulas, inconsistent date ranges. Worse, they create latency between when data becomes available and when decisions get made. In a marketplace where pricing, rankings, and inventory shift by the hour, a 48-hour gap between data pull and analysis is a structural disadvantage.

The Model Context Protocol (MCP) changes this by letting AI agents connect directly to data sources. Instead of exporting data and feeding it to an analysis tool, the analysis tool connects to the data at the source. A single natural-language question can pull live data from multiple endpoints, cross-reference it, and deliver a formatted answer — all without touching a spreadsheet.

## What sorftime-seller-agent Does

sorftime-seller-agent is an open-source MCP server that gives any MCP-compatible AI agent — Claude, Cursor, Codex, and others — direct access to marketplace intelligence. It covers product research, keyword analysis, category trends, competitor tracking, and profit estimation across major e-commerce platforms. Once configured, the agent becomes a data analyst that reads live marketplace data on demand.

The setup takes a single configuration file and one install command. Drop the following into the MCP configuration for the agent of choice:

```json
{
  "mcpServers": {
    "sorftime-seller-agent": {
      "command": "python3",
      "args": ["-m", "sorftime_seller_agent"],
      "env": {
        "SORFTIME_API_KEY": "your-api-key"
      }
    }
  }
}
```

For Claude, this goes into `claude_desktop_config.json`. For Cursor, `.cursor/mcp.json`. For Codex, the equivalent MCP settings file. Run the install script once, restart the agent, and marketplace data tools are available immediately.

## From Query to Insight in Seconds

A concrete example makes the shift tangible. Consider a seller evaluating the competitive landscape for yoga mats on Amazon US — a category with thousands of listings, wide price dispersion, and frequent new entrants.

The manual approach: export a category report, filter by subcategory, pull individual ASIN data for the top listings, cross-reference review counts and estimated revenue, build a pricing table in Excel, and manually scan for patterns. Two to three hours, assuming no formula errors and no need to re-export when a filter was wrong.

With sorftime-seller-agent configured, the same research begins with a single sentence typed into the agent:

> "Analyze the top 50 yoga mats on Amazon US. Show average price by material type, identify listings with under 100 reviews but strong revenue growth, and flag products that entered the category in the last 90 days with monthly revenue above $50,000."

Behind the scenes, the agent calls the relevant MCP tools — category listing, product detail, sales estimation — retrieves structured data from each endpoint, and synthesizes the answer. The round trip runs in seconds. The data is live. Cross-referencing happens programmatically, not through VLOOKUP. The output is a narrative summary with supporting tables, ready to inform a sourcing decision or discard a bad lead before hours are wasted.

## Why the Architecture Matters

The difference between spreadsheets and MCP is architectural, not cosmetic.

A spreadsheet pipeline is pull-based: data must be exported, cleaned, transformed, and loaded before analysis can begin. Every step is a manual touchpoint. Every touchpoint is a potential error. When the data changes tomorrow, the whole process repeats from scratch.

An MCP pipeline is query-based: data lives at the source, and the agent retrieves exactly what is needed, when it is needed. No exports. No cleaning. No version conflicts between CSV files exported on different days with different filters. The question drives the data retrieval, not the other way around.

This eliminates several categories of failure at once: stale data, formula drift, silent filter mismatches, and the cognitive overhead of maintaining spreadsheet hygiene across dozens of weekly exports.

## Beyond One-Off Research

The same MCP connection supports recurring workflows without additional integration work. A daily category snapshot becomes a scheduled prompt. Weekly competitor monitoring becomes a recurring query. An alert when a tracked product's rank drops below a threshold is a simple conditional check run through the same pipeline.

These are not separate integrations requiring new API keys, new dashboards, or new tools. They are different prompts sent through the same MCP connection, scheduled with the agent's built-in automation — Claude Code's loop command, a cron job wrapping a Cursor agent session, or any equivalent mechanism.

## Who This Is For

sorftime-seller-agent is designed for marketplace sellers who already understand their business but waste too many hours on data logistics. It does not replace domain expertise — the seller still decides what to research, which metrics matter, and what action to take. The pipeline handles retrieval, cross-referencing, and formatting. The seller handles judgment.

The tool is open-source and free to use. The data coverage spans major global marketplaces, and the MCP interface means it works with whichever AI agent the seller already prefers.

Try it:

```
git clone https://github.com/DannylydST/sorftime-seller-agent && cd sorftime-seller-agent && python3 scripts/install.py
```

Free at [open-intl.sorftime.com](https://open-intl.sorftime.com).
---
