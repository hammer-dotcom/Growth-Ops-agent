# Growth Ops Agents

An AI-powered SEO operations system built on Claude Code. Specialized agents analyze,
prioritize, optimize, validate, and report on SEO performance using real data.

## What it does

- Analyzes SEO performance data to find high-impact opportunities
- Audits technical SEO (crawlability, indexing, Core Web Vitals, structured data)
- Analyzes competitors and generates actionable SEO briefs
- Creates content strategy and structured content briefs
- Writes SEO/AEO/GEO-optimized content
- Optimizes existing content based on performance data
- Validates quality, facts, and tone before publishing
- Generates recurring performance reports (n8n-ready for scheduling)
- Prioritizes everything into a structured execution backlog

## Architecture

```
agents/          -> 9 specialized agents, each owns one responsibility
skills/          -> 11 focused skills, agents decide when to use which
company-setup/   -> your company config, filled in by /setup
workflows/       -> all outputs, organized by type (n8n-ready)
commands/        -> slash commands (/setup)
```

Agents decide WHEN to act. Skills define HOW. Workflows hold outputs.
CLAUDE.md is the constitution: rules every agent follows.

## Setup

```
/setup
```

Interviews you about your site, tools, brand, and strategy. Fills in `company-setup/`
and unlocks all agents. Nothing runs against placeholder data.

## Quick start

After setup:
- "Run an SEO analysis on my site"
- "Audit technical SEO for [url]"
- "Analyze competitors for [keyword]"
- "Create a content brief for [topic]"
- "Generate a weekly SEO report"

## Tools this system works with

All optional. Everything works with free built-in web search by default.

- **Google Search Console** (free, your own ranking data)
- **DataForSEO** (cheap, pay-per-call keyword and SERP data)
- **GA4** (free, traffic and conversion data)
- **Firecrawl / Apify** (competitor page scraping)
- **Airtable / Google Sheets** (project tracking)

## n8n-ready

The reporting agent's output format is designed for automated pickup. Add an n8n
workflow later to trigger weekly reports and forward to Slack or email. See
`docs/n8n-integration.md` for the pattern.

## Related

This system monitors and optimizes. For content production (keyword to publish-ready
draft), see the companion repo: [Content Engine](https://github.com/hammer-dotcom/Content-Engine).
