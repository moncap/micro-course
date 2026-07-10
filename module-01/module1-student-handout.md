Save as: module1-student-handout.md

# Module 1 Student Handout — Rational Choice, Preferences & Uncertainty
**Weeks 1–2 · Two lectures + Lab 1 + PS1 + tutor session**

## What this module is about
This is where the course's method gets established: you make choices first,
then the theory explains them — or fails to, in an interesting way. You
will produce the two most famous anomalies in decision theory (Allais and
Ellsberg) with your own answers before you learn their names, learn to
compute with expected utility on concrete numbers, and learn the
measurement discipline the whole course runs on: *what does this instrument
measure, and why would the subject answer honestly?* The module ends with
your first silicon experiment: do LLM agents reproduce the class's own
choice anomalies — and should anyone be impressed if they do?

## Session roadmap
- **Lecture 1** opens with four choices on your phone (one pays real
  money). Then: what rationality actually assumes (less than you think —
  the money-pump argument), expected utility with numbers that come out
  round, and the reveal: the class's own Allais and Ellsberg patterns, plus
  the Holt–Laury list as the workhorse risk-measurement tool.
- **Lecture 2** opens with a real BDM auction (bring your willingness to
  pay for a mug). Then: why truth-telling is optimal in BDM and where the
  argument breaks; whether anomalies survive real stakes (game shows,
  high-stakes village experiments); and a two-picture preview of prospect
  theory before Module 5 builds it properly. Ends with a live DRY_RUN
  walk-through of Lab 1.
- **AI tutor session (required this week):** bring one risky-choice
  measurement from your own research interests. The tutor opens with a
  flawed willingness-to-pay elicitation for you to critique. Log + short
  reflection due per the standard weekly deadline.

## Key concepts in plain language
- **Rationality = completeness + transitivity.** Nothing about selfishness.
  A violator of transitivity can be turned into a money pump — that's the
  behavioral content.
- **Utility is a ranking device.** The numbers have no units; "twice the
  utility" means nothing; comparisons across people are off the table.
- **Expected utility and the risk premium.** Curvature is risk aversion.
  A √-utility agent will pay $25 to avoid a 50/50 $100-or-nothing gamble —
  compute it once by hand and the concept is yours.
- **The independence axiom.** Adding the same ingredient to both sides of
  a choice shouldn't flip it. The Allais questions show most people flip —
  systematically, in one direction (the certainty effect).
- **Ambiguity aversion (Ellsberg).** Unknown probabilities are treated as
  hostile — a different violation than Allais, and present in any field
  setting where subjects don't know the odds.
- **Incentive-compatible elicitation.** Holt–Laury lists and BDM make
  honesty optimal *for a specific kind of agent* — the fine print of that
  "for" is a running theme of the course.

## Lab 1 — Replicating choice anomalies with persona-varied agents
**Code:** `module1-simulation-lab.ipynb` (Colab-ready; opens in DRY_RUN
mode — runs end-to-end with no API key on clearly-labeled synthetic data;
set `DRY_RUN = False` for the real run). Design: 3 personas (baseline /
cautious / gambler, plain behavioral language) × 2 stakes framings
(hypothetical high stakes vs. scaled real-payment language), 30 decisions
per cell, fixed temperature, all prompts logged.

**Human benchmarks:** Kahneman & Tversky (1979): 82% chose the certain
option in Q1, 83% the long shot in Q2 — so at least 65% chose the
EU-inconsistent pair. Plus the class's own Lecture-1 choices: your write-up
makes the **three-way comparison** — literature vs. this class vs. silicon.

**State your hypotheses before running (your pre-analysis plan):**
- **H1 (aggregate):** the modal silicon pattern is the human one — certain
  option in Q1, long shot in Q2 (an EU violation).
- **H2 (persona sensitivity):** the violation rate moves with persona
  wording (e.g., "gambler" personas choose the risky option in Q1 more
  often).
- **H3 (stakes framing):** real-payment language shifts choices toward
  EU-consistency (or doesn't — commit before you look).

**Required modifications (pick at least one; edit only CHANGE HERE cells):**
1. **Scale the stakes:** $2400 → $24. Does the certainty effect survive
   when the numbers stop looking like the textbook's?
2. **Add a loss-averse persona** described in plain language (no Greek
   letters — the design note in the notebook explains why). Does the Q1
   certainty share rise?
3. **Swap in a Holt–Laury list:** replace the two Allais questions with a
   10-row choice list (rows provided in the notebook comments); parse the
   switch row and compare to the human modal switch (rows 5–6).

**Robustness section (required):** paraphrased prompt; second model; and
the "economist persona" run — tell the agent it is an economist and see
whether the anomaly vanishes. If it does, what was your baseline result
made of?

**Write-up:** the standard six sections (question/benchmark → agent design
→ treatments → results vs. humans → divergence diagnosis → design
implication), 3–5 pages plus appendix (prompts, code, results CSV, exact
model string, parse-failure rate). Section 5 must engage training-data
contamination directly: KT79 is in every textbook the model has read — is a
match fidelity or recitation, and what in *your* data speaks to it?

**Grading rubric (20 pts):**

| Pts | Component |
|---|---|
| 4 | Pre-stated hypotheses and clean execution (parse-failure rate reported; prompts logged) |
| 4 | Results presented against BOTH benchmarks (KT79 and the class's own choices) |
| 4 | Persona and framing effects analyzed and interpreted, not just tabulated |
| 4 | Divergence diagnosis engages contamination + at least one alternative mechanism, with evidence |
| 4 | Design implication: one concrete improvement to a *human* choice experiment that this pilot justifies |

## Problem Set 1
`module1-problem-set.tex` / PDF — due before Lecture 1 of Module 2. Part A
walks you through expected-utility calculations with √-utility (every
number comes out round) and the Allais algebra in guided steps. Part B
(heaviest weight, 45 pts) asks you to design the experiment that tests
whether the certainty effect survives real incentives. Part C ⟨AI⟩
interprets a suspiciously perfect silicon replication. Attach AI
transcripts for Part C.

## Readings
**Core (read deeply this week):**
- Kahneman & Tversky (1979), "Prospect Theory," *Econometrica* — read for
  the experiments and the ideas; skim the formal sections.
- Holt & Laury (2002), "Risk Aversion and Incentive Effects," *AER*.

**Optional / going further:**
- Allais (1953); Ellsberg (1961) — the originals.
- Course text, chapter on choice under uncertainty.
- Tversky & Kahneman (1992) — where Module 5 goes.
- One post-2022 LLM choice-anomaly replication — assigned in class (verify
  with instructor).

## Deliverables checklist
- [ ] AI tutor session log + reflection — **[weekly deadline]**
- [ ] Lab 1 write-up (six sections + appendix) — **[one week after Lecture 2]**
- [ ] Problem Set 1 — **[before Lecture 1 of Module 2]**

## Limits of silicon subjects (read before interpreting anything)
The model has read every behavioral economics textbook, including the exact
experiments you are replicating; it faces no real stakes; its "personas"
are prompt text, not preferences; and its behavior can shift under
paraphrase. Lab 1 treats these as research questions — the robustness
section exists to measure them, and your divergence diagnosis exists to
reason about them. A silicon replication that matches Kahneman & Tversky is
*not* validated, and one that diverges is *not* useless: either way, the
deliverable is a mechanism and the design change it implies for a human
study.
