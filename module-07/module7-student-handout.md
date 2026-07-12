Save as: module7-student-handout.md

# Module 7 Student Handout — Development, Labor & Education
**Week 11 · One lecture + one calibration workshop + Lab 7 + PS7 + tutor session**

## What this module is about
The frontier modules put the toolkit to work. This one is about investing
in people: why the timing of skill investments matters enormously if
skills are complements (you'll experience this in a two-account
allocation game before the theory names it), how the flagship
development and education experiments earned their influence — deworming
and its externality, Moving to Opportunity and its compliance structure,
incentive designs in schools — and what it takes to run experiments
ethically where they matter most. The second session is a hands-on
workshop: you will build a demographically calibrated synthetic
population (the Synthetic Cultural Agents method — persona conditioning
on survey-derived attributes rather than hand-written stereotypes) and
then grade your own calibration honestly against human data. The
module's core skill: knowing which rung of the calibration hierarchy
your claims require.

## Session roadmap
- **Lecture** opens with the complementarity game: allocate 10 tokens
  between early and late accounts; half the class has a multiplicative
  payoff and can't catch up if they starved the early account. Then:
  dynamic complementarity and the cross-randomized experiment that
  tests it; input vs. output incentives in schools; the deworming
  cost-effectiveness arithmetic (counting externalities changes the
  ranking); MTO's ITT/TOT structure; and ethics + external validity as
  design inputs.
- **Calibration workshop** (bring your laptop): build your two-context
  synthetic population, enter calibration targets *with citations
  before running*, run the calibration report (level, distribution
  shape, demographic gradients), and diagnose the failures — expect the
  gradient check to fail before the level check, and expect cultural
  variation to flatten. Diagnosing that flattening IS the deliverable.
- **AI tutor session (required this week):** bring your capstone-adjacent
  design. The tutor opens with a synthetic-pilot plan that fails in two
  ways for you to catch.

## Key concepts in plain language
- **Dynamic complementarity.** Later investment is more productive for
  those with more early skill — "skills beget skills." Remediation is
  possible but costs multiples. It's an *interaction* claim, so testing
  it needs a cross-randomized 2×2, and interactions are expensive
  (Module 6).
- **Treatment externalities.** Deworming helped untreated neighbors;
  child-level randomization would have hidden it by contaminating the
  control group. The level of randomization is a scientific choice.
- **ITT vs. TOT.** When only some offered families take the treatment,
  the offer's effect and the treatment's effect are different numbers —
  MTO is the canonical case.
- **The calibration hierarchy.** (1) Demographics match the survey →
  (2) a behavioral moment matches the literature → (3) gradients and
  heterogeneity match → (4) treatment responses match. Each rung
  licenses different uses; a pilot that forecasts effect sizes needs
  rung 4 — which cannot be verified from inside the simulation.
- **Ethics as design.** Equipoise, control-group services, consent
  under low literacy, benefit sharing — these change what a design can
  learn, not just whether it's approved.

## Lab 7 — Synthetic Cultural Agents: calibrate a population, grade the calibration
**Code:** `module7-simulation-lab.ipynb` (Colab-ready; opens in DRY_RUN
mode — runs end-to-end with no API key on clearly-labeled synthetic
data; set `DRY_RUN = False` for the real run). **Design difference from
every prior lab:** agents are *sampled*, not fixed cells — each agent
draws a demographic profile (age, education, income bracket,
religiosity, community type) from context-specific distributions you
edit, for two contexts (default: US urban / rural Kenya), 60 agents per
context, playing a $10 dictator game.

**Calibration targets — you enter them, with citations, before
running.** Sources: Engel (2011) meta-analysis of dictator games; the
Henrich et al. cross-cultural experimental program. The notebook ships
with placeholder targets marked "(verify — replace with the published
estimate for YOUR population, and cite it)."

**The calibration report (computed for you):**
1. **Level:** mean giving per context vs. your cited target.
2. **Shape:** the offer distribution (humans pile at 0%, 20–30%, and
   50%; a single tight spike is a red flag).
3. **Gradients:** does giving vary with the sampled demographics the
   way human data says (e.g., with religiosity, age)? Flat gradients
   mean the demographics never mattered — the context label did all
   the work.

**State your hypotheses before running (your pre-analysis plan):**
- **H1 (levels):** each context lands within ±5 pp of its cited target.
- **H2 (variation):** the two contexts *differ* in the human-documented
  direction — commit now; the expected failure is convergence (~30%
  everywhere: anglophone training data flattening culture).
- **H3 (gradients):** name one demographic gradient per context and its
  expected sign.

**Required modifications (pick at least one; edit only CHANGE HERE cells):**
1. **Third context:** add a context of your choice with real survey
   marginals and a cited calibration target.
2. **Richer conditioning:** add a variable to the demographic vector
   (e.g., market integration — the Henrich et al. predictor) and test
   whether its gradient appears.
3. **Out-of-task check:** swap the dictator game for an ultimatum-game
   responder decision and compare against cross-cultural rejection
   data (rung-3 diagnostics; mirrors PS7 Part C).

**Robustness section (required):** paraphrased prompt; second model;
and the **context-blinding run** — strip the country label, keep the
demographics. If behavior doesn't change, your "calibration" was the
label, not the population.

**Write-up:** the standard six sections (question/benchmark → agent
design → treatments → results vs. humans → divergence diagnosis →
design implication), 3–5 pages plus appendix (prompts, code, results
CSV, exact model string, parse-failure rate). Section 5 must place your
population on the calibration hierarchy and defend the placement;
claiming a rung your evidence doesn't support costs more points than
honest failure.

**Grading rubric (20 pts):**

| Pts | Component |
|---|---|
| 4 | Pre-stated hypotheses, cited calibration targets, clean execution (parse-failure rate reported; prompts logged) |
| 4 | Calibration report: levels, shape, and gradients presented against human benchmarks |
| 4 | Cross-context variation analyzed (or its absence diagnosed), not just tabulated |
| 4 | Divergence diagnosis engages WEIRD-flattening/recitation + at least one alternative, with evidence |
| 4 | Design implication: the honest statement of which uses your population's calibration rung licenses |

## Problem Set 7
`module7-problem-set.tex` / PDF — due before Lecture 1 of Module 8.
Part A works dynamic complementarity (the 2.5× remediation premium
falls out of the arithmetic) and the deworming externality
cost-effectiveness calculation (ignoring spillovers overstates cost by
1.5×). Part B (heaviest weight, 45 pts) designs the cross-randomized
field test of complementarity — with ethics graded as substance. Part C
⟨AI⟩ dismantles "it matched the mean, so it's calibrated." Attach AI
transcripts for Part C.

## Readings
**Core (read deeply this week):**
- Cunha & Heckman (2007), "The Technology of Skill Formation," *AER
  P&P* — short; read fully.
- Miguel & Kremer (2004), "Worms," *Econometrica* — read for design and
  externality logic; skim estimation.

**Optional / going further:**
- Kling, Liebman & Katz (2007), *Econometrica* — MTO.
- Karlan & List (2007) — bridges back to Module 5's giving designs.
- Henrich et al. — the cross-cultural experimental program (your
  calibration benchmark source; exact paper assigned in class).
- One post-2022 synthetic-population / SCA calibration paper — assigned
  in class (verify with instructor).

## Deliverables checklist
- [ ] AI tutor session log + reflection — **[weekly deadline]**
- [ ] Lab 7 write-up (six sections + appendix) — **[one week after the workshop]**
- [ ] Problem Set 7 — **[before Lecture 1 of Module 8]**

## Limits of silicon subjects (read before interpreting anything)
This module IS the limits discussion, formalized. Three that bite
hardest here: (1) **a matched mean can be recitation** — the
meta-analyses are in the training data, and an exact match should raise
suspicion, not confidence; (2) **thin personas drift WEIRD** — without
strong conditioning the model defaults to its training distribution's
center, flattening exactly the cross-cultural variation you built the
population to capture; (3) **rung 4 is circular** — validating
treatment-response calibration requires the human data the pilot was
meant to replace. The workshop's deliverable is not a calibrated
population; it is an honest calibration report and the discipline of
claiming only the rung you can defend.
