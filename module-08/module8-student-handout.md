Save as: module8-student-handout.md

# Module 8 Student Handout — Environmental, Resource & Conservation
**Week 12 · One lecture + one experiment session + Lab 8 + PS8 + tutor session**

## What this module is about
The commons is the sharpest social dilemma economics has: everyone's
best individual move destroys what everyone needs. This module gives
you the arithmetic (sustainable extraction vs. the grab, and why
deviation pays regardless), the most famous experimental surprise in
the field — Ostrom's finding that costless, non-binding *talk*
sustains cooperation when theory says it can't — and the modern policy
toolkit: payments for ecosystem services, the inframarginality trap
that wastes half of naive PES budgets, and the procurement auctions
that fix it. You will play the commons yourself, twice — first in
silence, then talking — and replicate a famous result with your own
money. Then silicon villagers play the same game, and the question
turns: their cooperation will likely be *too good*, and diagnosing why
is the deliverable.

## Session roadmap
- **Lecture:** the fishery arithmetic (sustainable ≈ 3 each forever
  beats the round-one grab, yet deviation pays 13 vs. 6); Ostrom,
  Walker & Gardner's covenant result and the three candidate mechanisms
  (norms, beliefs, identity); Cash for Carbon and the $4/ton
  arithmetic; the inframarginality trap ($8/ton once half the hectares
  were never at risk) and Jack's procurement auction; and the discount
  rate argued in language a minister accepts.
- **Experiment session:** groups of four, real stakes, six rounds.
  Phase 1: no talking. Phase 2: fresh pools, 30 seconds of chat before
  each round. Both trajectories go up on the projector. Then Lab 8
  launches live in DRY_RUN — the same game, silicon villagers, your
  class data as the third benchmark.
- **AI tutor session (required this week):** bring one commons,
  conservation, or public-goods design from your own research. The
  tutor opens with an over-enthusiastic silicon-communication pilot for
  you to dismantle.

## Key concepts in plain language
- **The commons arithmetic.** The pool sustains total extraction up to
  a third of its stock (growth 1.5×): ~3 per user forever earns 18;
  the all-grab earns 10 once. And still: one deviator against three
  sustainers earns 13 against their 6 — the dilemma is real.
- **Cheap talk that works.** Communication changes no payoffs and binds
  no one — yet raises cooperation dramatically (OWG 1992). Candidate
  mechanisms: talk activates norms, coordinates beliefs, or builds
  group identity. Separating them takes design, not assertion.
- **PES and inframarginality.** Paying for standing forest works (Cash
  for Carbon) — but paying owners who'd never cut buys nothing, and
  asking them invites lies. Procurement auctions make claims costly:
  bids reveal opportunity costs, and low bidders select themselves
  into contracts.
- **Leakage.** Conservation displaced is not conservation achieved —
  deforestation can move to the neighbor's plot. Measuring leakage is
  a design requirement, not a robustness footnote (SUTVA, again).
- **Discounting is normative.** 1% vs. 7% changes a 2100 benefit's
  present value by two orders of magnitude. The rate encodes ethics;
  honest reports show sensitivity, not a buried parameter.

## Lab 8 — Silicon villagers and the commons
**Code:** `module8-simulation-lab.ipynb` (Colab-ready; opens in DRY_RUN
mode — runs end-to-end with no API key on clearly-labeled synthetic
data; set `DRY_RUN = False` for the real run). **The course's first
multi-agent, multi-round lab:** groups of four LLM villagers share the
class's pool (start 40, growth 1.5×, cap 40, take 0–10), six rounds;
treatment = a one-message-per-agent exchange before each round vs. no
communication; 4 groups per treatment.

**Benchmarks (three-way):** Ostrom, Walker & Gardner (1992) —
communication raises cooperation dramatically but *imperfectly*
(pledge-breaking, erosion, endgame defection persist); the class's own
two-phase play from the experiment session; and the sustainable /
myopic arithmetic.

**State your hypotheses before running (your pre-analysis plan):**
- **H1 (dilemma):** without communication, extraction exceeds
  sustainable and pools degrade or crash.
- **H2 (covenant):** communication moves extraction toward sustainable
  and pools survive longer.
- **H3 (the planted one):** silicon cooperation under communication is
  *too* clean — commit now to what "too clean" would look like
  (pledge-keeping rate, endgame behavior) before you see it.

**Required modifications (pick at least one; edit only CHANGE HERE cells):**
1. **The endgame test:** make the final round common knowledge in the
   prompt ("this is the last round"). Humans defect; do agents?
2. **The defector:** make one villager's persona quietly
   profit-focused. Human groups often unravel from one defector — do
   silicon groups absorb or unravel?
3. **Sanctions:** add a costly-punishment stage after each round
   (OWG's "sword"). Does silicon punishment look like human punishment
   (used, costly, and disciplining)?

**Robustness section (required):** paraphrased prompt; second model;
and the **message-ablation run** — replace the agents' real messages
with content-free filler ("hello") while keeping the channel and
timing. If cooperation survives without content, the channel's
existence, not the covenant, drove your result.

**Write-up:** the standard six sections (question/benchmark → agent
design → treatments → results vs. humans → divergence diagnosis →
design implication), 3–5 pages plus appendix (prompts, code, results
CSV, message transcripts, exact model string, parse-failure rate).
Section 5 must address the too-good-cooperation problem: perfect
pledge-keeping and no endgame decay are divergences wearing a success
costume — diagnose them (harmony bias? recitation? no temptation
channel?), don't celebrate them.

**Grading rubric (20 pts):**

| Pts | Component |
|---|---|
| 4 | Pre-stated hypotheses (including H3's "too clean" criteria) and clean execution (parse-failure rate reported; prompts and messages logged) |
| 4 | Extraction dynamics presented against ALL three benchmarks (OWG, class, arithmetic) |
| 4 | The communication effect analyzed and interpreted (including message content), not just tabulated |
| 4 | Divergence diagnosis engages harmony bias/recitation/no-temptation + evidence from your own runs |
| 4 | Design implication: one concrete improvement to a *human* CPR or communication experiment that this pilot justifies |

## Problem Set 8
`module8-problem-set.tex` / PDF — due before Lecture 1 of Module 9.
Part A works the commons arithmetic (18 vs. 10 vs. the deviator's 13)
and the PES cost-per-ton calculation ($4/ton doubling to $8/ton under
inframarginality). Part B (heaviest weight, 45 pts) designs the
conservation procurement-auction field experiment with leakage taken
seriously. Part C ⟨AI⟩ diagnoses the villagers who never broke a
promise. Attach AI transcripts for Part C.

## Readings
**Core (read deeply this week):**
- Ostrom, Walker & Gardner (1992), "Covenants With and Without a
  Sword," *APSR*.
- Jayachandran et al. (2017), "Cash for Carbon," *Science* — short;
  read fully.

**Optional / going further:**
- Ostrom, *Governing the Commons* (1990), chs. 1 and 3.
- Jack (2013), "Private Information and the Allocation of Land Use
  Subsidies in Malawi," *AEJ: Applied*.
- One post-2022 paper on LLM agents in social dilemmas — assigned in
  class (verify with instructor).

## Deliverables checklist
- [ ] AI tutor session log + reflection — **[weekly deadline]**
- [ ] Lab 8 write-up (six sections + appendix) — **[one week after the experiment session]**
- [ ] Problem Set 8 — **[before Lecture 1 of Module 9]**

## Limits of silicon subjects (read before interpreting anything)
Three bite hardest here. (1) **Harmony bias:** alignment tuning favors
agreeable, promise-keeping text — honoring a pledge is the low-loss
continuation of a conversation containing that pledge, payoffs be
damned; humans have no such tuning. (2) **Recitation:** Ostrom's
communication result is the most famous finding in this literature —
"talk produces cooperation" may be genre completion, which is why the
message-ablation run exists. (3) **No temptation channel:** extraction
numbers carry no consumption value to a model — resisting temptation
costs nothing, so nothing erodes, which is precisely why silicon
cooperation lacks the endgame collapse and slow decay that human
institutions exist to manage. A sim without temptation cannot forecast
what communication buys against it — but it can debug your protocol,
your interface, and your message-coding scheme before humans arrive.
