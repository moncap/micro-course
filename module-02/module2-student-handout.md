Save as: module2-student-handout.md

# Module 2 Student Handout — Consumer Theory, Demand & Welfare
**Week 3 · Two lectures + Lab 2 + PS2 + tutor session**

## What this module is about
Consumer theory is the part of micro you will actually *use* every time you
value anything: a program, a price change, a product, an environmental
amenity. This module builds demand from budget lines and indifference
curves, teaches the one decomposition every applied economist needs
(income vs. substitution), and then gets honest about measurement: how to
elicit willingness to pay so that people have a reason to tell the truth,
why buyers and sellers of the same mug report values that differ by a
factor of two, and why "the welfare cost" of a policy is not one number.
The lab audits a population of silicon consumers for rationality — and
plants a question about what it means if they pass too well.

## Session roadmap
- **Lecture 1** opens with you spending a $20 budget on four different
  price menus (your choices become the class dataset). Then: demand as
  tangency with a worked example where every number is whole; the Slutsky
  decomposition on one diagram (price drop → substitution +1, income +1);
  and a live revealed-preference audit of the class's own choices, matched
  against how humans do in the literature (~90% consistent).
- **Lecture 2** opens with the mug market: half of you own one and state a
  selling price, half state a buying price — for real. Then: why BDM makes
  honesty optimal, the reveal of the class's WTP–WTA gap next to the
  famous 2:1 result, and welfare measurement with numbers: CV, EV, and
  consumer surplus, when they coincide (quasi-linearity), when they don't,
  and which question each answers. Ends with a live DRY_RUN walk-through
  of Lab 2.
- **AI tutor session (required this week):** bring one valuation or
  demand-measurement instrument from your own research interests. The
  tutor opens with a flawed transit-fare welfare study for you to
  critique.

## Key concepts in plain language
- **Demand = tangency.** The rate you'd trade (your MRS) equals the rate
  you can trade (the price ratio). Everything else is bookkeeping.
- **Income vs. substitution effects.** A price drop makes the good
  relatively cheaper (substitution) *and* makes you richer (income). Two
  effects, one observed response — and policies differ in which channels
  they use, so experiments must separate them.
- **Revealed preference (WARP/GARP).** If you chose A when B was
  affordable, choosing B when A is affordable is a contradiction. It's a
  consistency audit you can run on any budget-choice data — humans pass
  ~90% of the time, not 100%.
- **Incentive-compatible elicitation (BDM/Vickrey).** A random price you
  can't influence makes your stated value only determine *which deals
  count for you* — so honesty is your best strategy. Hypothetical WTP has
  no such discipline.
- **The WTP–WTA gap.** Sellers of a mug ask ~2× what buyers offer.
  Leading account: loss aversion. Honest caveat: part of the gap fades
  with training and mechanism comprehension.
- **CV vs. EV vs. consumer surplus.** "How much must we compensate
  losers?" (CV, at new prices) and "what would they pay to avoid it?"
  (EV, at old prices) are different numbers unless utility is
  quasi-linear. The question picks the measure.

## Lab 2 — Silicon consumers: demand, framing, and a GARP audit
**Code:** `module2-simulation-lab.ipynb` (Colab-ready; opens in DRY_RUN
mode — runs end-to-end with no API key on clearly-labeled synthetic data;
set `DRY_RUN = False` for the real run). Design: 3 personas (baseline /
variety-lover / coffee-devotee) × 2 framings (plain prices vs. "on sale at
half the usual price" with identical final prices), 30 agents per cell;
each agent answers all four class menus in one prompt.

**Human benchmarks:** Andreoni & Miller (2002): ~90% of subjects
GARP-consistent. Choi et al. (2007): high but imperfect consistency, with
meaningful heterogeneity. Downward-sloping demand. Plus the class's own
Lecture-1 menu choices for the three-way comparison.

**State your hypotheses before running (your pre-analysis plan):**
- **H1 (demand):** average coffee purchases fall with its price across
  menus (downward-sloping aggregate demand).
- **H2 (framing):** "sale" framing raises coffee purchases at identical
  final prices (a reference-dependence effect standard theory says
  shouldn't exist).
- **H3 (consistency):** the per-agent WARP violation rate is in the human
  ballpark (~10%) — commit to this before you look; the interesting
  outcomes are both directions of failure.

**Required modifications (pick at least one; edit only CHANGE HERE cells):**
1. **Reference-price persona:** add a persona described as knowing the
   "usual price" of coffee and hating to overpay. Does it amplify the
   framing effect?
2. **Make GARP bind:** add a fifth menu chosen so that consistency
   requires checking a *chain* of comparisons, not just pairs (guidance in
   the notebook comments).
3. **Trace the demand curve:** replace the four menus with coffee at
   {$2, $3, $4, $5} and pastry fixed at $2; plot mean coffee quantity
   against price.

**Robustness section (required):** paraphrased prompt; second model; and
**non-round prices** ($3.70/$2.30) — if agent consistency collapses when
the arithmetic stops being easy, what was the consistency made of?

**Write-up:** the standard six sections (question/benchmark → agent design
→ treatments → results vs. humans → divergence diagnosis → design
implication), 3–5 pages plus appendix (prompts, code, results CSV, exact
model string, parse-failure rate). Section 5 must take a position on the
planted question: if your agents are *more* consistent than humans, that
is a divergence — diagnose it, don't celebrate it.

**Grading rubric (20 pts):**

| Pts | Component |
|---|---|
| 4 | Pre-stated hypotheses and clean execution (parse-failure rate reported; prompts logged) |
| 4 | Demand and framing results presented against the human benchmarks |
| 4 | The WARP audit analyzed and interpreted, not just tabulated |
| 4 | Divergence diagnosis engages the too-consistent question + at least one alternative mechanism, with evidence |
| 4 | Design implication: one concrete improvement to a *human* budget-choice or valuation experiment that this pilot justifies |

## Problem Set 2
`module2-problem-set.tex` / PDF — due before Lecture 1 of Module 3. Part A
walks you through Cobb–Douglas demand and the Slutsky decomposition (every
effect is a whole number) and the CV/EV/CS calculation (the trapezoid is
28). Part B (heaviest weight, 45 pts) asks you to design the experiment
that separates the endowment effect from mechanism confusion. Part C ⟨AI⟩
interprets the agents that came back too rational. Attach AI transcripts
for Part C.

## Readings
**Core (read deeply this week):**
- Kahneman, Knetsch & Thaler (1990), "Experimental Tests of the Endowment
  Effect and the Coase Theorem," *JPE*.
- Andreoni & Miller (2002), "Giving According to GARP," *Econometrica* —
  read for the method; the social-preference content returns in Module 5.

**Optional / going further:**
- Becker, DeGroot & Marschak (1964) — the original BDM note, short.
- Choi, Fisman, Gale & Kariv (2007), *AER*.
- Course text, chapters on consumer theory and welfare.
- A Plott–Zeisel-style critique of WTP–WTA experiments — assigned in class
  (verify with instructor).
- One post-2022 paper on LLM consumer behavior or GARP tests on LLMs —
  assigned in class (verify with instructor).

## Deliverables checklist
- [ ] AI tutor session log + reflection — **[weekly deadline]**
- [ ] Lab 2 write-up (six sections + appendix) — **[one week after Lecture 2]**
- [ ] Problem Set 2 — **[before Lecture 1 of Module 3]**

## Limits of silicon subjects (read before interpreting anything)
The model has read every consumer-theory textbook and the endowment-effect
literature; no budget is real to it (nothing is forgone when it "spends");
and its behavior can shift under paraphrase. This module adds a new limit
with its own lesson: **an agent that never errs is not a model of an agent
who rarely errs.** Human data includes the error process — attention,
fatigue, imprecision — and several things you might pilot (rationality
screens, attrition, comprehension rates) depend on exactly that process.
The robustness section measures what silicon consistency is made of; your
divergence diagnosis says what that means for the human study.
