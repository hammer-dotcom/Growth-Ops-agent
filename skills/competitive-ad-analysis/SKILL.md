---
name: competitive-ad-analysis
description: Track and classify competitor advertising creative from Meta Ad Library and LinkedIn Ad Library. Identify durable ads, new creative, messaging angles, and positioning gaps. Use when the user wants competitive ad intelligence, ad creative monitoring, or wants to understand what competitors are saying in paid channels.
---

# Competitive Ad Analysis

Monitor what competitors are saying in paid channels and surface the patterns
that matter for your own positioning.

## Data sources
- Meta Ad Library (public, free, searchable by advertiser name)
- LinkedIn Ad Library (public, free, searchable by advertiser name)
- Apify MCP (if connected) for automated scraping
- Web fetch as fallback

## What to capture per ad
- Advertiser name
- Platform (Meta or LinkedIn)
- First seen date (when you first found it)
- Headline / primary text
- Target audience (inferred from copy and targeting signals)
- Angle: the core argument (outcome/ROI, speed-to-value, compliance/security,
  cost-saving, authority/thought-leadership, product-feature, social-proof,
  seasonal urgency)
- Funnel stage: top, middle, bottom
- CTA type: book-a-demo, free-trial, gated-report, sign-up, learn-more
- Tone: confident, plain, urgent, institutional, research-led, consultative
- Proof shown: customer count, benchmark data, certification, case study, none
- Runtime estimate: days since first seen (proxy for performance)

## Classification guidelines

**Angle classification** (pick the primary argument, not a feature list):
- outcome/ROI: "cut planning time 60%", "save 10 hours/week"
- speed-to-value: "set up in a day", "ship weekly"
- compliance/security: "SOC 2", "auditable", "enterprise-grade"
- cost-saving: "cut admin load", "replace 3 tools"
- authority/thought-leadership: benchmark data, survey results, research
- product-feature: "one platform for X, Y, Z"
- social-proof: "used by 800,000 teams"
- seasonal urgency: "Q1 planning starts in 6 weeks"

**Runtime as a performance proxy**:
21+ days = earned its keep. Nobody keeps paying for creative that does not convert.
7-20 days = too early to call.
Under 7 days = new, watch next week.

## Report structure

### The read
3-4 bullets summarizing what matters this week. Editorial, pattern-level,
not per-ad. What shifted, what is new, what your brand should watch.

### Ads that have earned their keep
Long-running ads (21+ days). For each: platform icon, angle, CTA, runtime,
headline, advertiser, target audience, proof shown, one-line take.

### New this window
First seen since last run, newest first. Same format as above.

### Angle mix table
All live creative, per advertiser, grouped by angle. Gaps here are openings.

### Sources and disclaimers
Collection date/time, platforms checked, note that runtime is proxy not spend,
classification is by LLM.

## Output
Save to `/workflows/ad-intel-reports/ad-intel-{YYYY-MM-DD}.md`.
