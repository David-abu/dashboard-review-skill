# Dashboard Review Skill for Claude

A structured framework for reviewing dashboards and data reports with the depth and rigour of a senior data analyst — packaged as a Claude skill you can install and share.

Reviews are always calibrated to the dashboard's **actual audience** (executive, operations, analyst, field worker, etc.) — never assumed to be for a CEO by default.

---

## What This Skill Does

When you share a dashboard — as an image, PDF, screenshot, or text description — this skill produces a full structured review covering:

- **6 scored dimensions**: Business Question, Domain Knowledge, Audience Fit, Data Story, Visual Design, Actionability
- **Internal consistency checks**: Does the arithmetic add up? Are deviation signs correct?
- **Time horizon adequacy**: Is the data window sufficient for the claims being made?
- **5+ analytical challenge questions** framed for the specific audience
- **3+ missing analyses** a domain expert would run immediately
- **Top 3 prioritised recommendations** — specific and actionable
- **One thing done well** — genuine, specific praise

---

## Quick Start

### Option 1 — Install as a Claude Skill (recommended)

1. Download `dashboard-review.skill` from the [Releases](../../releases) page
2. In Claude.ai, go to **Settings → Skills → Upload Skill**
3. Upload the `.skill` file
4. Share a dashboard screenshot or describe a dashboard and ask Claude to review it

### Option 2 — Copy the Prompt Directly

Copy the contents of `dashboard-review/SKILL.md` and paste it into any Claude conversation as your system prompt or instruction block.

### Option 3 — Use the Prompt in Your Own Tools

The skill is plain Markdown. Drop it into any LLM pipeline that supports system prompts.

---

## How to Trigger a Review

Once installed, any of these prompts will trigger the skill:

```
Review my dashboard
Critique this Power BI report
Give feedback on this Tableau viz
What's wrong with my dashboard?
Score my dashboard
Help me improve this report
```

Or upload a dashboard image/PDF and ask Claude to review it.

---

## Review Framework Overview

### Step 0 — Identify the Audience
The skill first determines who the dashboard was built for, then applies all scoring criteria through that lens.

| Audience | Primary need | Review time |
|---|---|---|
| C-Suite / Executive | Situation awareness, go/no-go | 3–5 min |
| Department Head / Director | Performance management | 5–10 min |
| Operations Manager | Task prioritisation | 10–20 min |
| Analyst / Data Team | Pattern investigation | As needed |
| Field / Frontline Worker | Next action | 30 sec |
| External Stakeholder | Confidence, accountability | 2–3 min |

### 6 Dimensions Scored

| # | Dimension | What It Tests |
|---|---|---|
| 1 | Business Question & Purpose | Is there a clear question? Does every page serve it? |
| 2 | Domain Knowledge | Are these the right metrics for this domain? |
| 3 | Audience Fit & Interactivity | Is the depth, detail, and interactivity right for this audience? |
| 4 | Data Accuracy, Story & Definitions | Do the numbers add up? Are there context and benchmarks? |
| 5 | Visual Design, Chart Choice & Consistency | Right charts? Top-left priority? Consistent across pages? |
| 6 | Actionability & The So What | Every pattern → consequence → action for this audience |

### Three Checks Most Reviewers Miss

These were discovered by comparing AI reviews against expert human reviews of the same dashboards:

1. **Internal consistency** — add up the segment totals; do they match the stated overall?
2. **Time horizon adequacy** — is the date range sufficient for the trend claims being made?
3. **Deviation sign consistency** — is positive/negative used consistently throughout?

---

## Repo Structure

```
dashboard-review-skill/
├── README.md                          ← You are here
├── dashboard-review/
│   ├── SKILL.md                       ← The Claude skill (install this)
│   ├── references/
│   │   └── methodology.md             ← Full reference list + version history
│   └── examples/
│       └── construction-dashboard-review.md   ← Example of a full review output
└── dashboard-review.skill             ← Packaged skill file for one-click install
```

---

## Example Output

See [`dashboard-review/examples/construction-dashboard-review.md`](dashboard-review/examples/construction-dashboard-review.md) for a complete review of a real 4-tab Power BI construction management dashboard — including internal consistency findings, challenge questions, missing analysis, and scored dimensions.

---

## Training Sources

This skill's evaluation criteria are grounded in 14 sources:

**Books**: Knaflic · Few (×2) · Tufte (×2) · Berinato · Healy · Yau · Wexler/Shaffer/Cotgreave · Kleppmann · Akidau et al. · Deutsch

**Platform docs**: Microsoft Learn (Design Effective Reports in Power BI) · Tableau Help (Dashboard Best Practices)

Full details in [`dashboard-review/references/methodology.md`](dashboard-review/references/methodology.md).

---

## Version History

| Version | Summary |
|---|---|
| v1–v4 | Initial framework, book training, image support, challenge questions |
| v5 | Three expert-review fixes: internal consistency, time horizon, deviation signs |
| v6 | Microsoft Learn + Tableau sources: top-left rule, visual count, interactivity, accessibility |
| v6.1 | **Removed CEO/executive bias.** Step 0 audience identification now drives all scoring. |

---

## Contributing

Issues, improvements, and new example reviews are welcome. Open a PR or file an issue.

Built by **David Abu** · Shared with the [Nigerians in Seattle](https://www.meetup.com/nigerians-in-seattle/) and [Data Community Africa](https://www.datacommunityafrica.org/) communities.

---

## License

MIT — use freely, adapt as needed, attribution appreciated.
