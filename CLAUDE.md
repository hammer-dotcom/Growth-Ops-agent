# CLAUDE.md

This file tells Claude Code how to behave inside this repository. Read it at the start
of every session and follow it.

## What this repository is

An AI-powered SEO operations system. It uses specialized agents and focused skills to
analyze, prioritize, optimize, validate, and report on SEO performance using real data.

Each agent owns a specific responsibility. Skills define how execution happens. Agents
decide when to use which skill. Workflows hold all outputs.

## RULE 1: The setup gate

This repo ships with placeholder company config. Before running any agent or skill:

1. Check `company-setup/` for `{{REPLACE_ME}}` tokens or `<!-- SETUP_INCOMPLETE -->` lines.
2. If found, STOP. Tell the user:

   > This system needs to know about your site, tools, and brand before it can run.
   > Type `/setup` and I will walk you through it. Takes a few minutes.

3. Only proceed once every file in `company-setup/` is clean.

Once setup is confirmed complete, retire this gate check from all agent files and delete
this rule so future runs do not waste tokens re-checking.

## RULE 2: Read company context before acting

Every agent must read the relevant files in `company-setup/` before doing its work:

- `company-setup/site-profile.md` -- domain, CMS, business model, target market
- `company-setup/seo-strategy.md` -- priority topics, target segments, content goals
- `company-setup/tone-of-voice.md` -- writing style, brand rules, words to avoid
- `company-setup/data-sources.md` -- which tools are connected (GSC, DataForSEO, GA4, etc.)
- `company-setup/tracking-setup.md` -- Airtable/sheet config for project tracking

## RULE 3: Data sources are toggleable

`company-setup/data-sources.md` lists connected tools. Default is built-in web search.
If a tool is `on`, prefer it. If `off`, fall back to web search. Never invent metrics.

## RULE 4: Save every output to /workflows

Every agent writes its output to a dated file in `/workflows`. This is what makes the
system auditable and n8n-ready later. File naming: `{agent}-{slug}-{YYYY-MM-DD}.md`.

## RULE 5: Do not duplicate responsibilities

Each agent owns one job. If an agent needs another agent's output, it reads the file
from `/workflows`, it does not redo the work. Skills are shared capabilities, agents are
not.

## Execution flow (default)

When asked to run a full analysis:

1. seo-analyst
2. seo-technical-analyst
3. competitor-analyst
4. content-strategist
5. project-manager
6. content-writer (if new content needed)
7. content-optimizer (if refresh needed)
8. content-evaluator (before publishing)
9. reporting-agent (summary)

Not every run needs every agent. Use judgment. A "check my technical SEO" request
only needs seo-technical-analyst.

## Writing standards

- Never use em dashes. Use commas, full stops, or colons.
- Never invent statistics, sources, or competitor claims.
- Cite real, retrievable sources only.
- Prefer structured output (tables, JSON, prioritized lists) over prose.
- Every recommendation must tie to observed data.

## Make it yours

Fork this repo. Add agents, remove skills, change the flow. If the user asks to modify
something, edit the relevant file rather than working around it.
