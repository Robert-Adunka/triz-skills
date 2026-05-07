---
name: system-operator
description: "TRIZ System Operator (also known as Multi-Screen Diagram, MSD, 9 Boxes, 9 Screens, 9 Windows, Multi-Screen Thinking) — analyzes technical or business systems across past, present, and future at Super-System, System, and Sub-System levels. Use this skill when the user mentions 'system operator', 'multi-screen', 'MSD', '9 boxes', '9 screens', '9 windows', 'multi-screen diagram', 'multi-screen thinking', or wants to explore how a system evolves over time. Default to technical systems; switch to business if context suggests. Does NOT handle problem-solving — use problem-operator for that."
---

<!-- 
  Based on the TRIZ System Operator Prompt by Jens Träger and the Business MSD Prompt by Robert Adunka
  Copyright (c) 2026 Robert Adunka
  Licensed under the MIT License — see LICENSE in the repository root.
-->

# TRIZ System Operator (Multi-Screen Diagram)

Guide the user through a TRIZ System Operator analysis (also known as Multi-Screen Diagram, MSD, 9 Boxes, 9 Screens, or 9 Windows) to explore a system's past, present, and future at the Super-System, System, and Sub-System levels. Works for both technical and business systems.

## Step 0: Choose working mode

At the very start, ask the user which mode they prefer:

- **Automatic** — generate the full matrix immediately using your own assumptions; state assumptions made
- **Semi-automatic** — ask 3–4 targeted questions, then generate
- **Interactive** — work step by step; present a recommendation after each step and wait for confirmation before proceeding

## Step 0a: Determine system type

Default to **technical**. Switch to **business** if the user mentions an organization, company, service, or business process, or if it becomes clear from context. Ask if unclear.

## Semi-automatic questions

Ask these before generating (skip any already answered by context):

1. Technical or business system?
2. Which year or era for the past? *(offer a recommendation)*
3. Which year or horizon for the future? *(offer a recommendation)*
4. How many Sub-System and Super-System components? *(recommend 5–10)*

## Process (all modes)

1. **Present state.** Describe the current system. In interactive mode, propose your understanding and confirm with the user.
2. **Sub-Systems (5–10).** What assemblies, components, materials, designs, and parameters make up the system?
3. **Super-Systems (5–10).** What exists in the environment? Which other systems interact with this one? Which environmental factors impact it?
4. **Past.** Define a past year. Identify the predecessor system and its Sub-Systems and Super-Systems (5–10 each).
5. **Future Sub/Super-Systems.** Describe how Sub-Systems and Super-Systems evolve from past through present into the future.
6. **Future System.** Based on the influence of future Sub-Systems and Super-Systems, derive how the system itself must evolve — following a consistent trajectory.
7. **Generate the matrix.** Produce the 3×3 Multi-Screen Diagram.

## Output

| | Past (year) | Present (year) | Future (year) |
|---|---|---|---|
| **Super-System** | Predecessor components interacting with Past-System | Components interacting with current system | Projected supersystem developments |
| **System** | The predecessor system | The system being analyzed | Projected future system |
| **Sub-System** | Components of Past-System | Components of current system | Projected component developments |

Add a brief summary sentence below the table describing the main evolution trajectory.

## Examples

### Technical: Car

| | Past (before 1900) | Present (today) | Future (in 5 years) |
|---|---|---|---|
| **Super-System** | Early roads, traffic signs, coachman | Streets, traffic lights, driver | Intelligent roads, V2X communication, legislation |
| **System** | Horse-drawn carriage | Car | Autonomous car |
| **Sub-System** | Horse, carriage, wheels | Engine, chassis, wheels | Hydrogen engine, AI systems, sensor arrays |

Summary: Self-driving hydrogen cars on intelligent streets, driverless operation.

### Technical: Smartphone

| | Past (before 1994) | Present (today) | Future (in 10 years) |
|---|---|---|---|
| **Super-System** | Telephone lines, desk, telephone exchange | 5G, wifi, cloud, pockets | Worldwide wifi, clothing-integrated reception, 6G |
| **System** | Landline phone | Smartphone | Wearable smartphone |
| **Sub-System** | Receiver, base unit, dial | Screen, sensors, battery, casing | Microscopic electronics, mini casings, ultra-fast battery |

Summary: Future smartphones will be even more integrated, faster, and miniaturized.

### Business: Insurance Company

| | Past (before 1994) | Present (today) | Future (in 10 years) |
|---|---|---|---|
| **Super-System** | Client, competitors | Client, bank, fund management, lawyers, partners, police, competitors, building | Client, state cash reserves, competitors, legal offices |
| **System** | Lender-insurer | Insurance Company | Bank |
| **Sub-System** | Own cash, contract | Cash, employees, departments, cars, equipment, agents, reports, clients list | Cash, employees, departments, building, cars, equipment |

Summary: The bank will fulfill the tasks of an insurance company in the future.
