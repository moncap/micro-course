Save as: capstone-example-sketches.md

# Capstone Example Sketches — Three Worked Starting Points
**Microeconomic Theory for Experimentalists & Applied Microeconomists**

Three sketches at the level of detail a Milestone-3 draft should reach,
spanning the lab, the field, and AI-native designs. You may not adopt
one wholesale, but you may steal any part with attribution to the
sketch.

---

## Sketch 1 (lab): Do intentions price the gift? Gift exchange with a randomized wage-setter

**Question.** When workers reciprocate a generous wage, are they
rewarding the employer's *intention* or responding to the *amount*?
The answer decides whether gift-exchange effects survive automation of
wage-setting — a live question as firms delegate compensation to
algorithms.

**Theories in tension.** Reciprocity models (Module 4/5) require an
intentional benefactor: gratitude needs someone to thank. Distributional
models (Fehr–Schmidt) care only about payoffs: a computer-set generous
wage should buy the same effort as an employer-chosen one.

**Design.** Real-effort task (data transcription) on an online panel;
2×2: wage level (stingy $6 / generous $12, equal expected pay to a
piece-rate outside option) × wage-setter (employer chose / computer
drew at random, truthfully disclosed). Outcome: output and audited
quality. Identification: the wage-setter main effect at the generous
level is the intentions premium; reciprocity predicts it positive,
distributional models predict zero. Power: gift-exchange effect sizes
from FKR and Gneezy–List (~0.3–0.4 SD in the first hours), n ≈ 175/cell
before attrition; simulation-based power in the Module 6 harness.
Ethics: standard online-labor consent; pay floors met in all arms.

**Silicon pilot.** Adapt Lab 4 directly (it already contains the
intentions modification). What the pilot tunes: whether the
computer-set disclosure reads as credible; whether quality rubric
parses; framing-sensitivity of "generous." What it must not do: pick
the wage levels or forecast the premium. Known divergence risks
(taxonomy): harmony bias inflating reciprocity in *both* arms;
genre detection producing FKR patterns wherever "wage" and "effort"
co-occur. Audit battery on the decision prompt; the deviation the
battery can't catch — pledge-like behavior without payoffs — is why
the human study exists.

---

## Sketch 2 (field): Pricing commitment — the sophistication demand curve at a savings cooperative

**Question.** What fraction of a low-income savings population is
*sophisticated* about its own present bias — and what does
sophistication cost to reveal? (Module 5's diagnostic, taken to the
field.)

**Theories in tension.** Exponential discounters and full naifs have
zero willingness to pay for a commitment account; sophisticates have
strictly positive WTP (the PS5 arithmetic). A screening question
cannot separate them; a *price* can.

**Design.** Partner: a savings cooperative with ~3,000 members and
mobile-money rails. Arms: commitment-account offers at randomized
prices {−$1 (bonus), $0, $1, $3}; a liquidity-matched non-commitment
account arm (the kin-tax/other-control confound answer, per PS5's
rubric); pure control. Baseline: incentivized predictions of own
deposit behavior (the naiveté measure: the prediction–behavior gap).
Outcomes: take-up by price (the demand curve for commitment = the
sophistication distribution's lower envelope), deposits and balances
from administrative data. Power: take-up differences of 10 pp between
adjacent price arms, ~300/arm (Module 6 harness); cluster by branch if
information spillovers threaten. Ethics: no deception; the bonus arm's
"paying people to constrain themselves" reviewed with the partner;
products remain available to control at study end.

**Silicon pilot.** Adapt Lab 7's sampled-population method: profiles
from the cooperative's member demographics (with permission), the
offer scripts as the task. What the pilot tunes: whether offer scripts
read as the intended prices (comprehension across literacy levels);
whether the prediction elicitation parses. What it must not do:
forecast take-up (calibration rung 4; the WEIRD-flattening risk is
maximal here). The comparison memo should benchmark against
Ashraf–Karlan–Yin's 28% and the prediction-gap literature.

---

## Sketch 3 (AI-native): Do deployed LLM pricing tools collude when they must learn demand?

**Question.** Module 9's lab handed agents the demand curve and
watched them "collude" by calculation. The policy question is the
hidden-demand one: do LLM pricing agents, observing only their own
sales — the information condition of real repricing tools — sustain
supra-competitive prices with enforcement dynamics? Here the
simulation IS the study (the Module 6/9 twist): the agents are the
deployed technology, sampled with no external-validity gap.

**Theories in tension.** Calvano-style emergent collusion requires
learning reaction functions from experience; if LLM agents lack that
capacity under realistic information, the "immediate collusion risk"
narrative fails — while strong hidden-demand collusion would be
regulator-grade evidence.

**Design.** Repeated logit duopoly (Lab 9's engine), hidden-demand
condition: agents see own price, own realized sales, nothing else.
Factors: model family × memory window (5 vs. full history) × market
size (2 vs. 3 sellers). Outcomes: price paths vs. grid-searched Nash
and monopoly benchmarks; the manual-deviation probe (punishment
calibrated to deviation size vs. boilerplate — the PS9 diagnostic);
convergence speed. Preregistration is doubly binding here because the
result is the deliverable. Power/robustness: ≥20 pairs per cell; full
audit battery including cross-provider models; benchmark-shift runs
(cost changes) to separate computation from adaptation.

**Silicon pilot.** None needed — the sim is the experiment. The
"limits" section inverts: the scope limitation is about models and
prompts audited ("these versions, these configurations, this market
structure"), and the honest paragraph states that no claim is made
about markets where such tools interact with human sellers.

---

## Using these sketches
Each passes the three tests in the guidelines: two frameworks
disagree; the human version is feasible (< $25k for 1 and 2; sketch 3
needs only API budget); and each has a committee-proof answer to "why
do you want to know?" Your Milestone-1 memo should reach this
sketch's first two paragraphs; Milestone 3 should reach all of it.
