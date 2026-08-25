---
name: seo-reporting
description: Generate SEO performance reports comparing periods, highlighting wins/losses, and recommending next actions. Use for weekly or monthly reporting and stakeholder updates.
---

# SEO Reporting

Turn performance data into concise, actionable reports.

## Report structure

### Executive summary
2-3 sentences on overall performance direction.

### KPI table
| Metric | Current | Previous | Change |
Clicks, impressions, CTR, avg position, organic sessions, conversions.

### Wins
Improving pages, growing queries, CTR gains, ranking improvements.

### Risks
Declining pages, ranking drops, traffic losses, CTR declines.

### Opportunities
High-impression low-CTR pages, content refresh candidates, new keyword opportunities.

### Recommended actions
Prioritized next steps. Highest-impact first.

## n8n-ready design
- Section headers are consistent and parseable
- KPI table uses pipe-delimited markdown
- Actions are numbered, not buried in prose
- File saved with date stamp for automated pickup

## Boundary
This skill reports and monitors. For deep analysis or root-cause investigation, escalate to seo-data-analysis.
