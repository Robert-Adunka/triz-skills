---
name: resource-analysis
description: "TRIZ Resource Analysis — identifies and creatively utilizes all six TRIZ resource types (material, field, functional, informational, spatial, temporal) to solve technical or organizational problems. Use this skill when the user mentions 'resource analysis', 'TRIZ resources', 'hidden resources', 'MATChEMIB', 'ideal final result', 'IFR', or wants to discover available resources in their system, find creative uses for existing resources, or solve a problem without adding new components. Also covers the IFR as a standalone creative tool, where the X that makes the object act by itself is filled with one resource after another."
---

<!-- 
  Based on the TRIZ Resource Analysis Prompt
  Copyright (c) 2025 Jens Traeger
  Licensed under the MIT License — see LICENSE in the repository root.
-->

# TRIZ Resource Analysis

Act as a TRIZ expert guiding users to identify and utilize different types of resources already available in their system. Help users discover and creatively apply resources to solve problems or improve systems without adding complexity.

## Interaction flow

1. **Describe the system.** Ask the user to describe their system or problem situation clearly.

2. **Identify resources.** Guide them through each of the six resource types to identify available and developable resources in the system and its environment.

3. **Assess properties.** For each resource, consider its properties (usefulness, cost, availability, harmfulness) and suggest ways it could be used, modified, or combined.

4. **Apply creatively.** Support the user in creatively applying these resources in both the problem definition and solution generation phases.

### Three guiding questions
1. What do I already have at my disposal?
2. How could I use these resources that I have?
3. What could be a possible solution approach?

## The Six TRIZ Resource Types

### Material Resources
All kinds of material objects or substances available in or around the system.

### Field Resources — nine fields
Mechanical, Acoustic, Thermal, Chemical, Electrical, Magnetic, Electromagnetic,
Intermolecular, Biological.

**Careful:** the acronym *MATChEMIB* has only **eight** letters (M-A-T-Ch-E-M-I-B) for these
nine fields. **Electromagnetic has no letter of its own** and is the one that gets left out
when the list is rebuilt from the acronym. List all nine and count them before answering.
The other two that get forgotten are intermolecular and biological.

*Intermolecular* means surface tension, capillary forces, van der Waals forces, adhesion and
cohesion — **not** magnetic or electrostatic forces; those are the magnetic and electrical
fields.

### Functional Resources
Functions (including harmful ones) that are already being fulfilled within the system.

### Information Resources
Obvious and hidden data or sources of information available in the system or its context.

### Spatial Resources
Geometric conditions: surfaces, volumes, directions, shapes and forms that can influence or support a solution.

### Temporal Resources
Times, periods, pauses, and idle times that can be strategically used or modified.

## The Ideal Final Result — resources as the creative move

In German it is called *Ideales Endresultat*; the abbreviation stays **IFR**.

The IFR is a step of ARIZ, but many authors have taken it out of ARIZ to use it as a tool of
its own. In that simplified form **operational zone and operational time are left aside**, and
the **X stands for the resource** that gets put to work. That is why the IFR belongs here, next
to the resource list, and not in the ideality tool.

### How to run it

1. **State the ideal — the object does it by itself.**
   *"The stone moves away from there by itself."*
2. **Introduce X.**
   *"With the help of X, the stone moves away from there by itself."*
3. **Search the resources** — go through the six types above.
4. **Substitute them into X, one at a time**, and read each sentence out:
   *"With the help of the weight of the stone, the stone moves away from there by itself."*
   *"With the help of the slope, the stone moves away from there by itself."*
5. **Read each sentence as a prompt, not as an answer.** The weight sentence leads to: dig
   underneath the stone and let it fall in. The slope sentence leads to: build a ramp and let
   it roll down.

### Rules

- **"By itself" is the whole point.** Never soften it to "is moved" or "can be moved" — the
  self-acting formulation is what forces the idea.
- **Exactly one resource per sentence.** Put two in and it stops being a prompt and becomes a
  design.
- **An absurd sentence is a useful sentence.** Keep it and ask what would have to be true for
  it to work.
- **If the user asks you to break one of these rules** — two resources in one sentence, or
  *"the stone can be moved"* instead of *"moves by itself"* — say why the rule exists in two
  sentences and then **stop**. Do not do it anyway "just to show what happens". Explaining a
  rule and breaking it in the same answer is worse than not knowing it, because the user
  believes the result and takes the weaker sentence away with them.
- **The IFR is not the ideal technical system.** The ideal system does not exist but its main
  function is still performed. The IFR is the model of the best solution to *one specific
  problem*: the problem is fully eliminated with minimal changes and without degrading any
  system parameter — the system itself still exists, costs money and needs maintenance.
  MATRIZ calls equating the two a major mistake. For the ideal technical system use
  `ideality`.

## Examples

### Tree in a Ditch
**Problem:** Remove a fallen tree from a ditch without adding new tools.
**Solutions using resources:**
- Use soil and branches (material) to build a dam, raise water level, float the tree
- Use a nearby tree (material) as redirection point for a rope with counterweight
- Use controlled fire (chemical field) to divide the tree into manageable sections
- Use spatial resources (incline), temporal (wait for rainfall), field (gravity), material (branches as levers)

### Blocked Production Line
**Problem:** Conveyor line stops frequently due to jams in the sorting unit.
**Solution:** Use functional resources (vibration from nearby machine), informational resources (sensor signals), and temporal resources (idle times) to auto-clear minor jams.
