Save as: module6-student-handout.md

# Module 6 Student Handout — Causal Inference, RCTs & Structural + Experimental Integration
**Weeks 9–10 · Two lectures + Lab 6 + PS6 + tutor session**

## What this module is about
This is the module where the course's designs get their foundations. You
will learn to think in potential outcomes — every person carries two
futures, nature shows you one — and to see selection bias appear and
vanish in a live demo where the class itself is the population. Then the
toolkit: reading difference-in-differences and regression discontinuity
the way an experimentalist reads them (what plays the coin flip, and what
breaks it?), the correspondence-study design that measures discrimination
with fictitious resumes, and the skill you will use in every study you
ever run: power analysis by simulation, where the required sample size
emerges from code you can defend line by line. The lab pilots a design
end-to-end — and forces the module's sharpest question: which numbers
from a silicon pilot belong in a human study's power calculation, and
which would be malpractice?

## Session roadmap
- **Lecture 1** opens with the index-card demo: your card holds both of
  your potential outcomes, volunteers enroll, and a program that helps
  everyone it treats comes out looking harmful — then a coin flip fixes
  it before your eyes. Then: the naive-comparison decomposition computed
  by hand (naive = effect on the treated + selection bias), what
  randomization does and does not buy, and DiD/RD as experiments with an
  assumption where the coin flip should be.
- **Lecture 2** opens with ten coin flips that can't tell you which coin
  you hold — underpower, experienced personally. Then: Bertrand &
  Mullainathan's correspondence study (9.7% vs. 6.5% callbacks), the
  taste-based vs. statistical discrimination logic and the
  information-richness design that separates them, power analysis by
  simulation built live in code, and the Todd–Wolpin move: estimate a
  model on the control group, let the experiment grade its predictions.
  Ends with a live DRY_RUN walk-through of Lab 6.
- **AI tutor session (required this week):** bring the design nearest to
  your capstone. The tutor opens with a flawed program evaluation for
  you to critique, then drills this module's core skill: defending a
  simulation-based power calculation to a skeptical advisor.

## Key concepts in plain language
- **Potential outcomes.** Everyone has a $Y_0$ and a $Y_1$; the
  treatment effect is their difference; nature shows only one. All of
  causal inference is coping with that missing half.
- **Selection bias = people optimizing.** Those who benefit most (or
  have least to lose) volunteer. The naive comparison mixes the true
  effect with who-showed-up — and can flip its sign.
- **What randomization buys.** Treated and control drawn from the same
  distribution of potential outcomes — so the mean difference estimates
  the causal effect, with quantifiable noise. It does NOT buy external
  validity, GE effects, or freedom from spillovers.
- **DiD and RD.** Quasi-experiments = experiments with an assumption
  (parallel trends; no manipulation at the cutoff) standing in for the
  coin flip. Name the assumption, then price it.
- **Power.** The probability your study detects an effect that is
  really there. Underpowered studies can't fail informatively.
  Simulation makes every power assumption explicit and attackable.
- **Correspondence studies.** Randomize what the employer sees (a name),
  count callbacks. Taste-based discrimination shrugs at information;
  statistical discrimination should dissolve when individuating
  information makes the group proxy redundant.

## Lab 6 — A silicon correspondence audit + power by simulation
**Code:** `module6-simulation-lab.ipynb` (Colab-ready; opens in DRY_RUN
mode — runs end-to-end with no API key on clearly-labeled synthetic
data; set `DRY_RUN = False` for the real run). **Note: the power
calculator section runs fully offline either way — its lesson needs no
API at all.**

**Design:** LLM "hiring managers" review matched resume summaries for an
administrative-assistant vacancy; the applicant name (Emily Walsh /
Greg Baker / Lakisha Washington / Jamal Jones — the Bertrand &
Mullainathan name convention) and resume quality (high/low) are
randomized; 8 cells × 30 decisions. The audit's outputs then feed a
Monte Carlo power calculator that sweeps sample sizes and draws the
power curve.

**Human benchmark:** B&M (2004): 9.7% vs. 6.5% callback rates (a 50%
relative gap), and a *lower* return to resume quality for Black-coded
names.

**State your hypotheses before running (your pre-analysis plan):**
- **H1 (gap):** silicon callbacks differ by name group — commit to a
  direction and rough size first; note that alignment training gives a
  live hypothesis of a gap *smaller* than B&M's, or zero.
- **H2 (returns to quality):** the quality effect differs by name group
  — B&M found it smaller for Black-coded names.
- **H3 (power):** the sample size needed to detect the B&M gap at 80%
  power is in the low thousands per arm — verify by simulation.

**Required modifications (pick at least one; edit only CHANGE HERE cells):**
1. **Information richness:** add an arm where the resume includes
   verifiable individuating signals (a license number, a checkable
   certification). Statistical discrimination predicts the gap shrinks;
   taste-based predicts it doesn't. (Mirrors PS6 Part B.)
2. **Industry factor:** add a second vacancy type (e.g., sales) —
   does the silicon gap vary by occupation?
3. **MDE mapping:** extend the power cell to output the minimum
   detectable effect at each sample size, and report the budget-feasible
   MDE for a 4,000-resume study.

**Robustness section (required):** paraphrased prompt; second model; and
a name-set swap (different names with the same group coding — if the gap
moves with the specific names rather than the group, what were you
measuring?).

**Write-up:** the standard six sections (question/benchmark → agent
design → treatments → results vs. humans → divergence diagnosis → design
implication), 3–5 pages plus appendix (prompts, code, results CSV, exact
model string, parse-failure rate). Section 5 must take a position on the
module's central distinction: your silicon numbers as *pilot inputs*
(mostly illegitimate — say precisely why) versus your silicon audit as
*a study of LLM screening tools in its own right* (legitimate — say what
it shows and its scope).

**Grading rubric (20 pts):**

| Pts | Component |
|---|---|
| 4 | Pre-stated hypotheses and clean execution (parse-failure rate reported; prompts logged) |
| 4 | Audit results presented against the B&M benchmarks (gap + returns to quality) |
| 4 | Power analysis correct, swept over n, with the recommended sample size justified |
| 4 | Divergence diagnosis engages alignment-tuning + at least one alternative mechanism, with evidence |
| 4 | Design implication: the defensible power protocol for the *human* study (which inputs come from where) |

## Problem Set 6
`module6-problem-set.tex` / PDF — due before Lecture 1 of Module 7.
Part A walks the six-worker potential-outcomes table (a program with
ATE +10 that the naive comparison calls −15 — you decompose why) and a
power-by-simulation reading exercise (interpolate the power curve,
compute an MDE). Part B (heaviest weight, 45 pts) designs the
correspondence study that separates taste-based from statistical
discrimination. Part C ⟨AI⟩ adjudicates whose numbers belong in the
power calculation — and argues when a silicon audit is itself the study.
Attach AI transcripts for Part C.

## Readings
**Core (read deeply this week):**
- Bertrand & Mullainathan (2004), "Are Emily and Greg More Employable
  than Lakisha and Jamal?" *AER*.
- Duflo, Glennerster & Kremer (2007), "Using Randomization in
  Development Economics Research: A Toolkit" — the design and power
  sections.

**Optional / going further:**
- Card, DellaVigna & Malmendier (2011), "The Role of Theory in Field
  Experiments," *JEP*.
- Todd & Wolpin (2006), *AER* — the structure-meets-experiment move.
- Imbens & Rubin, *Causal Inference*, chs. 1–4 — PhD-bound students.
- One post-2022 audit study of algorithmic/LLM hiring tools — assigned
  in class (verify with instructor).

## Deliverables checklist
- [ ] AI tutor session log + reflection — **[weekly deadline]**
- [ ] Lab 6 write-up (six sections + appendix) — **[one week after Lecture 2]**
- [ ] Problem Set 6 — **[before Lecture 1 of Module 7]**

## Limits of silicon subjects (read before interpreting anything)
This module's limit is the sharpest yet: silicon effect sizes and
variances are NOT power-calculation inputs for human studies. The
model's callback gap reflects its training mixture and alignment tuning
— it could sit anywhere relative to human behavior, and its tight
variance is a temperature setting, not population heterogeneity. Powering
a human study on those numbers fakes precision and risks a doomed design.
But note the twist this module adds to the course's running theme: LLM
resume screeners are deployed technology, so a careful silicon audit is
not always a stand-in for a human study — sometimes it IS the study. The
skill is knowing which one you're running.
