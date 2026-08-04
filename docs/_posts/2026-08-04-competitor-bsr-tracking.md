---
layout: default
title: "Track Your Competitors' BSR Before They Know You Are Watching"
date: 2026-08-04
tags: [Amazon, Competitor-Analysis, Data, Automation]
---

A competitor drops their price by $3. Their BSR improves from #2,400 to #890 in 48 hours. Your sales dip 15% and you do not know why until you check your monthly report two weeks later. By then they have taken 200 units of market share.

Competitor monitoring is the highest-ROI automation in e-commerce — and the one most sellers skip because "it takes too much time." Here is how to set it up once and let it run.

## What to Track and Why

**BSR (Best Sellers Rank)** — The fastest signal of competitive change. A BSR spike means the competitor is gaining sales velocity. A BSR decline means they are losing momentum. Track BSR daily. Flag changes over 20% in either direction.

**Price** — The most actionable signal. A competitor's price drop is your cue to decide: match, hold, or reposition. A price increase (without BSR decline) means they have pricing power — understand why.

**Review count and rating** — Slow-moving but high-impact. A competitor gaining 50 reviews in a month is running an aggressive launch strategy. A competitor's rating dropping from 4.3 to 4.0 means they have a product quality problem — which is your opportunity.

**Keyword ranking changes** — Which keywords did the competitor gain or lose ranking on this week? If they gained ranking on 5 keywords that you do not target — those keywords belong on your radar.

```bash
# competitor monitoring via sorftime-seller-agent:
# product_detail → current price, BSR, review count, rating
# product_trend → historical trend for all metrics
# product_traffic_terms → keyword ranking changes
```

![Example output: competitor product trend — 12-month sales, price, and BSR history used for change detection.](https://cdn.jsdelivr.net/gh/Tomi431/Tomi@main/docs/assets/images/A9.png)
*Example output: competitor product trend — 12-month sales, price, and BSR history used for change detection.*


## Setting Up the Monitor

Pick 5-10 competitors. These should be the ASINs that consistently appear next to yours in search results — not the category leader who is doing 10× your volume. Monitor your direct competitive set.

Set thresholds that distinguish signal from noise. BSR: ±20% change from 7-day average. Price: ±5% change. Review count: +10 new reviews in a week. Rating: ±0.2 change. Flag anything that crosses a threshold. Ignore everything else — noise is the enemy of actionable monitoring.

## The Weekly Competitive Brief

Every Monday morning, your monitor produces a short brief: which competitors changed, what changed, and whether it matters.

A BSR spike without a price change means the competitor launched a successful ad campaign or got a PR boost — watch if it sustains. A price drop without a BSR improvement means the market rejected the new price — they will probably revert. A rating drop with new negative reviews means a product defect — check if it is a category-wide supplier issue that might affect your product too.

Competitor monitoring is not about copying what your competitors do. It is about knowing what is happening in your market so you can make informed decisions — instead of finding out two weeks later in your sales report.

---

*Try it yourself: `git clone https://github.com/DannylydST/sorftime-seller-agent` → `python3 scripts/install.py` → get your key at [open-intl.sorftime.com](https://open-intl.sorftime.com)*
