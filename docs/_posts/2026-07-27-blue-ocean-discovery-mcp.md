---
layout: post
title: "Blue Ocean Product Discovery — Let AI Find Your Next Winning Category"
date: 2026-07-27
tags: [MCP, Amazon, AI, ecommerce]
---

Everyone is looking at the same Best Seller lists. The real opportunities are in categories with high demand and low competition — the ones nobody is watching.

The logic is straightforward. When a category appears on a Best Seller list, thousands of sellers see it within hours. By the time you finish supplier research, ten more sellers have already shipped inventory to FBA. The window closes before you open it.

The categories worth entering are not on those lists. They are hiding one or two levels deeper in the category tree — subcategories where demand is real, reviews are thin, and the top listings are not fortified behind thousands of ratings. Finding them manually means clicking through hundreds of subcategory pages, running spreadsheets, and guessing which metrics actually signal opportunity.

That manual process is not discovery. It is gambling with more steps.

The sorftime-seller-agent changes the equation. It is an open-source MCP server that connects your AI agent directly to marketplace data, letting you find blue ocean categories with a few plain-English questions instead of a hundred browser tabs.

---

## What Blue Ocean Actually Means in Marketplace Terms

"Blue ocean" gets thrown around loosely. In the context of marketplace selling, it has a specific, measurable definition: a product subcategory where demand signals are strong but competitive defensibility is weak.

The numbers that reveal this are available. They just are not surfaced by tools optimized to show you what everyone else is already looking at.

A blue ocean category typically shows:

- **High demand-to-review ratio.** The top 10 listings have meaningful sales volume but low review counts — typically under 200 reviews. This indicates the incumbents have not yet built deep moats.
- **Fragmented brand share.** No single brand controls more than 15 to 20 percent of the top 20 positions. Dominance by one or two brands means the category is red, regardless of review counts.
- **Positive demand trajectory.** Search volume for the category's main keywords is growing month over month, not flat or declining. A small pond that is shrinking is not an opportunity.
- **Reasonable price dispersion.** The top 20 listings cluster in a price band with enough margin to support a new entrant, rather than racing to the bottom at breakeven.

A human can check these signals for one category in about 30 minutes, assuming they know which columns to look at and where to find the data. An AI agent connected to marketplace data through MCP can scan dozens of categories against these criteria in under a minute.

The difference is not quality of analysis. It is coverage. You cannot find the hidden category if you never look at it.

---

## How MCP Makes This Possible

Model Context Protocol (MCP) is an open standard that lets AI agents call external tools and data sources directly. Instead of building custom integrations for every AI-and-tool combination, you define the tools once as an MCP server. Any MCP-compatible agent discovers and uses them automatically.

The sorftime-seller-agent is that server for marketplace intelligence. It exposes 86 tools covering product research, category analysis, keyword discovery, competitive profiling, and profit estimation across multiple marketplaces. Your AI agent — Claude Code, Codex CLI, Cursor, or any MCP client — gains the ability to query live marketplace data as naturally as it looks up documentation or searches a codebase.

The workflow shifts from "open tool, run report, export CSV, open another tool, cross-reference" to "ask a question, get an answer, make a decision."

---

## Finding Blue Ocean Categories: A Concrete Prompt

Here is a prompt you can use today. After installing the sorftime-seller-agent and connecting it to your AI agent, paste this in:

```
Scan Amazon US subcategories under Home & Kitchen. For each subcategory
with at least 500 monthly searches on its primary keyword:

1. Retrieve the top 20 ASINs ranked by estimated monthly sales.
2. Calculate the average review count for those top 20 listings.
3. Count how many distinct brands occupy the top 20.
4. Check month-over-month search volume trend for the top 3 keywords
   in the category.
5. Calculate the median price of the top 20 and the price range.

Filter to subcategories where:
- Average review count of top 20 is under 200.
- At least 8 distinct brands appear in the top 20 (no monopoly).
- Primary keyword search volume is growing over the last 3 months.
- Median price is above $15 (filters out commodity price-war zones).

Return the top 5 candidates with:
- Subcategory name
- Average reviews of top 20
- Number of distinct brands in top 20
- Primary keyword monthly search volume and 3-month trend
- Median price and price range
- One-sentence opportunity summary
```

![Example output: blue ocean subcategories ranked by demand-to-competition ratio.](/Tomi/assets/images/A1.png)
*Example output: blue ocean subcategories ranked by demand-to-competition ratio.*


The AI agent calls the relevant MCP tools — category listing, product ranking, keyword volume, review counts — applies the filtering logic you specified, and returns a shortlist. You are not scrolling through category pages hoping to spot something. You are defining the criteria for what "opportunity" means and letting the agent find matches.

---

## What the Numbers Tell You That Best Seller Lists Cannot

Best Seller lists answer one question: what is selling the most right now. That question is useful, but it misses three critical dimensions that determine whether a category is enterable.

**Competitive defensibility.** A product selling 3,000 units a month with 2,500 reviews is a fortress. A product selling 1,800 units a month with 60 reviews is a door. Best Seller rank does not distinguish between them. Review count provides that signal, and an MCP-connected agent can scan for it at scale.

**Brand concentration.** A category where the top 10 listings belong to three brands is a different environment from one where the top 10 span nine brands. Both can appear on a Best Seller list. The second is far more accessible to a new entrant. The brand concentration ratio takes five seconds to calculate once you have the data. Most sellers never calculate it because the data is not presented that way in existing tools.

**Demand direction.** A category doing $2 million a month that is shrinking by 10 percent quarter over quarter is worse than a category doing $500,000 a month growing by 25 percent. Best Seller lists show the snapshot. They do not show the trajectory. Search volume trends over time — available through keyword research endpoints — reveal whether the tide is coming in or going out.

Combining these three signals — review depth, brand fragmentation, and demand trajectory — produces a view of a category that a single ranking metric cannot provide. The sorftime-seller-agent makes it practical to apply this lens across dozens of categories at once, rather than painstakingly for one or two.

---

## Install and Start Scanning

The sorftime-seller-agent is open source. Installation takes one command.

```bash
git clone https://github.com/DannylydST/sorftime-seller-agent && cd sorftime-seller-agent && python3 scripts/install.py
```

You need Python 3.10 or later and an MCP-compatible AI agent. The installer sets up a virtual environment, registers the MCP server with your agent, and prompts you to enter a Sorftime API key — available free at [open-intl.sorftime.com](https://open-intl.sorftime.com). No credit card required. The key stays on your machine.

After installation, restart your AI agent. It auto-discovers all 86 MCP tools. Copy the blue ocean scanning prompt from this article, adjust the parent category and filtering thresholds to match your strategy, and run it. The first scan takes under a minute. The categories your competitors are not looking at will be in the output.

---

## References

[1] Sorftime Seller Agent GitHub Repository — https://github.com/DannylydST/sorftime-seller-agent

[2] Sorftime International MCP Portal — https://open-intl.sorftime.com

[3] Model Context Protocol Specification — https://modelcontextprotocol.io
---
