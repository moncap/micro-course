Save as: module4-student-handout.md

# Module 4 Student Handout — Asymmetric Information, Moral Hazard & Adverse Selection
**Weeks 5–6 · Two lectures + Lab 4 + PS4 + tutor session**

## What this module is about
Most economic relationships involve one side knowing or doing something
the other side can't see. This module gives you the two workhorse
problems — hidden action (moral hazard) and hidden information (adverse
selection) — through stories, one fully worked contract, and two live
games you'll play before the theory explains them. You'll derive exactly
how much "skin in the game" an incentive contract needs (it's a number,
not a metaphor), watch a market unravel because of what acceptance
reveals, and confront the gift-exchange puzzle: real workers repay
generous wages with effort that standard theory says they shouldn't
supply. The lab asks a genuinely open question: when silicon workers
reproduce both the textbook AND the behavioral finding, what exactly have
we simulated?

## Session roadmap
- **Lecture 1** opens with a live gift-exchange game (principals offer
  wages, workers choose costly effort — one pair paid for real; results
  sealed until Lecture 2). Then: hidden action vs. hidden information
  through stories; the two-outcome contract solved in full — you'll
  compute the $25 spread that incentive compatibility demands; the
  risk–incentives trade-off; and Safelite's 44% (half incentives, half
  selection).
- **Lecture 2** opens with acquire-a-company: you bid on a firm whose
  value only the seller knows — and most of the class loses money to a
  logic you'll then derive in two lines. Then: adverse selection and the
  positive-correlation test in insurance; the gift-exchange reveal (your
  own Lecture-1 choices vs. Fehr et al.'s labs vs. Gneezy & List's
  fading field gift); and the two-stage design that separates selection
  from incentives. Ends with a live DRY_RUN walk-through of Lab 4.
- **AI tutor session (required this week):** bring one contract,
  monitoring, or screening question from your own research interests.
  The tutor opens with a flawed performance-pay inference for you to
  critique.

## Key concepts in plain language
- **Hidden action vs. hidden information.** Can't see what they *did*
  (moral hazard, after the contract) vs. can't see what they *are*
  (adverse selection, before it). Different problems, different
  experiments.
- **Participation constraint.** The deal, all-in, must beat the outside
  option. Sets the *level* of pay.
- **Incentive constraint.** The extra pay from outcomes effort makes more
  likely must cover effort's cost. Sets the *spread* — skin in the game,
  priced exactly.
- **The risk–incentives trade-off.** Bigger spreads mean stronger
  incentives but load more risk on the worker, who charges for it. The
  optimal contract stops short of full incentives.
- **Adverse selection in one sentence.** The other side's willingness to
  trade is bad news about what you're buying.
- **Gift exchange.** Generous wages buy real effort in one-shot anonymous
  labs (Fehr et al. 1993) — and for about half a workday in the field
  (Gneezy & List 2006). Real, short-lived, context-sensitive.
- **Selection vs. incentives.** A contract changes what workers do AND
  which workers come. Randomize-then-choose designs split the two.

## Lab 4 — Silicon workers under three contracts
**Code:** `module4-simulation-lab.ipynb` (Colab-ready; opens in DRY_RUN
mode — runs end-to-end with no API key on clearly-labeled synthetic data;
set `DRY_RUN = False` for the real run). Design: 3 personas (baseline
worker / money-focused / community-minded — deliberately neutral: a
persona *told* to reciprocate proves nothing) × 3 contracts (flat $10,
flat $25, piece rate $2.50/unit), 30 agents per cell; effort 0–10 against
a posted cost table ($c(e) = e^2/4$; the selfish piece-rate optimum is
e = 5).

**Benchmarks:** the selfish prediction (effort ≈ 0 under any flat wage,
5 under the piece rate) AND the gift-exchange pattern (effort rising in
flat-wage generosity — Fehr, Kirchsteiger & Riedl 1993; fading over a
field workday — Gneezy & List 2006). Plus the class's own Lecture-1 game.

**State your hypotheses before running (your pre-analysis plan):**
- **H1 (incentives):** piece-rate effort lands near the selfish optimum
  of 5.
- **H2 (gift exchange):** effort under flat $25 exceeds effort under
  flat $10.
- **H3 (persona):** the gift-exchange gap varies by persona — commit to a
  direction before looking.

**Required modifications (pick at least one; edit only CHANGE HERE cells):**
1. **Intentions:** add a condition where the flat wage was "set at random
   by the payroll computer" rather than chosen by the employer.
   Reciprocity needs someone to reciprocate — does the gradient collapse?
2. **Hour six:** add "you have been working for six hours" to the
   scenario (the Gneezy–List fade). Does silicon gift exchange decay?
3. **Contract choice:** add a first stage where the agent *picks* its
   contract, then works — selection and incentives, live in silicon
   (mirrors PS4 Part B).

**Robustness section (required):** paraphrased prompt; second model; and
the strip-the-framing run — rewrite the scenario as a mundane shift-work
vignette with no experiment flavor. If gift exchange vanishes, what was
your baseline result made of?

**Write-up:** the standard six sections (question/benchmark → agent design
→ treatments → results vs. humans → divergence diagnosis → design
implication), 3–5 pages plus appendix (prompts, code, results CSV, exact
model string, parse-failure rate). Section 5 must engage the double-match
problem head-on: if your agents produce the textbook result where the
textbook applies and the behavioral result where the behavioral paper
applies, what determined the switch — and is that a model of a worker or
of the literature about workers?

**Grading rubric (20 pts):**

| Pts | Component |
|---|---|
| 4 | Pre-stated hypotheses and clean execution (parse-failure rate reported; prompts logged) |
| 4 | Results presented against BOTH benchmarks (selfish optimum and gift-exchange pattern) |
| 4 | Contract and persona effects analyzed and interpreted, not just tabulated |
| 4 | Divergence diagnosis engages the double-match problem + at least one alternative mechanism, with evidence |
| 4 | Design implication: one concrete improvement to a *human* contract or gift-exchange experiment that this pilot justifies |

## Problem Set 4
`module4-problem-set.tex` / PDF — due before Lecture 1 of Module 5. Part A
works piece rates and the sell-the-job contract ($c(e) = e^2/20$, every
answer clean) and the participation/incentive constraints on fresh
numbers (the spread comes out to $30 — derive, don't copy the lecture's
$25). Part B (heaviest weight, 45 pts) designs the experiment that
decomposes performance pay into incentives and selection. Part C ⟨AI⟩
interprets the agents that matched both literatures at once. Attach AI
transcripts for Part C.

## Readings
**Core (read deeply this week):**
- Fehr, Kirchsteiger & Riedl (1993), "Does Fairness Prevent Market
  Clearing?" *QJE*.
- Lazear (2000), "Performance Pay and Productivity," *AER* — read for the
  decomposition logic and magnitudes.

**Optional / going further:**
- Gneezy & List (2006), "Putting Behavioral Economics to Work,"
  *Econometrica* — the field check.
- Holmström (1979) — the classic source, for PhD-bound students.
- Einav, Finkelstein & Cullen (2010), *QJE* — screening in insurance.
- Course text, chapters on information economics.
- One post-2022 LLM principal–agent or gift-exchange replication —
  assigned in class (verify with instructor).

## Deliverables checklist
- [ ] AI tutor session log + reflection — **[weekly deadline]**
- [ ] Lab 4 write-up (six sections + appendix) — **[one week after Lecture 2]**
- [ ] Problem Set 4 — **[before Lecture 1 of Module 5]**

## Limits of silicon subjects (read before interpreting anything)
The model has read the textbook, Fehr et al., and Gneezy & List — every
pattern it can produce has a recitation explanation, and this module's
lab makes that ambiguity the object of study. Two limits bite harder here
than usual: silicon effort costs nothing (the cost table is words, not
disutility — "skin in the game" has no skin), and persona wording can
smuggle in the conclusion (a "reciprocal" persona reciprocating is a
tautology). The lab keeps personas neutral and asks what makes the
behavior flip; your divergence diagnosis says what that means for a human
study — and what must simply wait for one.
