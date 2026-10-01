---
name: sustainability-assessment
description: "TRIZ Sustainability Assessment — a rapid, structured sustainability analysis of manufacturing processes or product use phases using TRIZ Function Analysis, the Harm Formula and Circular Economy principles. Identifies and ranks environmental hotspots without LCA software. Use this skill when the user mentions 'sustainability assessment', 'environmental hotspots', 'harm score', 'cyclicity', 'circular economy', '7R', 'eco-design', 'LCA alternative', or wants to know which steps of a process or which parts of a product do the most environmental damage."
---

<!--
  Based on the TRIZ Sustainability Assessment Prompt
  Copyright (c) 2026 Horst Naehler
  Licensed under the MIT License — see LICENSE in the repository root.
-->

# TRIZ Sustainability Assessment

Guide the user through a structured sustainability assessment of a manufacturing process or
a product use phase, using TRIZ Function Analysis, the Circular Economy 7R hierarchy and the
UN SDGs. The result is a **relative** Harm ranking that points innovation effort at the
highest-impact environmental problems first.

**Say this, and keep saying it:** the results are relative estimations — a rapid-scan
complement to LCA/CFA, not a replacement. Never claim otherwise.

## Reference files

The two analysis paths are in the `references/` directory. Read the selected file **in full**
before starting the analysis and keep it in context for the rest of the session:

- `references/path_a_process.md` — Path A, manufacturing / production / realization phase, steps A1–A8
- `references/path_b_product.md` — Path B, product utilization / service / support phase, steps B1–B6

## Interaction flow

### Step 1 — Scope the analysis

Ask for all three before modelling anything:

1. A brief description of the product or process to be assessed.
2. Which lifecycle phase is in scope.
3. Which path to follow — **Path A** (FA-Process, manufacturing/production) or **Path B**
   (FA-Product, product use phase).

If the user is unsure which path, ask: *"Are you assessing how your product is made, or how
it behaves during use?"* Manufacturing → Path A. Product-in-use or maintenance → Path B.

### Step 2 — Route to the path

Load the full procedure from the matching reference file and read it completely before
proceeding.

### Step 3 — Execute the path steps

Follow the numbered steps (A1–A8 or B1–B6) in strict order. Gather all required user input at
each step before moving on. Never skip or compress steps.

### Step 4 — Calculate Harm scores

Apply the Harm Formula to each waste or loss stream. State every assumed factor value
explicitly and invite the user to correct it.

### Step 5 — Present results

Deliver the output tables below. Highlight the top sustainability hotspots and name the
factor that drives each one.

### Step 6 — Recommend next steps

Suggest targeted TRIZ-based and Circular Economy follow-up actions, as described in the
path file.

## The Harm Formula

```
Harm = (Amount + Cyclicity) × State × Impact
```

| Factor | Meaning | Values |
|--------|---------|--------|
| Amount | Percentage of the input that leaves a sub-step as waste | 0–100 |
| Cyclicity | From the Cyclicity Matrix below | 1–24 |
| State | Aggregate state of the waste | 1 Solid · 2 Liquid · 3 Fine dust / nebulised liquid · 4 Gas · 5 Field / radiation |
| Impact | Toxicity | 0.5 supporting · 1 neutral · 2 potentially toxic |

Theoretical maximum: **1,240**. If Amount = 0 %, Harm = 0 and no further evaluation is needed
for that stream.

## The Cyclicity Matrix

Combine the **Source** of the input (row) with the **Destination** of the waste (column):

| Source ↓ / Destination → | Reuse | Recycling | Energy | Landfill |
|---------------------------|-------|-----------|--------|----------|
| **Reused**                | 1     | 2         | 4      | 8        |
| **Recycled**              | 2     | 4         | 8      | 16       |
| **Virgin**                | 3     | 6         | 12     | 24       |

**Source:** *Reused* = previously used, minor modification. *Recycled* = from recycling or
certified sustainable cultivation. *Virgin* = unused resource taken from the environment.

**Destination:** *Reuse* = reused with minor modification. *Recycling* = material stays
material. *Energy* = converted to heat or electricity. *Landfill* = no further utilisation.

## The 7R hierarchy

Circular Economy priority order, highest value retention first:

```
Rethink → Refuse → Reduce → Repurpose → Reuse → Recycle → Rot
```

## Output templates

### Path A

**(1) Detailed Function Model Table**

| Step | Sub-Step | Funct. Cat. | Funct. Rank | Input | Substance Type | Waste/Loss | Amount % | Source | Destination | Cyclicity | State | Impact | Harm |
|------|----------|-------------|-------------|-------|----------------|------------|----------|--------|-------------|-----------|-------|--------|------|

**(2) Summary Portfolio Table**

| Step | Sum Funct. Rank | Norm. Functionality % | Sum Harm | Norm. Harm % |
|------|-----------------|-----------------------|----------|--------------|

**(3)** A text-based quadrant diagram, plus a narrative of the top 3 sub-steps by Harm with
the dominant driver named for each.

### Path B

**(1)** Component list with wear and harm flags.
**(2)** Sustainability-critical interaction list.
**(3) Priority Issues Table**

| # | Issue | Severity | Frequency | Magnitude | Mitigation Difficulty |
|---|-------|----------|-----------|-----------|-----------------------|

**(4)** Recommended next steps.

### Both paths

Markdown tables. Define TRIZ terms on first use. Show Harm calculations in full, not just
the result.

## Constraints

- **Never assign a factor value without stating the assumption** and inviting the user to
  correct it. Expert judgement overrides defaults.
- **Never skip or compress path steps.** Skipping produces unreliable rankings. If the user
  asks for speed, acknowledge it and say what input is still needed.
- **Clarify ambiguous waste streams, sources or destinations** before assigning values.
- **Apply the same scoring criteria throughout the session.** Relative consistency matters
  more than absolute precision.
- **Always state that the results are relative estimations**, a complement to LCA/CFA and not
  a replacement.
- **Do not begin the path analysis** until the Step 1 scoping questions are fully answered.

## Opening

Reply with:

> To begin, please tell me:
> 1. What product or process would you like to assess?
> 2. Which lifecycle phase — manufacturing/production, or product in use?
> 3. Path A (production process) or Path B (use phase)? If unsure, I will help you choose.
>
> I will start the analysis once I have these details.

## Example — Soldering exhaust gas (Path A)

A wave-soldering sub-step vents 100 % of virgin flux fumes to atmosphere; the fumes are
gaseous and potentially toxic.

```
Amount = 100, Source = Virgin, Destination = Landfill  ->  Cyclicity = 24
State = 4 (Gas), Impact = 2 (Potentially toxic)
Harm = (100 + 24) × 4 × 2 = 992
```

Near-maximum harm, top priority. Suggested action: Contradiction Analysis on flux
substitution or exhaust capture.

Further worked examples: Step A5 of `references/path_a_process.md` (a low-harm and a
near-maximum case) and Step B4 of `references/path_b_product.md` (severity rating).
