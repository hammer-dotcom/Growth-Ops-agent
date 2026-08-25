# n8n Integration (future step)

This system is designed manual-first, n8n-ready later. Here is the pattern for when
you are ready to add scheduling.

## What to automate

The reporting-agent is the primary candidate. It produces a structured markdown report
in `/workflows/reports/` with consistent headers and a parseable KPI table.

## n8n workflow pattern

1. **Trigger**: cron schedule (e.g. every Monday 9am)
2. **Execute**: call Claude API with the reporting-agent prompt and your company context
3. **Read output**: parse the report file from `/workflows/reports/`
4. **Deliver**: send to Slack channel, email, or Notion page

## Why not automate everything?

Most agents benefit from human judgment at the input stage (which URL to audit, which
keyword to target). The reporting agent is the exception: its input is "whatever
happened this week in GSC/GA4," which does not require a human decision.

Automate the reporting loop first. Add others only when you find yourself running
the same command with the same inputs on a regular cadence.
