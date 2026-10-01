---
name: function-analysis
description: "TRIZ Function Analysis for technical systems — identifies tools, actions, objects, and functions, clarifies component relationships, and reveals the system's main function. Use this skill when the user wants to perform a function analysis, identify functions in a technical system, map tools-actions-objects, create a function model, or analyze component interactions. Also trigger on mentions of 'function analysis', 'function model', 'tool-action-object', 'function carrier', or when the user wants a CSV for the Function Model Visualizer or TIRAZIS."
---

<!-- 
  Based on the TRIZ Function Analysis Prompt
  Copyright (c) 2025 Jens Traeger, 2026 Robert Adunka
  Licensed under the MIT License — see LICENSE in the repository root.
-->

# TRIZ Function Analysis

Guide users through a structured Function Analysis of a technical system using TRIZ principles.

## Working mode — ask first, and wait for the answer

Ask before anything else, and wait for the answer:

- **Automatic** — build the whole analysis at once from your own assumptions, and state the
  assumptions you made.
- **Semi-automatic** — ask the four questions below, then build.
- **Interactive** — one step at a time: propose, wait for confirmation, then continue.

Naming a system is **not** choosing a mode. If the user describes a system without picking one,
ask again instead of assuming Automatic.

### Semi-automatic — the four questions

1. Which system, and what is its main function?
2. Where does the system boundary run — what still belongs to the system, what is already
   supersystem?
3. Which components do you already know?
4. Which problem is behind this analysis?

## Interaction flow

1. **Identify the system.** Ask the user: "What is your interesting technical system?" Wait for input.

2. **Component analysis.** Identify super-system, technical system, and sub-system components.

3. **Interaction analysis.** Analyze interactions between components from the component analysis. Ask: "Can you help me analyze the interactions?"

4. **Function Analysis.** Write all relevant functions in tabular form:

   | Tool | Action | Object | Category (U/H) | Degree of fulfillment (N/I/E or "---") | Changed/retained parameter |
   |---|---|---|---|---|---|

   Three rules decide whether the model is usable — see *Rules for the function model* below.

5. **CSV export.** After the table is finished, ask whether the user wants it as CSV, mention
   that one file opens in both tools — and then **stop and wait for the answer**.

   Ask in the user's own language and in your own words. The wording in this skill is an
   instruction to you, not a sentence to print: never quote it, never ask in English inside a
   German answer, and never answer your own question by outputting the CSV straight away.

   Only once the user has said yes, output **one** CSV, in a code block, in this format:

   ```
   Carrier,Carrier Type,Action,Object,Object Type,Status,Parameter
   ```

   | Column | Values | |
   |---|---|---|
   | Carrier | the component that acts | content language |
   | Carrier Type | `standard` · `super` · `target` | **always English** |
   | Action | one short active verb | content language |
   | Object | the component that is acted on | content language |
   | Object Type | `standard` · `super` · `target` | **always English** |
   | Status | `normal` · `insufficient` · `excessive` · `harmful` | **always English** |
   | Parameter | the parameter that changes or is kept | content language |

   `Status` carries category and degree together: useful + normal/insufficient/excessive, and
   `harmful` for a harmful function. `standard` is a system component, `super` a supersystem
   element, `target` the target of the main function.

   **The header, the type words and the status words must be English**, even in a German
   analysis. Not a matter of taste: TIRAZIS recognises the header row by the words `carrier`,
   `action` and `object`. With a German header it reads the header as a function and the model
   starts with a phantom. Names, verbs and parameters stay in the language of the analysis.

   Quote any field that contains a comma. One line per function, no blank lines.

   Example (German analysis, English structure words):

   ```
   Carrier,Carrier Type,Action,Object,Object Type,Status,Parameter
   Hand,super,drückt,Hebel,standard,normal,Position
   Schneidrad,standard,schneidet,Pizza,target,normal,Struktur
   Schneidrad,standard,verletzt,Finger,super,harmful,Unversehrtheit
   ```

   Then add both links on their own lines:

   [🔗 Function Model Visualizer](https://www.triz-consulting.de/FunctionModel/index.html)
   [🔗 TIRAZIS](https://www.triz-consulting.de/TIRAZIS/)

   Both read this one file. TIRAZIS takes the first six columns and ignores the parameter;
   the Function Model Visualizer reads all seven and uses the two type columns to fill in the
   component classification that the user would otherwise click together by hand.

## Rules for the function model

### The system itself never appears in the model

Tool and object are always **components** — parts of the system, or elements of the
supersystem. The system as a whole is the heading above the model, never a line inside it.

> **Wrong:** Pizza cutter cuts pizza
> **Right:** Cutting wheel cuts pizza

The component analysis keeps its three levels — supersystem, system, subsystem. The rule is
about the **table**, not about the component list.

### One short active verb

One line, one verb, active, third person. This is where models fail most reliably, so the
counter-examples matter more than the rule:

| | |
|---|---|
| **Right** | Cutting wheel cuts pizza |
| Passive | ~~Pizza is cut by the cutting wheel~~ |
| Nominalisation | ~~Cutting wheel performs the cutting~~ |
| Auxiliary construction | ~~Cutting wheel makes it possible that…~~ |
| Two verbs | ~~Cutting wheel cuts and holds~~ — that is two lines |

A verb that needs a helper verb is not a function. If no short verb fits, the function has not
been understood yet.

### The main function is named, but is not a line

Name the main function above the table, with its target and the parameter that changes. **Do
not write it into the table** in the form *system — action — target*. In the table it is
carried by a **component**:

> Main function: the pizza cutter cuts the pizza. Target: pizza. Changed parameter: structure.
> In the table: **Cutting wheel cuts pizza** — not *Pizza cutter cuts pizza*.

If no component can be named that carries the main function, the component analysis is
incomplete. That is a finding, not a reason to put the system into the table.

## Key concepts

### Definition of Function
A function is an action performed by one component (the tool / function carrier) to change or maintain a parameter of another component (the object of the function). Examples: Broom moves dirt. Helmet stops stone. Display informs user.

### Function Classification
Functions are either useful (U) or harmful (H). Only useful functions are graded:
- **N** = Normal (adequate performance)
- **I** = Insufficient (underperforming)
- **E** = Excessive (overperforming)

Harmful functions are empty in the degree of fulfillment.

### Magic Wand Test
To verify the legitimacy of a function: if removing the tool changes the object, a function exists.

### Main Function and Targets
The main function must always be identified. It determines the **target component** in the
supersystem — the one whose parameter changes because of it. In the CSV that component carries
`target` as its type.

How it is written down is covered under *The main function is named, but is not a line*.

**Example:** Main function of an aircraft: transport passengers and cargo. Targets: passengers
and cargo. Changed parameter: geographic location. In the table it reads **fuselage transports
passengers** — not *aircraft transports passengers*.
