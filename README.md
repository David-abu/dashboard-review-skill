# Dashboard Review Skill

A structured framework for reviewing dashboards, reports, and data visualizations with the depth of a senior data analyst.

Reviews are calibrated to the dashboard's actual audience, such as executives, department heads, operations managers, analysts, frontline workers, or external stakeholders. The skill does not assume every dashboard is built for a CEO.

## What It Does

When you share a dashboard as an image, PDF, screenshot, or text description, the framework produces a structured review covering:

- 6 scored dimensions: business question, domain knowledge, audience fit, data story, visual design, and actionability
- Internal consistency checks for arithmetic, totals, units, and deviation signs
- Time horizon checks for whether the data window supports the claims
- 5+ analytical challenge questions framed for the actual audience
- 3+ missing analyses a domain expert would run next
- Top 3 prioritized recommendations
- One specific thing done well

## Try It

| Option | Best for | Cost model |
|--------|----------|------------|
| `SKILL.md` | First option for ChatGPT, Copilot, Codex, Claude, Gemini, or other AI users | Free or included for many users through their existing AI tool |
| [Live Prompt Builder](https://david-abu.github.io/dashboard-review-skill/) | Anyone who wants a copy-ready review prompt | Free, no API key |
| `dashboard-review.skill` | Claude users who want the skill installed | Uses the user's Claude plan |

## Free Public App

The GitHub Pages app is a prompt builder. It does not call Anthropic, OpenAI, or any other model API.

How it works:

1. Add dashboard context and optionally upload a screenshot.
2. The app builds a structured review prompt in your browser.
3. Copy the prompt into ChatGPT, Microsoft Copilot, Claude, Gemini, Codex, or another AI assistant.
4. If you uploaded a screenshot, attach the same image in that AI chat.

This keeps the public app free to host and free to use. No visitor data or images are sent anywhere by the page.

## Install As A Claude Skill

1. Download `dashboard-review.skill` from the repo or Releases page.
2. In Claude.ai, go to Settings -> Connectors -> Customize -> Skills -> Plus Sign (+) -> Upload Skill.
3. Upload the `.skill` file.
4. Share a dashboard screenshot or describe a dashboard and ask Claude to review it.

To confirm it is working, start a new Claude conversation and ask:

```text
is the dashboard review skill active?
```

## Use With ChatGPT, Copilot, Codex, Or Claude

Try `SKILL.md` first. It is the most portable version of the framework and works with tools many people already have access to, including ChatGPT, Microsoft Copilot, Codex, Claude, Gemini, and other AI assistants.

Paste `SKILL.md` into the model's instructions, add it as a local Codex skill, or use it as the system/developer prompt in an app.

This repo also includes `agents/openai.yaml` so Codex-style skill lists can display the skill cleanly.

## How To Trigger A Review

Once installed or pasted into your AI tool, ask things like:

```text
Review my dashboard
Critique this Power BI report
Give feedback on this Tableau viz
What's wrong with my dashboard?
Score my dashboard
Help me improve this report
```

Or upload a dashboard image/PDF and ask for a review.

## Review Framework Overview

### Step 0: Identify The Audience

The skill first determines who the dashboard was built for, then applies all scoring criteria through that lens.

| Audience | Primary need | Review time |
|---|---|---|
| C-Suite / Executive | Situation awareness, go/no-go | 3-5 min |
| Department Head / Director | Performance management | 5-10 min |
| Operations Manager | Task prioritization | 10-20 min |
| Analyst / Data Team | Pattern investigation | As needed |
| Field / Frontline Worker | Next action | 30 sec |
| External Stakeholder | Confidence, accountability | 2-3 min |

### 6 Dimensions Scored

| # | Dimension | What It Tests |
|---|---|---|
| 1 | Business Question & Purpose | Is there a clear question? Does every page serve it? |
| 2 | Domain Knowledge | Are these the right metrics for this domain? |
| 3 | Audience Fit & Interactivity | Is the depth, detail, and interactivity right for this audience? |
| 4 | Data Accuracy, Story & Definitions | Do the numbers add up? Are there context and benchmarks? |
| 5 | Visual Design, Chart Choice & Consistency | Right charts? Top-left priority? Consistent across pages? |
| 6 | Actionability & The So What | Does every pattern lead to consequence and action? |

### Three Checks Many Reviews Miss

1. Internal consistency: add up segment totals and compare them with the stated overall.
2. Time horizon adequacy: check whether the date range is long enough for the claims.
3. Deviation sign consistency: make sure positive and negative values mean the same thing everywhere.

## Repo Structure

```text
dashboard-review-skill/
├── README.md                 # Project overview and setup notes
├── SKILL.md                  # First-choice instructions for ChatGPT, Copilot, Codex, Claude, and other AI tools
├── dashboard-review.skill    # Packaged Claude skill archive
├── agents/
│   └── openai.yaml           # ChatGPT/Codex skill metadata
├── docs/
│   └── index.html            # Free GitHub Pages prompt builder
└── .gitignore                # Local tooling ignores
```

## Roadmap

- Refresh the packaged `dashboard-review.skill` after source updates.
- Add example review prompts and outputs.
- Add a short guide for installing `SKILL.md` as a local Codex skill.

## License

MIT. Use freely, adapt as needed, attribution appreciated.

Built by David Abu and shared with the Data Community Africa community.
