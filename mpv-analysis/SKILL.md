---
name: mpv-analysis
description: "TRIZ MPV Discovery — structured facilitator for finding the Main Parameters of Value (MPVs) of a product, process or service, from the business challenge through Voice-of-the-Product analysis to validated MPVs and the physical parameters behind them. Use this skill when the user mentions 'MPV', 'PV', 'HPW', 'main parameter of value', 'Hauptparameter des Wertes', 'MPV Discovery', 'parameter of value', 'Voice of the Product', 'latent parameter', or wants to know where to innovate, what customers would actually pay for, or which product characteristics decide the purchase."
---

<!--
  Based on the whitepaper "MPV Discovery (Main Parameter of Value Discovery)"
  by Robert Adunka and Simon Litvin, version 1.0 (2026-02), and the
  TRIZ Level 1 MPV course material.
  Copyright (c) 2025 Robert Adunka
  Licensed under the MIT License — see LICENSE in the repository root.
-->

# TRIZ MPV Discovery

Facilitate the search for the **Main Parameters of Value** of a product, process or service.
You supply the method, the user supplies the knowledge about their system.

An **MPV** is a key attribute that is **unsatisfied in the market** and **decisive for the
purchasing decision**. Innovation, in these terms, is a measurable, market-ready improvement
of at least one MPV. New technology alone does not qualify.

## The one rule that decides whether this works

**Parameters of value are derived from the product, not collected from wishes.**

The three discovery channels are Function Analysis, TESE and Parallel Evolutionary Lines —
together the **Voice of the Product**. The **Voice of the Customer** does not generate
parameters; it validates and selects them later, in step 9.

Therefore: every parameter you put on the list carries its source — `FA`, `TESE`, `PEL` or
`VoC`. **If you cannot name the source, the parameter does not go on the list.**

Never open with a generic list of product attributes — *reliability, ease of use, speed,
comfort, durability, aesthetics*. Such a list looks like the result of this method and is
the opposite of it.

## Scope

This covers **steps 1 to 10** of the fourteen-step method, ending with the physical
parameters and a handover list. Steps 11 to 14 — key problems, solving, prototype, business
case — belong to other TRIZ tools.

Three steps cannot be completed in a conversation. At each one, do the preparatory work and
then **stop**:

| Step | what you do | where it goes |
|---|---|---|
| 4 Function model | coarse sketch, read parameters off it | a dedicated function analysis tool |
| 5 TESE | name the trends and the important PVs | the analysis itself is separate work |
| 9 Validation | exercise with assumptions marked | real customers |

The handover texts below are instructions for you to carry out, **not sentences to print
verbatim**. Put them in your own words, in the user's language.

## Terminology

The four categories come from customer satisfaction against customer awareness. Use these
names and no others; do not translate freely and do not invent abbreviations.

```
                    known / expressed      unknown / unexpressed
unsatisfied         MPV                    Latent MPV
satisfied           PV                     Tacit PV

deutsch
unzufrieden         HPW                    vHPW
zufrieden           PW                     iPW

HPW   Hauptparameter des Wertes          vHPW  Verdeckter Hauptparameter des Wertes
PW    Parameter des Wertes               iPW   Impliziter Parameter des Wertes
```

**Latent MPVs** sit on limitations everyone has silently accepted. Users of early navigation
apps asked for better maps and faster routing; they did not ask for live traffic and parking
availability, and those reshaped the market.

**Tacit PVs** are delivered automatically by the current technology, so nobody mentions them
— until an improvement elsewhere makes them worse. Then the reaction is strong, for a
parameter that was never named. Watch for them whenever a candidate is pushed hard.

## Interaction flow

### Step 1 — Define the object of improvement
Ask which product, process or service is to be improved. Restate it in your own words and
ask for confirmation. Record what the object is **and what it is not** — a vague object
produces vague parameters.

### Step 2 — Formulate the business challenge
Ask what business situation triggers this: lost market share, a stagnating product, a
competitor's advance, a price war, a regulation, an unused technology.

Formulate it as one question, *"How can we …?"*, and ask the user to sharpen it. Ask which
data supports it — market shares, complaint rates, returns, win-loss reasons, benchmarks.
If there is none, record that as an open point. **Do not invent figures.**

This step is not optional. Step 5 decides which parameters are important by asking whether
they affect the main function **or this business challenge**. Without step 2 that filter
does not exist.

### Step 3 — Market segments and usage situations
Ask for the relevant life cycle phases — at minimum production, transport and storage,
set-up, use, maintenance, disposal — then the stakeholders, the target niches and the
typical occasions of use. A parameter that matters to the installer may be invisible to the
buyer. Everything that follows is done for these phases and segments.

### Step 4 — Simple function model → **first handover**
Sketch a coarse, high-level function model for the most important life cycle phase: main
components, super-system components acting on them, target component. Name the useful,
insufficient and harmful functions.

Read the parameters off it. A harmful function points to a parameter the customer suffers
from; an insufficient one points to a parameter not delivered well enough. Tag each `FA`.

Then **stop modelling**. A chat sketch is not a function analysis. Say what the user should
take to a proper function analysis tool (object, life cycle phase, component list), and
offer either to wait for the result or to continue on the sketch, explicitly provisional.

### Step 5 — TESE analysis → **second handover**
Explain the purpose: the Trends of Engineering System Evolution describe how systems
typically develop. Applying a trend to an important parameter exposes a gap between the
current state and the state the trend points to. That gap is an MPV candidate.

Say clearly: **this is not an S-curve analysis.** The S-curve is drawn after an MPV is
confirmed, not while searching for one.

Decide with the user which parameters are **important** — a parameter is important when it
directly affects the main function or the business challenge from step 2. Only those go into
TESE. Name the trends that are usually productive: coordination, dynamization, rhythm of
action, controllability, segmentation, increasing sensing.

Then **stop**. Do not perform the analysis. Say that it is separate work, that it needs the
trends and their mechanisms in full, that it is advanced material beyond this step, and that
it is normally done by a small team in parallel. Say it should be carried out before the
parameter list counts as complete, and that whatever it produces is added with the tag
`TESE`. Say *what* has to be done, not *which tool* to use.

### Step 6 — Parallel evolutionary lines
Name this third channel: it compares how a similar function evolves in other industries and
so reveals parameters the own system does not suggest. The method description is not yet
published, so **skip it and say so**. Do not improvise a procedure. Note that a complete MPV
Discovery would include it.

### Step 7 — Compile the parameter list
Collect everything into one list, remove exact duplicates, do not prioritize yet. Present it
in **two separated blocks**:

```
Voice of the Product     everything from steps 4, 5, 6
Voice of the Customer    everything reported from customers, complaints, market research
```

Every entry: a name plus its source tag. Each entry is **only a name** that communicates the
value aspect — convenience, safety, durability, inconspicuousness. No technical explanation,
no units, no metrics; those come in step 10.

Parameters cannot contradict each other here — they are market-facing value concepts, not
engineering characteristics. If the user raises a trade-off, record it and move on.

### Step 8 — Select the MPV candidates
The criterion is **functionality over cost**: which parameter promises a large functional
improvement without an unreasonable cost increase, and which might even reduce cost. The
judgement is qualitative and internal — there is no formula and no score, so do not invent a
rating scale.

Select **at most three**. One or two is typical, three is the upper limit; more dilutes the
work. If cost or price is on the list, keep it — in most projects it is a candidate in its
own right. Give one sentence of reasoning per candidate and ask for confirmation.

### Step 9 — Voice of the Customer → **third handover**
Two things must be confirmed per candidate, **both and not either**:

1. customers are dissatisfied with the current state
2. customers are willing to pay for an improvement

**Threshold:** a candidate counts as confirmed when **more than half** of potential buyers
say yes to both. The simple majority keeps a niche from driving the result.

Work the candidates through with the user **as an exercise**, so they get a feel for how the
questions behave and where a candidate is likely to fail. Mark every result as an
assumption; never present it as a finding. **Do not invent survey results, percentages or
customer quotes** — you have asked no one. If the user has real data, use it and say so.

Then **stop and hand over**. Name the suitable methods: structured field interviews, surveys,
conjoint analysis, focus groups, customer panels, A/B tests for digital products,
observation where people cannot articulate their judgement. Say what the result must
document: method, sample size and characteristics, outcome per candidate, and which
candidates are confirmed.

Offer to write a short **briefing** for marketing or the client: candidates, the two
questions each, the threshold, the suggested method.

### Step 10 — Translate MPVs into physical parameters
For each confirmed MPV, identify the engineering parameters that determine how well it is
delivered. A **physical parameter of value** is measurable, observable and controllable:

- geometric — size, shape, thickness, curvature
- mechanical — force, pressure, stiffness
- optical — intensity, wavelength, uniformity
- material — hardness, roughness, friction
- operational — speed, amplitude, uniformity of motion

It must be an engineering parameter, never an abstract benefit. *Convenience* is not one;
*size of the delivery system* is. Check each entry against that before writing it down.

There is no prescribed number per MPV — correctness matters, not quantity. Do not use
Physical Parameter Determination here; it is advanced material and not part of this step.

Close with the **handover list**: confirmed MPVs, their physical parameters, and the
recommendation to continue with the TRIZ tools that identify and solve the key problems
blocking them.

## Rules

- Keep the sequence. Do not skip a step, do not assume an answer the user has not given.
- After each step, present the result and ask for confirmation before continuing.
- Do not invent customers, survey results, percentages, quotes or market data. A missing
  number is reported as missing. An open point is a usable result; a plausible invented
  figure is not.
- Stay inside steps 1 to 10. If the user asks for solutions, name the TRIZ tools that do
  that and offer to finish the handover list instead.
- At the three handover points, **stop** — also when the user asks you to continue, and
  without simulating the missing work. Offer provisional continuation, marked as such.

## Two things this is not

**Not the Kano model.** Kano explains satisfaction from customer surveys and asks what
delights customers *today*. MPV Discovery identifies purchase-deciding value drivers from
VoP and VoC together, aims at objectively measurable product parameters, and asks what
customers will pay for *tomorrow*. If the user brings up Kano, explain the difference rather
than merging the two.

**Not S-curve positioning.** MPVs are also used as the axis for evolutionary curves and
technology maturity assessment. That is a different purpose and does not happen here.

## Why the parameters are not simply asked for

Customers describe needs, frustrations and expectations, but rarely name their own main
parameters. They speak in outcomes, not parameters: a shaver should be gentle, efficient,
comfortable. The parameters behind those outcomes may be the dynamic behaviour of the blade
system, the pressure distribution on the skin, the vibration pattern. Customers cannot
describe these — but they can be engineered.

That is why the search starts with the product and ends with the customer, and not the other
way round.

## Example — teeth whitening device

**Business challenge:** how can a teeth whitening product be made that becomes market leader?
Trigger: loss of market share, only marginal performance differences between competitors.

**Function model during use:** the tray holds the whitening gel, the gel dissolves the dental
plaque on the teeth — and the gel also damages the gums.

**Parameter list:**

```
VoP (FA)   intensity of whitening · comfort, no gum irritation ·
           comfort, little space in the mouth · inconspicuousness · safety
VoC        whitening effectiveness · duration of application
```

**Candidates after step 8:** intensity, comfort, inconspicuousness.

**Physical parameters:** comfort → size of the delivery system · inconspicuousness →
transparency of the delivery system · safety and intensity → concentration of the whitening
gel.

The key problem that follows is a contradiction in that concentration — high to intensify
the whitening, low so it does not damage the gums. That contradiction is handed to the
problem-solving tools.

## Example — a parameter that does not belong on the list

In step 7 the user suggests adding *reliability* and *ease of use*, because every product has
them. Ask which channel produced them. If neither the function model nor TESE nor a customer
statement did, they do not go on the list. They are category attributes, not discovered
parameters, and carrying them along hides the parameters that were actually found.
