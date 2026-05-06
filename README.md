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

## Choose The Right Tool

| Option | Best for | Cost model |
|--------|----------|------------|
| ChatGPT Project + `CHATGPT_PROJECT_INSTRUCTIONS.md` | ChatGPT users who want a reusable dashboard review workspace | Free for ChatGPT users with Projects access |
| [Live Prompt Builder](https://david-abu.github.io/dashboard-review-skill/) | Anyone who wants a copy-ready prompt without setup | Free, no API key, no backend |
| `SKILL.md` pasted into any AI chat | Copilot, Gemini, Codex, Claude, or any assistant that accepts instructions | Free or included through the user's existing AI tool |
| `dashboard-review.skill` | Claude users who want Claude's `/dashboard-review` skill experience | Uses the user's Claude plan |

Recommended free path:

1. If you use ChatGPT often, create a ChatGPT Project and add `CHATGPT_PROJECT_INSTRUCTIONS.md` as the project instructions.
2. If you only need a quick review, use the Live Prompt Builder and paste the generated prompt into your AI chat.
3. If you use Claude and have Skills enabled, install `dashboard-review.skill`.
4. If you use Copilot, Gemini, Codex, or another assistant, paste `SKILL.md` as the instruction prompt.

This repo does not require a paid OpenAI API key, Anthropic API key, Cloudflare Worker, or Custom GPT builder subscription.

## Free ChatGPT Setup: Project Instructions

Use this when you want a reusable ChatGPT workspace for dashboard reviews.

Use `CHATGPT_PROJECT_INSTRUCTIONS.md` for ChatGPT Projects. It is a compact v3 version of the skill, kept around 6,000 characters so it fits ChatGPT's project instruction limit.

1. Open ChatGPT and sign in.
2. Create a new Project.
3. Name the project:

```text
Dashboard Review
```

4. Inside the project, click the three-dot menu (`...`) in the top-right corner.
5. Open the project instructions or settings from that menu.
6. Copy the full contents of `CHATGPT_PROJECT_INSTRUCTIONS.md` from this repo.
7. Paste it into the Project instructions.
8. Save the project.
9. Start a new chat inside that project.
10. Upload a dashboard screenshot, PDF, or describe the dashboard.
11. Ask:

```text
Review this dashboard.
```

Use this option when:

- You want ChatGPT to remember the review framework across multiple dashboard review chats.
- You review dashboards often.
- You do not want to create or pay for a Custom GPT.
- You want the cleanest free ChatGPT workflow.

Note: ChatGPT does not currently support custom user slash commands like Claude's `/dashboard-review`. A ChatGPT Project is the closest free ChatGPT-native replacement.

## Free Public App

The GitHub Pages app is a prompt builder. It does not call Anthropic, OpenAI, or any other model API.

How it works:

1. Add dashboard context and optionally upload a screenshot.
2. The app builds a structured review prompt in your browser.
3. Copy the prompt into ChatGPT, Microsoft Copilot, Claude, Gemini, Codex, or another AI assistant.
4. If you uploaded a screenshot, attach the same image in that AI chat.

This keeps the public app free to host and free to use. No visitor data or images are sent anywhere by the page.

Use this option when:

- You want the fastest no-setup workflow.
- You are sharing the tool with people who may use different AI assistants.
- You want a structured prompt that works in ChatGPT, Microsoft Copilot, Claude, Gemini, Codex, or another AI tool.
- You do not want users to install anything.

## Use With Copilot, Gemini, Codex, Or Other AI Tools

Use `SKILL.md` when the AI tool lets you paste custom instructions, system prompts, or reusable context.

1. Open `SKILL.md`.
2. Copy the full file.
3. Paste it into the AI tool's instructions or into the start of a new chat.
4. Add:

```text
Use these instructions as your dashboard review framework.
```

5. Upload or describe the dashboard.
6. Ask for a review.

## Install As A Claude Skill

1. Download `dashboard-review.skill` from the repo or Releases page.
2. In Claude.ai, go to Settings -> Connectors -> Customize -> Skills -> Plus Sign (+) -> Upload Skill.
3. Upload the `.skill` file.
4. In Claude, type:

```text
/dashboard-review
```

5. Share a dashboard screenshot or describe a dashboard and ask Claude to review it.

To confirm it is working, start a new Claude conversation and ask:

```text
is the dashboard review skill active?
```

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
|-- README.md                 # Project overview and setup notes
|-- SKILL.md                  # Full portable skill instructions for Copilot, Codex, Claude, and other AI tools
|-- CHATGPT_PROJECT_INSTRUCTIONS.md # Compact ChatGPT Project version around 6,000 characters
|-- dashboard-review.skill    # Packaged Claude skill archive
|-- agents/
|   `-- openai.yaml           # ChatGPT/Codex skill metadata
|-- docs/
|   `-- index.html            # Free GitHub Pages prompt builder
`-- .gitignore                # Local tooling ignores
```

## Roadmap

- Refresh the packaged `dashboard-review.skill` after source updates.
- Add example review prompts and outputs.
- Add screenshots for the ChatGPT Project setup flow.
- Add a short guide for installing `SKILL.md` as a local Codex skill.

## License

MIT. Use freely, adapt as needed, attribution appreciated.

Built by David Abu and shared with the Data Community Africa community.
