---
name: dashboard-review
description: >
  Use this skill whenever a user wants to review, critique, evaluate, or give feedback on a
  dashboard, report, or data visualization. Triggers include: uploading a dashboard screenshot
  or PDF, saying "review my dashboard", "critique this report", "give feedback on this viz",
  "what's wrong with my dashboard", "score my dashboard", "help me improve this Power BI /
  Tableau / Looker report", or any request involving dashboard quality, design, or analytical
  depth. Also use when a user describes a dashboard in text and wants structured feedback.
  This skill produces a full structured review across 6 dimensions with scores, challenge
  questions, missing analysis, and prioritised recommendations — always calibrated to the
  actual audience the dashboard was built for.
---

# Dashboard Review Skill

A structured framework for reviewing dashboards and data reports with the depth and rigour
of a senior data analyst. Reviews are always calibrated to the dashboard's actual audience —
executive, operations, analyst, or other — not assumed to be for a CEO by default.

---

## Activation Confirmation

When a user says any of the following:
- "dashboard review skill"
- "is the dashboard review skill active?"
- "what skills do you have?"
- "are you ready to review a dashboard?"

Respond with:

> ✅ **Dashboard Review Skill is active.**
>
> Share a dashboard — image, PDF, screenshot, or text description — and I'll give you a full structured review across 6 dimensions:
>
> 1. Business Question & Purpose
> 2. Domain Knowledge & Business Logic
> 3. Audience Fit & Interactivity
> 4. Data Accuracy, Story & Definitions
> 5. Visual Design, Chart Choice & Consistency
> 6. Actionability, Insight & The So What
>
> Every review includes scores, internal consistency checks, challenge questions, missing analysis, and prioritised recommendations — all calibrated to your dashboard's actual audience, not assumed to be for a CEO.
>
> **To start:** upload a screenshot or describe your dashboard.

---

## Training Sources

This skill's review criteria are grounded in:
- *Storytelling with Data* — Cole Knaflic
- *Big Book of Dashboards* — Wexler, Shaffer, Cotgreave
- *Information Dashboard Design* — Stephen Few
- *Show Me the Numbers* — Stephen Few
- *The Visual Display of Quantitative Information* — Edward Tufte
- *Good Charts* — Scott Berinato
- *Data Visualization: A Practical Introduction* — Kieran Healy
- *Data Points* — Nathan Yau
- Microsoft Learn: Design Effective Reports in Power BI (4-module path)
- Tableau Help: Dashboard Best Practices & Create a Dashboard

For the full reference list and detailed methodology, see `references/methodology.md`.

---

## How to Use This Skill

When the user shares a dashboard (image, PDF, screenshot, or text description):

1. Work through Steps 0–4 in order
2. Never skip Step 0 — audience identification changes every scoring decision
3. Return output in the exact structured format defined in Step 4
4. Be specific — cite actual numbers and visuals from the dashboard, not generic advice

---

## STEP 0 — IDENTIFY THE AUDIENCE FIRST

Before anything else, determine who this dashboard is designed for.
Every dimension is judged through the lens of whether **this specific audience**
can do their job better because of this dashboard.

| Audience | Primary need | Appropriate depth | Review time |
|---|---|---|---|
| C-Suite / Executive | Situation awareness, go/no-go | Headline KPIs only | 3–5 min |
| Department Head / Director | Performance management | Summary + one breakdown level | 5–10 min |
| Operations Manager | Day-to-day prioritisation | Task-level detail, status tracking | 10–20 min |
| Analyst / Data Team | Pattern investigation | Full granularity, drill-through | As needed |
| Field / Frontline Worker | What do I do next | Single focused metric | 30 seconds |
| External Stakeholder / Client | Confidence, accountability | Curated highlights, no jargon | 2–3 min |

**Rules:**
- If the dashboard states the audience explicitly, use it
- If the purpose implies the audience (e.g. "CEO monthly review"), infer it
- If the audience is unclear, flag it as a finding — no defined audience means no design standard
- If the dashboard serves multiple audiences on one page, flag it — almost always a design failure

---

## STEP 1 — READ BEFORE JUDGE

Complete all four checks before scoring anything.

### 1a. Orient
- What business question is this answering?
- Who is the audience (from Step 0)?
- What domain — sales, finance, construction, HR, logistics, other?
- How many pages/tabs? What does each cover?

### 1b. Internal Consistency Check
- Add up all segment totals → do they match the stated overall total?
- If subtotals exceed the parent, flag immediately — data integrity failure
- Are deviation calculations correct? (Target − Actual = stated gap?)
- Are deviation signs consistent throughout? (positive = above target everywhere, or vice versa — never mixed)
- Do units match across related metrics? (person-days vs. persons vs. hours → flag if mixed)

### 1c. Time Horizon Adequacy
- Revenue/financial trends → need 12+ months for seasonality vs. noise
- Churn/retention → need 4–6 quarters before drawing conclusions
- Project progress → elapsed duration must be shown against total planned duration
- If the time window is too short for the claims being made, flag it

### 1d. Audience Scan Simulation
Simulate how the identified audience actually uses this dashboard:
- **Executive**: Can they get what they need in 3–5 minutes without scrolling or filtering?
- **Operations manager**: Can they immediately identify their top priority task?
- **Analyst**: Can they drill into anomalies without leaving the dashboard?
- **Field worker**: Is there a single unambiguous action signal?
- Does the most critical information for this audience appear where they will look first (top-left)?

---

## STEP 2 — EVALUATE ACROSS 6 DIMENSIONS

All dimensions must be evaluated through the lens of the identified audience.
The same feature can be a strength for one audience and a failure for another.

### DIMENSION 1 — Business Question & Purpose
- Is there a clearly stated or implied business question?
- Does every page/tab serve that question, or are there orphan pages?
- **Audience time test**: Given this audience, how long will they realistically spend here? Does the dashboard deliver its most important message within that window?
- **Top-left priority rule**: The most important finding for this audience should occupy or span the upper-left — matching the natural scan path of most viewers
- **Opening screen test**: Does the first thing this audience sees tell them what they need to know — or does it waste their time with navigation/branding?
- Is the most critical number/finding the most visually prominent element?

### DIMENSION 2 — Domain Knowledge & Business Logic
- Does the dashboard reflect genuine understanding of how this domain works?
- Are these the right metrics for the business problem, or vanity metrics?
- Are domain-specific metrics missing? (e.g., pipeline coverage ratio in sales, churn by segment in telecom, cost-at-completion in construction)
- Do metrics reflect cause-and-effect, not just outputs?
- Are thresholds domain-appropriate — does the dashboard treat a crisis as a crisis?

### DIMENSION 3 — Audience Fit & Interactivity
- **Depth calibration**: Is the level of detail right for this audience?
  - Executives: headline KPIs and trend direction — not raw tables or operational codes
  - Operations managers: task-level detail, status flags, ownership
  - Analysts: full granularity, slicers, ability to slice any dimension
  - Mixing all levels for a single audience is a design failure
- **Dashboard vs. Report**: A dashboard is an overview. Operational detail belongs in drill-through unless the audience is operational and detail is their primary need
- **Interactivity match**: Does the level of interactivity match what this audience needs?
  - Executives rarely filter — they need pre-filtered views
  - Analysts always filter — they need full slicer control
- **Navigation**: Are tabs/buttons clearly labelled? Can users always find their way back? Are transitions logical for this audience's workflow?
- **Display context**: Is this built for the screen this audience actually uses — boardroom TV, laptop, shop floor tablet, mobile?

### DIMENSION 4 — Data Accuracy, Story & Definitions
- **Facts vs. insights test**: Flag every KPI card showing a number without comparison context (no target, no prior period, no benchmark). A number alone is a fact. An insight needs at least two data points.
- Are metrics clearly defined in terms this audience understands?
- Are benchmarks, targets, or comparisons present and appropriate?
- Are calculations arithmetically correct? (Cross-check Step 1b)
- **Time horizon**: Is the window sufficient for the claims? (Cross-check Step 1c)
- Any data integrity issues — impossible values, suspicious uniformity, totals that don't reconcile?
- Is a "data as of" date shown on every page?

### DIMENSION 5 — Visual Design, Chart Choice & Consistency

**Chart choice:**
- Is each chart the right type for the relationship being shown?
- **Anti-pattern checklist** — flag any:
  - 3D charts (always wrong — distort perception)
  - Pie/donut with 5+ categories (use bar chart instead)
  - Gauge/speedometer charts (low data-ink ratio)
  - Dual-axis charts without clear labelling
  - Maps encoding no quantitative data (decorative geography)
  - Monochromatic encoding where status differentiation is needed

**Layout and hierarchy:**
- **Top-left priority**: Most important visual for this audience in the top-left?
- **Reading path**: Does the layout flow high-priority → supporting context → detail?
- **Visual count**: 2–3 key views per page is the Tableau/Microsoft Learn standard. 4–5+ dilutes the message. Flag overcrowded pages.
- Is visual hierarchy clear — what this audience needs most is largest/most prominent?
- Does background imagery reduce contrast or compete with data?

**Consistency and accessibility:**
- Fonts, sizes, and colours consistent across all pages?
- Same colour = same meaning everywhere (e.g., red = behind target, always)?
- Recurring elements (KPI cards, navigation, filters) in consistent spatial positions?
- **Accessibility**: Is colour the only encoding? Add icons/labels if so. Minimum 4.5:1 contrast ratio between text and background.

### DIMENSION 6 — Actionability, Insight & The So What
- **The so what push**: Every pattern must end with a consequence and an action relevant to this audience's decision authority:
  - Operations manager → task assignment or escalation
  - Director → resource reallocation or team intervention
  - Executive → go/no-go, approve/reject, escalate
  - Never leave an observation without a consequence and an action
- Does the dashboard distinguish monitoring (what is) from decision support (what to do)?
- Are critical alerts visually dominant or buried in tables?
- Are forward-looking projections present where the data supports them?
- Can a viewer from this audience leave knowing the single most important action to take today?
- **Missing analysis test**: What would a domain expert serving this audience do immediately after seeing this data that the dashboard doesn't show?

---

## STEP 3 — CHALLENGE QUESTIONS

Ask at least 5 questions the dashboard raises but doesn't answer, framed from this audience's perspective. Good challenge questions:
- Are specific and rooted in actual numbers shown ("X is 44% of total — why?")
- Are questions this audience would actually ask in a meeting
- Challenge assumptions in the design choices
- Probe for missing context, time windows, or comparisons
- Ask about interdependencies the dashboard doesn't surface

---

## STEP 4 — STRUCTURED OUTPUT

Return the review in this exact format:

---

**IDENTIFIED AUDIENCE** — Who this dashboard is for and how you determined it. If unclear, flag it.

**WHAT I SEE** — 2–3 sentence factual summary: audience, domain, pages, key numbers visible.

**DIMENSION SCORES:**

| Dimension | Score | Status | Key Finding |
|---|---|---|---|
| 1. Business Question | /100 | PASS/WARN/FAIL | one sentence |
| 2. Domain Knowledge | /100 | PASS/WARN/FAIL | one sentence |
| 3. Audience Fit | /100 | PASS/WARN/FAIL | one sentence |
| 4. Data Story | /100 | PASS/WARN/FAIL | one sentence |
| 5. Visual Design | /100 | PASS/WARN/FAIL | one sentence |
| 6. Actionability | /100 | PASS/WARN/FAIL | one sentence |
| **Overall** | **/100** | | |

**INTERNAL CONSISTENCY FINDINGS** — Step 1b results: arithmetic issues, unit mismatches, deviation sign errors. "None found" is a valid result.

**CHALLENGE QUESTIONS** — Minimum 5, specific to this dashboard's actual data.

**MISSING ANALYSIS** — Minimum 3 analyses relevant to this audience that the dashboard doesn't show. Each with one sentence on why it matters to them specifically.

**TOP 3 PRIORITIES** — Each with: what to change, why it matters to this audience, what they gain.

**ONE THING DONE WELL** — Genuine, specific praise for the strongest design or analytical decision.

---

## Review Philosophy

A dashboard review is not a design critique. It is a stress test of whether the right people
can make the right decisions faster because of this dashboard.

The standard changes with the audience. What counts as appropriate depth, detail, interactivity,
and recommended action all depend on who is sitting in front of the screen.

A dashboard is not good or bad in the abstract — it is good or bad **for a specific person
trying to do a specific job.**

- If a visual is beautiful but does not accelerate a decision for this audience → it is decoration
- If a number is shown without context → it is noise for any audience
- The standard is not "is this good work?" → it is "does this make **this specific audience** smarter and faster at their job?"
