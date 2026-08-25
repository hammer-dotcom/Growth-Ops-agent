---
description: Configure the system for your company. Walks through every placeholder and unlocks all agents. Usage: /setup
---

You are running guided setup for this SEO operations system. Your job is to fill in
every placeholder in `company-setup/` with real company information and unlock the agents.

Be direct and practical. The user may be a solo marketer or a team lead.

## Core principle: documents first, questions second

Before asking questions, ask the user if they already have: a brand guide, tone doc,
SEO strategy document, ICP or persona file, or a list of competitors. If they do, read
those first, extract what you can, and only ask about gaps.

## Step 1: Site profile

Fill in `company-setup/site-profile.md`:
- Company name and domain
- CMS (WordPress, Webflow, Shopify, other)
- Business model (B2B SaaS, ecommerce, agency, publisher, other)
- Target market and geography
- Primary competitors (3-5 domains)

## Step 2: SEO strategy

Fill in `company-setup/seo-strategy.md`:
- Priority topic clusters or categories
- Target audience segments
- Content goals (traffic, leads, citations, authority)
- Funnel focus (top, mid, bottom, or balanced)
- Any pages or sections that are off-limits for changes

## Step 3: Tone of voice

Fill in `company-setup/tone-of-voice.md`:
- Brand voice in 3 words
- Tone description
- Words or phrases to avoid
- Formatting rules (em dash ban is default)

If the user can share 3-5 articles that represent their best writing, read them and
extract the voice patterns (how they open, sentence rhythm, evidence usage, structure).

## Step 4: Data sources

Fill in `company-setup/data-sources.md`:
- Which MCP connectors are available (Google Search Console, DataForSEO, GA4, Firecrawl, Apify)
- For each: set to `on` or `off`
- Explain that everything works with free web search by default, connectors make it better

## Step 5: Tracking setup

Fill in `company-setup/tracking-setup.md`:
- Does the user have Airtable, Google Sheets, or Notion for project tracking?
- If yes, note the workspace. If no, set to `local-files-only`.

## Step 6: Remove markers and confirm

Remove all `<!-- SETUP_INCOMPLETE -->` and `{{REPLACE_ME}}` tokens. Tell the user setup
is complete and show them their first commands:

> You are ready. Try:
> "Run an SEO analysis on my site"
> "Audit technical SEO for [url]"
> "Analyze competitors for [keyword]"
> "Create a content brief for [topic]"
> "Generate a weekly SEO report"
