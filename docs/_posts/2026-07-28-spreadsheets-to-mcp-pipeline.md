---
layout: default
title: "From Spreadsheets to MCP — A Seller Data Pipeline in 5 Minutes"
date: 2026-07-28
tags: [MCP, Amazon, ecommerce, automation, data-pipeline]
---

Every morning you export data from Seller Central, open Excel, run the same pivot tables, format the same charts. By the time you are done, it is 10am and you have not made a single decision.

This is the default operating rhythm for thousands of marketplace sellers. The data is there. The questions are clear. But the gap between source and insight is filled with repetitive manual work — exports, merges, formulas, formatting — none of which moves the business forward. The pipeline itself has become the bottleneck.

The Model Context Protocol (MCP) offers a different model. Instead of pulling data out of platforms and pushing it through a spreadsheet assembly line, an MCP server lets an AI agent connect to the data at its source and retrieve exactly what a question demands. No exports. No pivot tables. No waiting until 10am for a usable view of the market.

## The Five-Minute Setup

sorftime-seller-agent is an open-source MCP server that gives any MCP-compatible AI agent direct access to marketplace intelligence. It covers product discovery, keyword research, category trends, competitor tracking, and profitability estimation across major e-commerce platforms. The setup is a single install script:

```bash
git clone https://github.com/DannylydST/sorftime-seller-agent
cd sorftime-seller-agent
python3 scripts/install.py
```

The script registers the MCP server with the AI agent and prompts for API credentials. A free key is available at [open-intl.sorftime.com](https://open-intl.sorftime.com). After restarting the agent, all marketplace intelligence tools are available — no further configuration, no separate dashboards, no integration work.

The server works with Claude Code, Cursor, Codex CLI, and any other agent that speaks MCP. The configuration is a single JSON block dropped into the agent's MCP settings file.

## What the Pipeline Delivers

To make the shift concrete, compare two approaches to the same research task: evaluating whether the "collapsible water bottle" niche on Amazon US is worth entering.

**The spreadsheet pipeline.** Export a category report from Seller Central. Export keyword data from a research tool. Open both CSVs. Merge by ASIN in Excel. Build a pivot table for average price by material. Create a separate sheet for review velocity. Format charts. Manually scan for listings that entered the top 50 in the past 90 days. Cross-reference against estimated monthly sales. Two hours elapsed, the pivot table has a broken reference from a column re-sort, and the data is already a day old.

**The MCP pipeline.** Type into the AI agent:

> "Find collapsible water bottles on Amazon US with under 200 reviews but monthly revenue above $30,000. Show me average price, brand concentration, and whether any new sellers entered the top 30 in the past 90 days."

Behind the scenes, the agent calls multiple MCP tools — category listing, product detail, sales estimation, keyword volume — retrieves structured data from each, cross-references the results programmatically, and returns a narrative summary with supporting figures. The round trip takes seconds. The data is live. No formula errors to debug. No column sort that silently broke a VLOOKUP.

The output is not just faster. It is broader. A person clicking through dashboards typically checks five to ten data points before forming a conclusion. An agent with access to the full tool set cross-references dozens of dimensions — pricing trends, review velocity, keyword demand, seasonal patterns — in parallel, catching signals that a manual scan would miss.

## Query-Based vs. Pull-Based Architecture

The difference between the two approaches is architectural, not cosmetic.

A spreadsheet pipeline is pull-based. Data must be exported from each source, cleaned, transformed, and loaded before analysis can begin. Every step is a manual touchpoint. Every touchpoint is a potential error — a misaligned date range, a formula that references the wrong sheet, a CSV filter that silently dropped rows. When the data changes tomorrow, the entire process repeats from scratch.

An MCP pipeline is query-based. Data stays at the source. The agent retrieves exactly what the question needs, when it needs it. There are no exports to manage, no version conflicts between files downloaded on different days with different parameters, and no accumulated spreadsheet cruft from weeks of incremental patches. The question drives the retrieval. The pipeline adapts to the question, not the other way around.

This eliminates several categories of failure at once. Stale data stops being a risk — every query hits live endpoints. Formula drift stops being a risk — cross-referencing happens in code, not in cell references. The cognitive overhead of maintaining spreadsheet hygiene across dozens of weekly exports disappears.

## Beyond the Morning Routine

The same MCP connection handles recurring work without additional setup. Once the agent has access to the tools, a daily category snapshot is a scheduled prompt. Weekly competitor monitoring is a recurring query. An alert when a tracked product's rank drops below a threshold is a conditional check through the same pipeline.

These workflows do not require new API keys, new dashboards, or new tools. They are different prompts sent through the same MCP connection, scheduled with the agent's built-in automation — a cron job wrapping a terminal agent session, a Claude Code loop command, or the equivalent mechanism in whichever agent the seller uses.

The seller still decides what to research, which metrics matter, and what action to take. The pipeline handles retrieval, cross-referencing, and formatting. The seller handles judgment.

---

**Start here.**

```bash
git clone https://github.com/DannylydST/sorftime-seller-agent
cd sorftime-seller-agent
python3 scripts/install.py
```

A free MCP key is available at [open-intl.sorftime.com](https://open-intl.sorftime.com). No credit card required. After installation, open the AI agent and ask a marketplace question. The tools are wired up. The spreadsheet can wait.

---
