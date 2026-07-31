---
layout: home
title: "Seller MCP Playbook"
---

<div class="hero">
  <h1>Seller MCP Playbook</h1>
  <p>Marketplace intelligence workflows for Amazon, Walmart, TikTok Shop, Shopee, TEMU, and 1688 sellers — powered by MCP and AI agents.</p>
</div>

## Latest Articles

<div class="article-grid">
{% for post in site.posts reversed %}
  <a href="{{ post.url | relative_url }}" class="article-card">
    <div class="card-meta">{{ forloop.rindex | prepend: '0' | slice: -2, 2 }} · {{ post.tags | join: ' · ' }}</div>
    <h3>{{ post.title }}</h3>
    <p>{{ post.excerpt | strip_html | truncatewords: 22 }}</p>
  </a>
{% endfor %}
</div>

## Quick Start

1. **Install the MCP server**
   ```bash
   git clone https://github.com/DannylydST/sorftime-seller-agent && cd sorftime-seller-agent && python3 scripts/install.py
   ```
2. **Get a free MCP key** at [open-intl.sorftime.com](https://open-intl.sorftime.com)
3. **Open any article above**, copy the prompt, and paste it into your AI agent

Works with Claude Code, Codex CLI, Cursor, OpenClaw, Hermes, Pi, or any MCP-compatible agent.

---

*Built for sellers. By sellers.*

<style>
.hero {
  background: linear-gradient(135deg, #155799 0%, #159957 100%);
  color: #fff;
  padding: 3rem 1.5rem;
  margin: -2rem -2rem 2rem -2rem;
  text-align: center;
}
.hero h1 {
  font-size: 2.4rem;
  margin: 0 0 0.75rem 0;
  font-weight: 700;
  letter-spacing: -0.02em;
}
.hero p {
  font-size: 1.15rem;
  margin: 0 auto;
  opacity: 0.95;
  max-width: 640px;
}
.article-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1rem;
  margin: 1.5rem 0;
}
.article-card {
  display: block;
  text-decoration: none;
  color: inherit;
  border: 1px solid #e1e4e8;
  border-radius: 8px;
  padding: 1.25rem;
  background: #fff;
  box-shadow: 0 1px 3px rgba(0,0,0,0.04);
  transition: box-shadow 0.2s, transform 0.2s;
}
.article-card:hover {
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  transform: translateY(-2px);
}
.article-card h3 {
  font-size: 1.05rem;
  margin: 0 0 0.5rem 0;
  color: #0366d6;
  line-height: 1.35;
}
.article-card p {
  font-size: 0.9rem;
  color: #586069;
  margin: 0;
  line-height: 1.5;
}
.card-meta {
  font-size: 0.8rem;
  color: #586069;
  margin-bottom: 0.5rem;
  text-transform: capitalize;
}
</style>
