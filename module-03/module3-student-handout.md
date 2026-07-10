Save as: module3-student-handout.md

# Module 3 Student Handout — Producer Theory, Costs & Technology
**Week 4 · Two lectures + Lab 3 + PS3 + tutor session**

## What this module is about
Producer theory in this course is not a tour of duality — it is the
minimum machinery you need to think about the module's real subject: why
profitable technologies go unadopted. You will generate a production
function with your own hands (a paper-chain factory with one scissors),
compute a cost-minimizing input mix where every number is whole, and then
meet the central puzzle of development microeconomics: fertilizer with a
~50% seasonal return that most farmers don't buy, and free consulting
that raised factory productivity ~17% and had to be given away. The
module's payoff is a taxonomy of frictions — credit, information, risk,
procrastination — each with its own experimental fingerprint, and the
design logic that separates them.

## Session roadmap
- **Lecture 1** opens with the paper-chain factory: your teams produce
  output with a growing workforce and one fixed scissors, and diminishing
  marginal product appears on the board with your names attached. Then:
  returns to scale, cost minimization worked ($q=\sqrt{KL}$, $w=4$,
  $r=1$: hire $L=5$, $K=20$, cost 40), short-run cost curves and the
  envelope — all from one technology — and the free-consulting puzzle
  (Bloom et al. 2013).
- **Lecture 2** opens with an adoption choice on your phones (pay 2
  tokens for a stream worth more — once payable now, once payable next
  week). Then: the fertilizer NPV numbers, the break-even discount rate
  of 50%/season that makes non-adoption a puzzle, the four frictions and
  their fingerprints, and the flagship result: a small well-timed
  discount that matched a 50% subsidy (Duflo, Kremer & Robinson 2011).
  Ends with a live DRY_RUN walk-through of Lab 3.
- **AI tutor session (required this week):** bring one adoption or
  input-choice question from your own research interests. The tutor
  opens with a flawed subsidy-experiment inference for you to critique.

## Key concepts in plain language
- **Diminishing marginal product ≠ bad technology.** It is a fixed input
  doing its job; total output can rise while each extra worker adds less.
  Returns to scale is the different question: what happens when you
  double *everything*.
- **Cost minimization = tangency.** The rate inputs trade in production
  (MRTS) equals the rate they trade in the market (w/r). Off-tangency
  choices are measurable waste — and lab subjects produce plenty of it
  before feedback.
- **MC cuts AC at its minimum.** A new player above the team average
  pulls the average up. The short-run AC touches the long-run AC exactly
  where the fixed input is the long-run optimum (the envelope).
- **Adoption = NPV decision.** Pay now, gain later; adopt if the return
  beats your discount rate. Fertilizer's break-even rate is ~50% per
  season — which is why low adoption needs a *friction*, not curvature.
- **The four frictions and their fingerprints.** Credit responds to
  loans; information to demonstrations; risk to insurance;
  procrastination to *decision timing*. A price cut moves all four —
  which is why price arms alone identify nothing.
- **The DKR result.** A tiny, time-limited discount at harvest (cash in
  hand, decide now) raised adoption about as much as a 50% subsidy at
  planting. The binding margin was *when*, not *how much*.

## Lab 3 — Silicon plant managers vs. the NPV benchmark
**Code:** `module3-simulation-lab.ipynb` (Colab-ready; opens in DRY_RUN
mode — runs end-to-end with no API key on clearly-labeled synthetic data;
set `DRY_RUN = False` for the real run). Design: 3 manager personas
(patient planner / impatient procrastinator / cautious skeptic) × 2
decision timings (deciding at harvest with cash in hand vs. at planting
when cash is tight — the DKR manipulation), 30 agents per cell.

**Benchmarks — and the tension between them:** the NPV rule says adopt in
*every* cell (break-even discount: 50%/season). The human literature says
a minority adopts at baseline and timing moves adoption substantially.
An agent population that matches the NPV rule is textbook-right and
human-wrong; one that matches humans needs a reason. Your write-up takes
a position on which you got and why.

**State your hypotheses before running (your pre-analysis plan):**
- **H1 (levels):** silicon adoption exceeds human baseline rates —
  commit to a direction before you look.
- **H2 (timing):** the cash-in-hand condition raises adoption relative
  to cash-tight (the DKR direction).
- **H3 (persona):** the impatient procrastinator adopts less than the
  patient planner, especially in the cash-tight condition (an
  interaction).

**Required modifications (pick at least one; edit only CHANGE HERE cells):**
1. **Credit arm:** the manager must borrow the $10 at 20% seasonal
   interest. Does silicon adoption respond to the borrowing rate at all —
   and does it collapse at rates above 50%, where the NPV actually turns
   negative?
2. **Risk arm:** gains become +$25 / +$5 with equal probability (same
   mean). Does the cautious-skeptic persona respond to mean-preserving
   risk the way safety-first farmers do?
3. **Information arm:** replace the explicit numbers with a neighbor's
   testimonial vs. an agronomist's table (same content, different
   source). Does source credibility move silicon adoption?

**Robustness section (required):** paraphrased prompt; second model; and
the **explicit-parameterization bait** — tell the agent its discount rate
outright and see whether behavior snaps to the textbook answer. If it
does, what were the personas doing?

**Write-up:** the standard six sections (question/benchmark → agent
design → treatments → results vs. humans → divergence diagnosis → design
implication), 3–5 pages plus appendix (prompts, code, results CSV, exact
model string, parse-failure rate). Section 5 must engage the
calculator-capture problem head-on: a transparently positive NPV may
trigger the model's arithmetic, not its "behavior" — say what in *your*
data speaks to this (PS3 Part C works the same question).

**Grading rubric (20 pts):**

| Pts | Component |
|---|---|
| 4 | Pre-stated hypotheses and clean execution (parse-failure rate reported; prompts logged) |
| 4 | Results presented against BOTH benchmarks (NPV rule and human adoption patterns) |
| 4 | Persona × timing interaction analyzed and interpreted, not just tabulated |
| 4 | Divergence diagnosis engages calculator capture + at least one alternative mechanism, with evidence |
| 4 | Design implication: one concrete improvement to a *human* adoption experiment that this pilot justifies |

## Problem Set 3
`module3-problem-set.tex` / PDF — due before Lecture 1 of Module 4.
Part A walks you through the cost-minimization example (every number
whole), the envelope relationship (one derivative), and the NPV
arithmetic with break-even discount and borrowing rates. Part B
(heaviest weight, 45 pts) asks you to design the field experiment that
separates at least three adoption frictions — price-subsidy arms alone
are explicitly not acceptable. Part C ⟨AI⟩ interprets the managers that
always adopt. Attach AI transcripts for Part C.

## Readings
**Core (read deeply this week):**
- Duflo, Kremer & Robinson (2011), "Nudging Farmers to Use Fertilizer,"
  *AER*.
- Bloom, Eifert, Mahajan, McKenzie & Roberts (2013), "Does Management
  Matter? Evidence from India," *QJE* — read for design and magnitudes.

**Optional / going further:**
- Foster & Rosenzweig (2010), "Microeconomics of Technology Adoption,"
  *Annual Review of Economics* — mine it for capstone ideas.
- Course text, chapters on production and cost.
- One post-2022 paper on LLM agents in managerial decision simulations —
  assigned in class (verify with instructor).

## Deliverables checklist
- [ ] AI tutor session log + reflection — **[weekly deadline]**
- [ ] Lab 3 write-up (six sections + appendix) — **[one week after Lecture 2]**
- [ ] Problem Set 3 — **[before Lecture 1 of Module 4]**

## Limits of silicon subjects (read before interpreting anything)
This module's version of the warning is specific: give a language model a
decision with explicit numbers and a correct answer, and it may *compute*
rather than *behave* — 96% adoption tells you about arithmetic, not
about farmers. No LLM is ever actually short of cash at planting time,
so scarcity narratives bind only if the persona gives them something to
bind on. And a sim that fails to reproduce the adoption gap can still
earn its keep: instrument wording, response formats, and framing bugs
are exactly what it can debug before the human study spends real money.
The robustness section measures these limits; your divergence diagnosis
reasons about them; the design implication says what changes.
