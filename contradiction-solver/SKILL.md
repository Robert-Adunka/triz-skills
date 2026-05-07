---
name: contradiction-solver
description: "TRIZ Contradiction Solver and 40 Inventive Principles — resolves engineering and physical contradictions using the Altshuller Matrix, Matrix 2003, and the 40 Inventive Principles. Use this skill whenever the user mentions 'contradiction', 'inventive principles', '40 principles', 'Altshuller', 'Matrix 2003', 'engineering contradiction', 'physical contradiction', 'IF THEN BUT', or wants to solve a technical trade-off, improve a system parameter without worsening another, or apply TRIZ contradiction analysis."
---

<!-- 
  Based on the TRIZ Contradiction Solver and 40 Inventive Principles Prompt
  Copyright (c) 2025 Jens Traeger
  Licensed under the MIT License — see LICENSE in the repository root.
-->

# TRIZ Contradiction Solver and 40 Inventive Principles

Identify and solve engineering and physical contradictions using the Altshuller Matrix, Matrix 2003, and the 40 Inventive Principles.

## How this tool works (two-phase)

This tool operates in two phases:

**Phase 1 — Init (first call, no indices):**  
Call this tool with just the user's `query`. The response contains this methodology guide and the complete numbered parameter lists for both matrices. Use these lists to guide the user through parameter mapping.

**Phase 2 — Calculate (second call, with indices):**  
After the user has confirmed the abstract TRIZ parameters, call this tool again with:
- `matrix_type`: `"altshuller"` or `"matrix_2003"`
- `improving_indices`: comma-separated 1-based parameter numbers for the improving side (e.g. `"9,14"`)
- `worsening_indices`: comma-separated 1-based parameter numbers for the worsening side (e.g. `"25,33,19"`)

The tool then computes all (improving × worsening) matrix intersections, scores the inventive principles (1st position = 100 pts, 2nd = 90 pts, 3rd = 80 pts, …), aggregates across all cells, and returns ranked principles with their names and sub-principles.

**Important:** Physical contradictions do NOT require Phase 2 — solve them directly using the separation principles below.

---

## Interaction flow

1. **Problem input.** Ask the user for a problem statement or contradiction. Wait for user input.

2. **Identify the contradiction type:**
   - **Engineering contradiction:** improving one parameter worsens another  
     → "IF …, THEN …, BUT …"
   - **Physical contradiction:** a parameter must have two opposing values at once  
     → "X must be [A] IN ORDER TO …, AND X must be [not-A] IN ORDER TO …"

3. **Engineering contradiction → follow the two-phase matrix flow:**

   a. Ask whether to use the **Altshuller Matrix** (39 classic parameters) or **Matrix 2003** (48 modern parameters). Recommend Matrix 2003 for modern technical systems.

   b. **Map concrete → abstract (multiple allowed):**  
      From the Phase 1 parameter list, identify one or more abstract TRIZ parameters that match the user's concrete improving parameter. Then do the same for the worsening parameter.  
      A single concrete parameter often maps to multiple abstract ones — this is expected and important.

      Example:  
      Concrete worsening parameter: *"Ladekomfort"*  
      → Altshuller abstract: 25 (Loss of time) + 33 (Ease of operation) + 9 (Speed)

   c. **Present and confirm** the proposed abstract parameters with the user before proceeding.

   d. **Call this tool (Phase 2)** with the confirmed parameter numbers. The tool calculates the lookup across all combinations and returns ranked inventive principles.

   e. **Present the results:** show the ranked principles, explain how each applies to the specific problem, and suggest concrete solution directions.

4. **Physical contradiction → solve directly (no matrix call needed):**

   Express the contradiction as: *"X must be [A] IN ORDER TO …, AND X must be [not-A] IN ORDER TO …"*  
   Apply the four separation principles:
   - **Separation in Time** — A at one time, not-A at another
   - **Separation in Space** — A in one place, not-A in another  
   - **Separation between Parts and Whole** — A at part level, not-A at system level
   - **Separation between Conditions** — A under one condition, not-A under another

   For each applicable separation, suggest inventive principles that realize it.

5. **No clear contradiction:** Apply the 40 Inventive Principles directly. Scan each principle for applicability, consider sub-principles and synonyms.

---

## Key definitions

### Engineering Contradiction
Improving one system parameter causes deterioration of another.  
Format: "IF …, THEN …, BUT …" / "WENN …, DANN …, ABER …"

Example: "IF the barrel of the muzzle-loader is long, THEN accuracy increases, BUT loading comfort decreases."

### Physical Contradiction
A parameter must simultaneously take two opposing values, each justified by a different requirement.  
Format: "X must be [A] TO …, AND X must be [not-A] TO …"

Example: "A boat must be wide TO prevent capsizing, AND it must be narrow TO go fast."

### Nomenclature
- English: Altshuller Matrix, Inventive Principles
- German: Altschuller-Matrix, Innovationsprinzipien

---

## 40 Inventive Principles — Quick Reference

| # | EN | DE |
|---|----|----|
| 1 | Segmentation | Zerteilen |
| 2 | Taking out | Extraktion |
| 3 | Local quality | Lokale Qualität |
| 4 | Asymmetry | Asymmetrie |
| 5 | Merging | Zusammenführen |
| 6 | Universality | Universalität |
| 7 | Nested doll | Schachtelung |
| 8 | Anti-weight | Gegengewicht |
| 9 | Preliminary anti-action | Vorzeitige Gegenwirkung |
| 10 | Preliminary action | Vorherige Wirkung |
| 11 | Beforehand cushioning | Vorbeugungsmaßnahmen |
| 12 | Equipotentiality | Äquipotentialität |
| 13 | The other way round | Umkehrung |
| 14 | Spheroidality — Curvature | Sphärizität |
| 15 | Dynamics | Dynamisierung |
| 16 | Partial or excessive action | Teil- oder Überwirkung |
| 17 | Another dimension | Dimensionswechsel |
| 18 | Mechanical vibration | Mechanische Schwingung |
| 19 | Periodic action | Periodische Wirkung |
| 20 | Continuity of useful action | Kontinuität der nützlichen Wirkung |
| 21 | Skipping | Überspringen |
| 22 | Blessing in disguise | Umwandlung von Nachteilen |
| 23 | Feedback | Rückkopplung |
| 24 | Intermediary | Vermittler |
| 25 | Self-service | Selbstbedienung |
| 26 | Copying | Kopieren |
| 27 | Cheap short-living | Billige Kurzlebigkeit |
| 28 | Mechanics substitution | Mechanikersatz |
| 29 | Pneumatics and hydraulics | Pneumatik und Hydraulik |
| 30 | Flexible shells and thin films | Flexible Hüllen und dünne Folien |
| 31 | Porous materials | Poröse Materialien |
| 32 | Color changes | Farbwechsel |
| 33 | Homogeneity | Homogenität |
| 34 | Discarding and recovering | Verwerfen und Wiederherstellen |
| 35 | Parameter changes | Parameteränderung |
| 36 | Phase transitions | Phasenübergang |
| 37 | Thermal expansion | Wärmedehnung |
| 38 | Strong oxidants | Starke Oxidationsmittel |
| 39 | Inert atmosphere | Inertgas-Atmosphäre |
| 40 | Composite materials | Verbundwerkstoffe |
