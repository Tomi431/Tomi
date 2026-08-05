---
layout: default
title: "Shopee Cross-Border Sourcing: From 1688 to Southeast Asia"
date: 2026-08-04
tags: ["Shopee", 1688, "Cross-Border", "Sourcing"]
---

Selling on Shopee from outside Southeast Asia is viable. The cross-border logistics program handles warehousing, customs, and last-mile delivery. You ship inventory to Shopee's China warehouse. Shopee handles everything from there to the customer in Vietnam, Thailand, or the Philippines.

![Shopee Cross-Border Sourcing: From 1688 to Southeast Asia](https://cdn.jsdelivr.net/gh/Tomi431/Tomi@main/docs/assets/images/C5.png)
*Screenshot: Shopee Cross-Border Sourcing: From 1688 to Southeast Asia*


The real challenge is not logistics — it is knowing which products work in markets you cannot visit.

## The Cross-Border Sourcing Stack

**Step 1**: Identify what sells on Shopee in your target country. Pull category reports. Filter for products with strong sales velocity (>200 units/month) and moderate review counts (<100). These are products with validated demand and low competitive moats.

```bash
# shopee_category_request → top products with sales, price, reviews
# shopee_product_request → detail on individual products
```

**Step 2**: Cross-reference on 1688. For each candidate product, search 1688 by the core product name in Chinese. Compare the 1688 ex-factory price against the Shopee retail price. The gap needs to cover cross-border logistics, Shopee fees, and your margin.

**Step 3**: Check Amazon for the same product. If it sells on Amazon at a higher price than Shopee, you have a multi-platform opportunity. If it only exists on Shopee, you have a platform-specific opportunity. Either is valid — the key is knowing which one you are chasing.

## What Works Best

Lightweight products under 1kg with standardized packaging — kitchen tools, phone accessories, basic stationery, simple fitness gear, home organization. These categories have low logistics costs and low return rates. Avoid: heavy goods, fragile items, fashion with sizing, regulated products.

---

*Try it yourself: `git clone https://github.com/DannylydST/sorftime-seller-agent` → `python3 scripts/install.py` → get your key at [open-intl.sorftime.com](https://open-intl.sorftime.com)*
