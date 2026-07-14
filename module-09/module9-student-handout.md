Save as: module9-student-handout.md

# Module 9 Student Handout — Digital & Platform Markets
**Week 13 · One lecture + one experiment session + Lab 9 + PS9 + tutor session**

## What this module is about
Platforms are where most experiments in the world now run — and where
the toolkit's assumptions break most instructively. This module covers
the economics you need to read platforms straight: why subsidizing one
side below cost is profit-maximizing rather than predatory (you'll
compute the fee falling below marginal cost yourself), why the world's
most sophisticated A/B-testing operations still produce estimates that
are wrong by construction when users share capacity (+18% measured, 0%
true — you'll do that arithmetic too), what eBay learned by turning
off its ads, and the unsettling Calvano result: pricing algorithms
that learn to collude without communicating. You will play repeated
Bertrand against strangers and then a fixed rival — most classes
produce tacit collusion live — and then silicon sellers play your
market, converging suspiciously fast to the monopoly price. Deciding
what that speed is evidence of is the module's exam question.

## Session roadmap
- **Lecture:** two-sided pricing arithmetic (the optimal rider fee is
  $2.50 against a $3 cost, and profit rises 6×); A/B testing craft and
  the interference disease (the rideshare +18%-vs-0% calculation);
  cluster vs. switchback fixes and their prices; eBay's paid-search
  natural experiment; Calvano et al.'s algorithmic collusion and the
  regulatory puzzle (coordination without agreement).
- **Experiment session:** the pricing tournament. Phase 1: repeated
  Bertrand, new random rival each round — watch prices grind toward
  the competitive benchmark. Phase 2: same rival all eight rounds,
  history visible, no talking — watch some pairs drift to the
  monopoly price without a word. Then Lab 9 launches live in DRY_RUN,
  and the notebook computes the two benchmarks (Nash = 4, monopoly
  = 6) by grid search before your eyes.
- **AI tutor session (required this week):** bring a platform-adjacent
  design or your capstone. The tutor opens with a promoted-listings
  experiment that overstates its effect in two ways for you to catch.

## Key concepts in plain language
- **Two-sided pricing.** Each rider generates profit on the driver
  side, so the rider's true margin includes the externality — and the
  optimal fee can sit below cost. The price *structure* across sides
  is the design; below-cost on one side is not predation.
- **Interference in A/B tests.** When treated and control users share
  a fixed resource (drivers, inventory, attention), the treated gain
  comes partly out of control's pocket, and the naive estimate can be
  wildly wrong — +18% for a true 0%. SUTVA again (Modules 6 and 8),
  now at platform scale.
- **Cluster vs. switchback.** Randomize markets (clean, but few
  clusters = power pain) or time blocks within a market (captures
  equilibrium, pays with carryover). The randomization unit is your
  theory of where interference flows.
- **Attribution ≠ identification.** eBay's dashboards said brand ads
  printed money; the market-level experiment said users would have
  clicked anyway.
- **Algorithmic collusion.** Calvano's Q-learners discovered
  reward–punishment pricing through ~100,000 episodes of experience —
  supra-competitive prices, no communication, no agreement. The
  coordination lives in the learned reactions, which is why audits
  should probe reactions, not price levels.

## Lab 9 — Silicon sellers: algorithmic pricing and the collusion question
**Code:** `module9-simulation-lab.ipynb` (Colab-ready; opens in DRY_RUN
mode — runs end-to-end with no API key on clearly-labeled synthetic
data; set `DRY_RUN = False` for the real run). Multi-agent repeated
duopoly: pairs of LLM sellers post integer prices 1–10 (cost 1) under
logit demand with an outside option, 12 rounds. **The analysis cell
computes the benchmarks from the demand engine by grid search:** the
competitive (Nash) price is 4, the joint-monopoly price is 6 — you
watch them fall out of the code, no formulas.

**Treatment:** `history` (each agent sees the full price/profit path)
vs. `amnesia` (each round stateless). Prediction from the human and
Q-learning literatures: history is what makes tacit collusion
sustainable.

**Benchmarks (three-way):** Calvano et al. (2020) — supra-competitive
convergence with punishment dynamics after ~10⁵ learning episodes; the
class's own two-phase tournament; and the grid-searched Nash/monopoly
prices.

**State your hypotheses before running (your pre-analysis plan):**
- **H1 (amnesia):** stateless sellers price near the Nash benchmark
  of 4.
- **H2 (history):** with history, prices drift above 4 toward 6.
- **H3 (the planted one):** commit NOW to what "suspiciously fast"
  convergence would look like, and to what you'd conclude if sellers
  hit exactly 6 within three rounds.

**Required modifications (pick at least one; edit only CHANGE HERE cells):**
1. **The manual-deviation probe:** force one seller to price at 3 for
   one round mid-game. Calvano's signature is
   punishment-then-forgiveness — does silicon enforce, or accommodate?
2. **Shifted benchmarks:** change the cost to 2 (the notebook
   recomputes Nash and monopoly by grid search). Do sellers track the
   *new* monopoly price, or recite the old one?
3. **Three sellers:** collusion is harder with more firms — in humans
   and Q-learners. Is it in silicon?

**Robustness section (required):** paraphrased prompt; second model;
and the **hidden-demand run** — sellers observe only their own price
and realized sales, never the demand function. This is the information
condition of actually deployed pricing tools, and it is where your
Part C argument lives.

**Write-up:** the standard six sections (question/benchmark → agent
design → treatments → results vs. humans/Q-learners → divergence
diagnosis → design implication), 3–5 pages plus appendix (prompts,
code, results CSV, exact model string, parse-failure rate). Section 5
must take a position on the speed question: three-round convergence to
the exact textbook answer is recognition or computation, not Calvano-
style learning — unless your hidden-demand and deviation-probe results
say otherwise.

**Grading rubric (20 pts):**

| Pts | Component |
|---|---|
| 4 | Pre-stated hypotheses (including H3's "too fast" criteria) and clean execution (parse-failure rate reported; prompts logged) |
| 4 | Price paths presented against ALL three benchmarks (grid-searched Nash/monopoly, Calvano, class tournament) |
| 4 | The history-vs-amnesia contrast analyzed and interpreted, not just tabulated |
| 4 | Divergence diagnosis engages recognition/computation vs. learning + evidence from your own runs (deviation probe especially) |
| 4 | Design implication: what a policy-relevant audit of deployed LLM pricing tools requires (information conditions front and center) |

## Problem Set 9
`module9-problem-set.tex` / PDF — due before Lecture 1 of Module 10.
Part A works the two-sided pricing problem (the optimal fee lands at
$2.50 against a $3 cost) and the interference arithmetic (+18% naive,
0% true). Part B (heaviest weight, 45 pts) designs the verified-seller
badge experiment that separates market growth from reallocation.
Part C ⟨AI⟩ adjudicates what three-round silicon "collusion" is
evidence of. Attach AI transcripts for Part C.

## Readings
**Core (read deeply this week):**
- Calvano, Calzolari, Denicolò & Pastorello (2020), "Artificial
  Intelligence, Algorithmic Pricing, and Collusion," *AER* — read for
  the design and the punishment-scheme evidence; skim the Q-learning
  machinery.
- Blake, Nosko & Tadelis (2015), *Econometrica* — the paid-search
  natural experiment.

**Optional / going further:**
- Rochet & Tirole (2003), *JEEA* — for PhD-bound students.
- Kohavi, Tang & Xu, *Trustworthy Online Controlled Experiments* —
  the interference and guardrails chapters.
- One post-2022 paper on LLM pricing agents — assigned in class
  (verify with instructor).

## Deliverables checklist
- [ ] AI tutor session log + reflection — **[weekly deadline]**
- [ ] Lab 9 write-up (six sections + appendix) — **[one week after the experiment session]**
- [ ] Problem Set 9 — **[before Lecture 1 of Module 10]**

## Limits of silicon subjects (read before interpreting anything)
Three bite hardest here. (1) **Your agents were handed the demand
curve** — deployed pricing tools must learn it from noisy sales, and
Calvano's entire result is about that learning; convergence without
learning is computation, not collusion. (2) **The model has read the
literature** — "repeated duopoly with history → tacit collusion" is a
completable pattern, possibly including Calvano itself. (3) **The
Module 6 twist applies:** LLM pricing tools are really being deployed,
so a hidden-demand audit of what they do is a legitimate,
policy-relevant study of the technology itself — the information
condition is what separates a homework answer from evidence a
regulator should read.
