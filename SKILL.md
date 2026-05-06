---
name: dashboard-review
metadata:
  version: "3.0"
description: >
  Use this skill whenever a user wants to review, critique, evaluate, or give feedback on a
  dashboard, report, or data visualization. Triggers include: uploading any dashboard/report
  file such as a PBIX, PBIT, PBIP, Tableau TWB/TWBX, PDF, Excel workbook, CSV, screenshot, or
  image; saying "review my dashboard", "critique this report", "give feedback on this viz",
  "what's wrong with my dashboard", "score my dashboard", "help me improve this Power BI /
  Tableau / Looker report", or any request involving dashboard quality, design, or analytical
  depth. Also use when a user describes a dashboard in text and wants structured feedback.
  This skill produces a full structured review across 6 dimensions with anchored scores, severity-
  classified issues, challenge questions, missing analysis, and prioritised recommendations —
  always calibrated to the actual audience the dashboard was built for.
---

# Dashboard Review Skill v3.0

A structured framework for reviewing dashboards and data reports with the rigour of a senior
data analyst. Reviews are audience-first, score-anchored, and severity-classified. Every
finding connects to a decision, not just a design preference.

---

## Methodological Grounding

This skill's criteria are grounded in the following primary sources:

| Source | Applied to |
|---|---|
| *Information Dashboard Design* — Stephen Few | KPI design, chart choice, data-ink ratio |
| *Show Me the Numbers* — Stephen Few | Comparison logic, table vs. chart decisions |
| *Storytelling with Data* — Cole Knaflic | Narrative structure, clutter reduction, audience calibration |
| *Big Book of Dashboards* — Wexler, Shaffer, Cotgreave | Domain-specific metric standards |
| *The Visual Display of Quantitative Information* — Edward Tufte | Data-ink ratio, chartjunk, sparklines |
| *Good Charts* — Scott Berinato | Visual rhetoric, persuasion vs. exploration |
| *Data Visualization: A Practical Introduction* — Kieran Healy | Perceptual principles, encoding channels |
| *Data Points* — Nathan Yau | Audience-relative truth in visualisation |
| Microsoft Learn: Design Effective Reports in Power BI | Layout standards, visual count, accessibility |
| Tableau: Dashboard Best Practices | Interactivity, filter design, tab structure |
| WCAG 2.1 AA | Contrast ratios, colour-blind-safe encoding |
| Nielsen Norman Group: Data Dashboards | Usability heuristics applied to BI |

---

## Activation

When a user says any of:
- "dashboard review skill"
- "is the dashboard review skill active?"
- "are you ready to review?"

Respond with:

> ✅ **Dashboard Review Skill v3.0 is active.**
>
> Share a dashboard — PBIX, Tableau workbook, PDF, spreadsheet, image, screenshot, or text description — and I'll give you a full structured review across 6 dimensions with anchored scores, severity-classified issues, and a before/after rewrite.
>
> **Dimensions:** Business Question · Domain Logic · Audience Fit · Data Story · Visual Design · Actionability
>
> **To start:** upload a dashboard/report file or describe your dashboard.

---

## Supported Inputs

This skill can be used with any dashboard or report artifact the AI environment can access:

- Power BI: `.pbix`, `.pbit`, `.pbip`, exported PDF, screenshots, or images
- Tableau: `.twb`, `.twbx`, `.tds`, `.tdsx`, `.hyper`, exported PDF, screenshots, or images
- Spreadsheet/report files: `.xlsx`, `.xls`, `.csv`, PDF, images, or screenshots
- Other BI/reporting files from Looker, Looker Studio, Excel, web dashboards, or custom tools
- Text descriptions when no file is available

If the uploaded file can be inspected directly, use it as the primary evidence.
If the AI environment cannot inspect the file type directly, do not pretend to have reviewed it.
Ask the user to export or attach one of the following:

1. Dashboard screenshots for each important page/tab
2. A PDF export of the report
3. Images of key visuals and KPI cards
4. A short text summary of pages, metrics, filters, audience, and concerns

When only file metadata is visible, say so clearly and review only the context the user provides.

---

## Scoring System

### Score Anchors (apply to all 6 dimensions)

| Band | Score | What it means |
|---|---|---|
| Excellent | 90–100 | No meaningful issues; this dimension accelerates decisions for the audience |
| Good | 75–89 | Works for the audience; minor improvements possible but none blocking |
| Warn | 55–74 | Partial — reduces effectiveness; specific fixes needed before sharing widely |
| Fail | 35–54 | Actively impedes the audience; must be fixed before this dashboard is used |
| Critical | 0–34 | Misleads, confuses, or breaks trust; do not use in current state |

### PASS / WARN / FAIL Thresholds

| Status | Score range | Meaning |
|---|---|---|
| PASS | ≥ 75 | Fit for this audience on this dimension |
| WARN | 55–74 | Usable but with risk — flag specific fix |
| FAIL | < 55 | Not fit for purpose — specific action required |

### Overall Score Weighting

The overall score is a weighted average, not a simple mean. Dimensions closest to the
audience's decision-making are weighted more heavily:

| Dimension | Weight |
|---|---|
| 1. Business Question & Purpose | 15% |
| 2. Domain Knowledge & Business Logic | 15% |
| 3. Audience Fit & Interactivity | 15% |
| 4. Data Accuracy, Story & Definitions | 20% |
| 5. Visual Design, Chart Choice & Consistency | 15% |
| 6. Actionability, Insight & The So What | 20% |

*Rationale: A beautiful dashboard that misleads (Dimension 4) or leaves the audience with no
action (Dimension 6) fails its core job more severely than one with imperfect chart choices.*

### Severity Classification for Issues

Every issue found must be tagged:

| Severity | Definition | Example |
|---|---|---|
| 🔴 CRITICAL | Actively misleads the audience or breaks data trust | Totals don't reconcile; red used for a positive result |
| 🟡 MAJOR | Significantly reduces effectiveness or confidence | KPIs with no target or comparison; 12+ visuals on one page |
| 🔵 MINOR | Polish or improvement; audience can still do their job | Inconsistent font sizes; chart title not specific enough |

*Never mix severity levels in a flat list. Group by severity so the dashboard owner can
triage in order of impact.*

---

## Workflow: Steps 0 → 4

### STEP 0 — IDENTIFY THE AUDIENCE (never skip)

Every dimension is judged through the lens of whether **this specific audience** can do
their job better because of this dashboard. The same feature can be a strength for one
audience and a failure for another.

| Audience | Primary need | Appropriate depth | Attention budget |
|---|---|---|---|
| C-Suite / Executive | Situation awareness, go/no-go | Headline KPIs only | 3–5 min |
| Department Head / Director | Performance management | Summary + one breakdown level | 5–10 min |
| Operations Manager | Day-to-day prioritisation | Task-level detail, status, ownership | 10–20 min |
| Analyst / Data Team | Pattern investigation, anomaly diagnosis | Full granularity, drill-through | As needed |
| Field / Frontline Worker | What do I do right now | Single unambiguous signal | 30 seconds |
| External Stakeholder / Client | Confidence, accountability | Curated highlights, plain language | 2–3 min |

**Rules:**
- If the audience is stated explicitly, use it
- If the purpose implies the audience (e.g. "CEO monthly review"), infer it and state the inference
- If the audience is ambiguous, flag it — no defined audience means no design standard
- If one page serves multiple audiences, flag it — this is almost always a design failure

---

### STEP 1 — READ BEFORE JUDGE

Complete all five checks before scoring anything. Do not form scoring opinions during this step.

#### 1a. Orient
- What business question is this dashboard answering?
- Who is the audience (from Step 0)?
- What domain — sales, finance, construction, HR, logistics, community data, other?
- How many pages or tabs? What does each cover?

#### 1b. Internal Consistency Check
- Add up all segment totals → do they match the stated overall total?
- If subtotals exceed the parent total, flag immediately — data integrity failure (🔴 CRITICAL)
- Are deviation calculations correct? (Target − Actual = stated gap?)
- Are deviation signs consistent throughout? (positive = above target everywhere, or nowhere — never mixed)
- Do units match across related metrics? (person-days vs. persons vs. hours — flag if mixed)

#### 1c. Time Horizon Adequacy
- Revenue/financial trends → need 12+ months to distinguish seasonality from noise
- Churn/retention → need 4–6 quarters before conclusions are defensible
- Project progress → elapsed duration must be shown against total planned duration
- If the time window is too short for the claims being made, flag it (🟡 MAJOR)

#### 1d. Audience Scan Simulation
Simulate how the identified audience actually uses this dashboard:
- **Executive**: Can they extract what they need in under 5 minutes without scrolling or filtering?
- **Operations manager**: Is the highest-priority task immediately visible?
- **Analyst**: Can they drill into anomalies without leaving the dashboard?
- **Field worker**: Is there exactly one unambiguous action signal?
- Does the most critical information appear where this audience looks first — top-left on most screens?

#### 1e. Data Trust & Governance Check *(new in v3)*
These questions do not score a separate dimension — they feed into Dimension 4.
- Is a "data as of" date visible on every page? If not: 🟡 MAJOR
- Is the data source or system of record identified anywhere?
- Is the refresh cadence stated (live, daily, weekly, monthly)?
- For regulated or high-stakes domains (finance, HR, health): is the dataset certified or validated?
- Are there impossible values — negative headcounts, >100% completion on a bounded scale?
- If governance information is completely absent and the audience is executive or external: 🔴 CRITICAL

---

### STEP 2 — EVALUATE ACROSS 6 DIMENSIONS

Evaluate each dimension with a score, PASS/WARN/FAIL status, and a one-sentence key finding.
Apply severity tags (🔴 🟡 🔵) to all issues found.

#### DIMENSION 1 — Business Question & Purpose

**What to assess:**
- Is there a clearly stated or implied business question?
- Does every page or tab serve that question, or are there orphan pages?
- **Audience time test**: Given this audience's attention budget, does the dashboard deliver its most important message within that window?
- **Top-left priority rule**: The most important finding for this audience should occupy or anchor the upper-left quadrant, matching the natural scan path of most viewers
- **Opening screen test**: Does the first thing this audience sees answer their core question — or does it waste their time with navigation, branding, or decorative content?
- Is the most critical number or finding the most visually prominent element on the page?

**Anchor examples:**
- 90+: Title states the business question, opening screen answers it, every tab has clear purpose
- 75–89: Purpose is clear but some tabs are loosely connected or take extra scanning to reach the key insight
- 55–74: Purpose has to be inferred; some visuals serve no clear decision
- <55: No clear question; dashboard appears to be a data dump

---

#### DIMENSION 2 — Domain Knowledge & Business Logic

**What to assess:**
- Does the dashboard reflect genuine understanding of how this domain works?
- Are these the right metrics for the business problem — or vanity metrics that look good without informing decisions?
- Are domain-critical metrics absent? Common absences by domain:
  - **Sales**: pipeline coverage ratio, win rate by stage, average deal velocity
  - **Telecom/SaaS**: churn by segment, net revenue retention, LTV:CAC ratio
  - **Construction**: cost-at-completion, schedule performance index, earned value
  - **HR**: regrettable attrition rate, time-to-productivity, span of control
  - **Community/nonprofit**: engagement depth (not just reach), return participation rate
- Do metrics reflect causes and drivers — not just outcomes?
- Are thresholds and crisis bands domain-appropriate?

**Anchor examples:**
- 90+: Right metrics for this domain, cause-and-effect chain visible, thresholds calibrated to domain norms
- 75–89: Core metrics correct; one or two important leading indicators missing
- 55–74: Metrics are generic; domain expert would immediately ask for what's missing
- <55: Vanity metrics dominate; no domain-specific logic visible

---

#### DIMENSION 3 — Audience Fit & Interactivity

**What to assess:**
- **Depth calibration**: Is the level of detail right for this audience?
  - Executives: headline KPIs and trend direction only — not raw tables or operational codes
  - Operations managers: task-level detail, status flags, ownership assignment
  - Analysts: full granularity, slicers on every relevant dimension, drill-through paths
  - Mixing depths for a single-audience dashboard is a design failure (🟡 MAJOR)
- **Dashboard vs. report distinction**: A dashboard is an at-a-glance overview. Operational detail belongs in drill-through or a linked report unless the audience is operational and detail is their primary need
- **Interactivity match**:
  - Executives rarely filter — they need pre-filtered views for their specific scope
  - Analysts always filter — they need full slicer control and saved bookmark support
- **Navigation**: Are tabs clearly labelled? Can users always return to the home view?
- **Display context**: Is this designed for the screen the audience actually uses — boardroom TV, laptop, shop floor tablet, mobile phone?

**Anchor examples:**
- 90+: Detail level, interactivity, and display format precisely match this audience's workflow
- 75–89: Mostly right; one depth mismatch or a filter the audience doesn't need
- 55–74: Audience has to work around the dashboard to get what they need
- <55: Dashboard built for a different audience than the one using it

---

#### DIMENSION 4 — Data Accuracy, Story & Definitions

**What to assess:**
- **Facts vs. insights test**: Flag every KPI card showing a number without comparison context — no target, no prior period, no benchmark. A number alone is a fact. An insight requires at least two data points. (🟡 MAJOR for executive dashboards; 🔵 MINOR for analyst exploratory tools)
- Are metrics clearly defined in terms this audience understands — with glossary or tooltip support if needed?
- Are benchmarks, targets, or prior period comparisons present and relevant?
- Are calculations arithmetically correct? (Cross-check Step 1b results)
- Is the time horizon sufficient for the claims? (Cross-check Step 1c)
- Is the "data as of" date visible on every page? (Cross-check Step 1e)
- Any data integrity issues — impossible values, suspicious uniformity, totals that don't reconcile?
- Are variance signs and colours logically consistent? (Green = favourable, Red = unfavourable — always, never inverted)

**Anchor examples:**
- 90+: All KPIs have targets or comparisons; definitions accessible; data trust signals visible; time window appropriate
- 75–89: Most KPIs contextualised; one or two standalone numbers; data-as-of date present
- 55–74: Several KPI cards show bare numbers; no data timestamp; definitions absent
- <55: Majority of metrics lack context; totals don't reconcile; no governance signals

---

#### DIMENSION 5 — Visual Design, Chart Choice & Consistency

**Chart choice:**
- Is each chart the right type for the relationship it encodes?
- **Anti-pattern checklist** — tag each with severity:
  - 3D charts → 🔴 CRITICAL (always distort perception)
  - Pie/donut with 5+ categories → 🟡 MAJOR (use horizontal bar chart instead)
  - Gauge/speedometer charts → 🔵 MINOR (low data-ink ratio; use bullet chart instead)
  - Dual-axis charts without explicit axis labelling on both sides → 🟡 MAJOR
  - Maps used decoratively with no quantitative encoding → 🔵 MINOR
  - Monochromatic colour where status differentiation is needed → 🟡 MAJOR
  - Trend claimed on fewer than 6 data points → 🟡 MAJOR

**Layout and hierarchy:**
- **Top-left priority**: Is the most important visual for this audience in the top-left quadrant?
- **Reading path**: Does the layout flow naturally — high priority → supporting context → detail?
- **Visual count**: 2–3 key views per page is the Tableau and Microsoft Learn standard. 4–5 is acceptable for analyst dashboards. 6+ on one executive page = 🟡 MAJOR
- Is visual hierarchy enforced by size, position, and contrast — not just colour?
- Does background imagery reduce contrast or compete with data labels?

**Consistency and accessibility:**
- Fonts, sizes, and colour palettes consistent across all pages?
- Same colour = same meaning everywhere (e.g., teal = actual, grey = target — never swapped)
- Recurring elements — KPI cards, navigation, date filters — in consistent spatial positions across pages?
- **Accessibility (WCAG 2.1 AA)**: Minimum 4.5:1 contrast ratio for text vs. background. If colour is the only encoding for status (good/bad), add an icon or label. (Absent: 🟡 MAJOR)

**Anchor examples:**
- 90+: Every chart type is the best choice for its data; layout is scannable in one pass; fully accessible
- 75–89: Chart choices mostly correct; minor layout inconsistencies; accessibility mostly covered
- 55–74: One or more anti-patterns present; layout requires searching; colour encoding ambiguous
- <55: Multiple anti-patterns; cluttered layout; low contrast; misleading visual choices

---

#### DIMENSION 6 — Actionability, Insight & The So What

**What to assess:**
- **The so-what test**: Every visible pattern must connect to a consequence and an action within this audience's decision authority:
  - Executive → go/no-go, approve/reject, escalate to board
  - Director → resource reallocation, team intervention, budget adjustment
  - Operations manager → task assignment, escalation, schedule change
  - A dashboard that shows "what is" without implying "therefore do X" is monitoring, not decision support
- Does the dashboard distinguish between monitoring mode (status) and decision-support mode (recommended action)?
- Are critical alerts visually dominant — or buried in tables where the audience will miss them?
- Are forward-looking projections shown where the data and domain support them?
- Can a viewer from this audience leave with a single clear, unambiguous priority action?
- **Missing analysis test**: What would a domain expert do in the first five minutes after seeing this data that the dashboard doesn't support?

**Anchor examples:**
- 90+: Every major insight has an explicit consequence and action for this audience; alerts are unmissable
- 75–89: Most insights actionable; one or two patterns left as observations without consequence
- 55–74: Dashboard shows data; audience must derive all implications themselves
- <55: Pure data display with no action orientation; audience leaves no smarter than before

---

### STEP 3 — CHALLENGE QUESTIONS

Generate at least 5 questions the dashboard raises but does not answer.

**Quality standard for challenge questions:**
- Rooted in actual numbers visible in the dashboard (e.g., "Revenue is 12% below target — is this driven by volume, price, or mix?")
- Questions this audience would ask in a real meeting or review
- Challenge assumptions embedded in the design choices themselves
- Probe for missing context, insufficient time windows, or absent comparisons
- Surface interdependencies the dashboard doesn't show

Do not write generic questions that could apply to any dashboard.

---

### STEP 4 — STRUCTURED OUTPUT

Return the review in this exact format. Do not skip or reorder sections.

---

**IDENTIFIED AUDIENCE**
State who this dashboard is for and how you determined it (explicit label, inferred from domain/title, or unclear). If unclear, flag it as a finding.

---

**WHAT I SEE**
2–3 sentences: audience, domain, number of pages/tabs, key metrics visible, and time period shown. This confirms you have read the dashboard before scoring it.

---

**GENUINE STRENGTH**
One specific thing this dashboard does well — a design or analytical decision that genuinely serves the audience. Place this early so the reviewer leads with context, not just criticism.

---

**DIMENSION SCORES**

| Dimension | Score /100 | Status | Key Finding |
|---|---:|---|---|
| 1. Business Question | | PASS/WARN/FAIL | one sentence |
| 2. Domain Knowledge | | PASS/WARN/FAIL | one sentence |
| 3. Audience Fit | | PASS/WARN/FAIL | one sentence |
| 4. Data Story | | PASS/WARN/FAIL | one sentence |
| 5. Visual Design | | PASS/WARN/FAIL | one sentence |
| 6. Actionability | | PASS/WARN/FAIL | one sentence |
| **Overall (weighted)** | | | |

*Weights: D1 15% · D2 15% · D3 15% · D4 20% · D5 15% · D6 20%*
*PASS ≥ 75 · WARN 55–74 · FAIL < 55*

---

**INTERNAL CONSISTENCY FINDINGS**
Results from Step 1b (arithmetic), Step 1c (time horizon), and Step 1e (governance/data trust).
Each finding tagged with severity. "None found" is a valid result — state it explicitly.

---

**ISSUES BY SEVERITY**

List all issues grouped by severity. Do not mix severity levels in a flat list.

🔴 CRITICAL — must fix before this dashboard is used
🟡 MAJOR — must fix before this dashboard is shared widely
🔵 MINOR — fix when time allows

Each issue: state what it is, where it appears, and what it costs the audience.

---

**CHALLENGE QUESTIONS**
Minimum 5, specific to this dashboard's actual data and audience. No generic questions.

---

**MISSING ANALYSIS**
Minimum 3 analyses this audience would need that the dashboard does not provide.
Format: [Analysis name] — [one sentence on why it matters specifically to this audience]

---

**TOP 3 PRIORITIES**
Each with:
1. What to change (specific, not vague)
2. Why it matters to this audience in particular
3. What they gain when it is fixed

---

**BEFORE / AFTER REWRITE** *(include for at least one issue)*
Show a concrete example of how to improve a specific label, KPI title, chart title, or dashboard narrative.

| Element | Current | Recommended | Why |
|---|---|---|---|
| Dashboard title | [current text] | [better version] | [one sentence] |
| KPI label | [current] | [better] | [one sentence] |
| Chart title | [current] | [better] | [one sentence] |

---

## Review Philosophy

A dashboard review is not a design critique. It is a stress test of whether the right people
can make the right decisions faster because of this dashboard.

The standard is not "is this good work?" — it is "does this make **this specific audience**
smarter and faster at their job?"

- If a visual is beautiful but does not accelerate a decision for this audience → it is decoration
- If a number is shown without comparison context → it is noise for any audience
- If an insight has no consequence and no action → it is a fact, not a finding

The same dashboard can be excellent for an analyst and actively harmful for an executive.
Audience comes first. Every time.
