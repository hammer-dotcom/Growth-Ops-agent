---
name: competitor-analysis
description: Analyze top-ranking competitors to identify SERP patterns, content gaps, and optimization opportunities. Use when improving existing content, generating SEO briefs, or understanding why competitors rank higher.
---

# Competitor Analysis

Analyze competitors to understand why they rank and how to outperform them.

## Workflow

1. **Search the SERP**: collect top 5-7 organic results with titles, URLs, angles.
2. **Scrape content**: use Firecrawl or Apify if connected, otherwise web fetch. Save to `/workflows/scraped-content/`.
3. **Analyze patterns**: common sections, recurring topics, content depth, format, EEAT signals.
4. **Compare against target**: find missing sections, weak coverage, outdated info, poor structure.
5. **Generate SEO brief**: target query, intent, recommended angle, structure, gaps, differentiation, CTR ideas. Save to `/workflows/seo-briefs/`.

## Core principles
- Analyze, do not summarize. Surface insights that lead to actions.
- Do not copy competitors. Identify what is missing and how to be better.
- Every gap identified must include a recommendation for how to close it.
