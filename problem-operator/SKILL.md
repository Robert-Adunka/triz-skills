---
name: problem-operator
description: "TRIZ Problem Operator (Problem-Oriented Nine Screen Approach) — solves problems by analyzing them across a problem timeline (before / during / after the problem) at Super-System, System, and Sub-System levels. The problem is treated as unavoidable; Past explores how to prevent it, Present explores how to address it, Future focuses on how to still reach the overall goal (Plan B / Oberziel) after the problem has occurred. Use this skill when the user describes a specific problem occurring in a system and wants to find solutions. Triggers on 'problem operator', '9 boxes problem', 'problem-oriented', or when the user mentions both a concrete problem and a system. Does NOT handle system evolution — use system-operator for that."
---

<!-- 
  Copyright (c) 2026 Robert Adunka
  Based on the TRIZ System Operator Problem-Oriented Mode by Jens Träger
  Copyright (c) 2025 Jens Träger
  Licensed under the MIT License — see LICENSE in the repository root.
-->

# TRIZ Problem Operator (Problem-Oriented Nine Screen Approach)

Guide the user through a problem-oriented 9 Boxes analysis to find solutions across time and system hierarchy levels. The problem is treated as an unavoidable event:

- **Past** = before the problem — how could it have been prevented?
- **Present** = while the problem is occurring — how can it be addressed?
- **Future** = after the problem — the problem cannot be undone; how can the overall goal (Plan B / Oberziel) still be reached?

## Step 0: Choose working mode

At the very start, ask the user which mode they prefer:

- **Automatic** — generate both tables immediately using your own assumptions; state assumptions made
- **Semi-automatic** — ask a few targeted questions (problem, system, overall goal), then generate
- **Interactive** — work step by step; present a recommendation after each step and wait for confirmation before proceeding

## Process (all modes)

1. **Define the problem and overall goal (Plan B / Oberziel).** What is the problem? Where does it occur (system)? What is the overall goal that should still be reached even if the problem cannot be solved directly?
2. **Define concrete time point labels.** Do not use generic terms. Name the specific moments: Present = the moment the problem exists (e.g., "after the shot"); Past = a point before the problem where prevention was still possible (e.g., "before the shot", "during planning"); Future = the state where the problem is completely unavoidable and irreversible (e.g., "park fully littered"). In interactive mode, propose labels and confirm with the user.
3. **Identify the System, Sub-Systems, and Super-Systems per time point.** The system itself, its sub-systems, and its super-systems may all differ across the three time points — what exists at the moment the problem occurs may be fundamentally different from what existed before or what remains after. Identify all three separately for each time point where they differ.
4. **Present time point — System.** Describe the problem at the system level. What guiding question helps find solutions here?
5. **Present time point — Sub-System.** Describe the problem at the component level. What guiding questions help?
6. **Present time point — Super-System.** Analyze the environment. What in the surroundings can contribute to a solution?
7. **Past time point.** Analyze all three levels for solutions that would preventively stop the problem from occurring.
8. **Future time point.** The problem is completely unavoidable and irreversible. Analyze all three levels for solutions that allow the overall goal (Plan B / Oberziel) to still be reached.

## Output

Before both tables, show a **header block** with:
- **Problem:** [brief description]
- **Overall goal (Plan B / Oberziel):** [goal statement]
- **System definition per time point:** for each time point state the System, its Sub-Systems, and its Super-Systems — all three may differ across time points
- **Time points:** Past = [label], Present = [label], Future = [label]

**Table 1 — Relevant guiding questions per cell** (column headers use the concrete time point labels):

| | Past [label] | Present [label] | Future [label] |
|---|---|---|---|
| **Super-System** | | | |
| **System** | | | |
| **Sub-System** | | | |

**Table 2 — Proposed solutions per cell** (same column labels):

| | Past [label] | Present [label] | Future [label] |
|---|---|---|---|
| **Super-System** | | | |
| **System** | | | |
| **Sub-System** | | | |

## Example

**Problem:** Ink leaks from a pen stored in a shirt pocket and stains the shirt.
**Overall goal (Plan B / Oberziel):** Ensure a neat appearance.
**System:** Pen. **Sub-Systems (Present):** Pen case, refill, retraction mechanism, clip. **Super-Systems (Present):** User, paper, shirt, desk. Sub-systems and super-systems may differ at Past (e.g., packaging, retailer) and Future (e.g., stained fabric, laundry).
**Time points:** Past = pen purchased and stored | Present = pen leaks in pocket | Future = shirt permanently stained

| | Past — pen purchased | Present — pen leaks | Future — shirt stained |
|---|---|---|---|
| **Super-System** | Retailer provides leak-proof cap | Shirt fabric neutralizes ink | Shirt pocket is ink-resistant by design |
| **System** | Pen requires actuation to write — retracts when released | Pen retracts refill automatically when vertical | Pen contains cleaning agent compartment |
| **Sub-System** | Retraction mechanism in grip section prevents accidental opening | Clip locks only when refill is retracted | Ink is water-soluble for easy washing |
