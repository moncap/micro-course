Save as: module5-student-handout.md

# Module 5 Student Handout — Behavioral Economics: Deviations, Biases & Nudges
**Weeks 7–8 · Two lectures + Lab 5 + PS5 + tutor session**

## What this module is about
Modules 1–4 gave you the standard model and its stress points. This module
gives you the workhorse *alternatives* — prospect theory, present bias,
social preferences, limited attention — not as a museum of anomalies but as
competing hypotheses you will learn to separate experimentally. The module's
single most useful idea: a **sophisticated** present-biased person will pay
for commitment while a **naive** one won't, so commitment take-up is a
*measurement instrument*, not just a treatment. By the end you will run a
nudge experiment on a population of LLM agents whose behavioral "types" you
assign yourself — something no human dataset lets you do.

## Session roadmap
- **Lecture 1** opens with four choices on your phone (one pays real money).
  Your own answers become the data for the day: the value-function and
  weighting-function pictures, loss aversion with λ = 2 arithmetic, and
  present bias via β = 0.7 stories. Centerpiece: why sophisticates buy
  commitment and naifs don't, and what SEED's 28% take-up reveals.
- **Lecture 2** opens with a live one-shot ultimatum game. Then: inequity
  aversion vs. reciprocity as rival suspects and the experiment that
  separates them; matching grants in the field; the tax-salience experiment;
  and the hard welfare question behind the famous 49-point default effect.
- **AI tutor session (required this week):** bring one nudge or
  social-preference design from your own research interests. The tutor will
  open with a flawed savings-default inference for you to critique. Log +
  short reflection due per the standard weekly deadline.

## Key concepts in plain language
- **Reference dependence / loss aversion:** you evaluate outcomes as gains
  and losses relative to a reference point, and losses hurt about twice as
  much (λ ≈ 2). The experimenter *sets* the reference point via framing —
  deliberately or accidentally.
- **Present bias (β–δ):** one extra discount, β, on everything that isn't
  *now*. β = 0.7 explains taking $10 today over $11 tomorrow while also
  preferring $11 in 31 days over $10 in 30 — no contradiction.
- **Naive vs. sophisticated:** same β, different self-knowledge. The naif
  believes tomorrow-self will behave; the sophisticate knows better and
  *acts on that knowledge* — including paying for commitment.
- **Inequity aversion vs. reciprocity:** "I dislike unequal outcomes" vs.
  "I punish unkind intentions." Same rejection data; separated by varying
  intentions while holding payoffs fixed (e.g., computer-generated offers).
- **Limited attention:** demand responds to how *salient* a price component
  is, not just its size. Attention is a treatment variable.
- **The nudge welfare question:** a 49-point enrollment jump is not proof
  anyone is better off. With heterogeneous people, any single default
  misfits someone — welfare claims need a normative benchmark.

## Lab 5 — Nudging silicon populations
**Code:** `module5-simulation-lab.py` (Colab-ready; runs top to bottom; your
edits go only in the three CHANGE HERE blocks). Design: 3 discounting
personas × 2 defaults (opt-in/opt-out) × 2 incomes, 30 decisions per cell,
fixed temperature, all prompts logged.

**Human benchmark:** Madrian & Shea (2001, *QJE*) — automatic enrollment
raised 401(k) participation from ~37% to ~86%, with contributions clustering
at the 3% default. Your comparison targets: (i) the aggregate default
effect, (ii) clustering at the default rate, and (iii) the *heterogeneity*
pattern, which human data can never deliver — we don't observe a worker's β,
but your simulation assigns it by construction. That is the intellectual
case for this lab.

**State your hypotheses before running (your pre-analysis plan):**
- **H1 (aggregate):** enrollment is higher under opt-out, directionally
  consistent with the 49 pp human benchmark.
- **H2 (interaction — the sharp test):** default effect ≈ 0 for exponential
  personas (switching costs are trivial), largest for naive personas,
  intermediate for sophisticates.
- **H3 (anchoring):** opt-out enrollees cluster at the 3% contribution rate.

**Required modification (pick at least one; edit only CHANGE HERE blocks):**
1. **Price the nudge:** add a small monetary cost to remaining enrolled
   (opt-out arm). At what cost does the naifs' default effect collapse?
2. **Reminder treatment:** add a week-2 reminder condition and elicit the
   week-2 decision. Do reminders substitute for the default in silicon the
   way they (partially) do in human RCTs?
3. **Defaults-as-advice:** add a sentence that the default was "chosen at
   random by the payroll processor." If the effect shrinks, part of what you
   measured was rational inference from the default, not inertia.

**Robustness cell (required):** rerun key cells with (a) a paraphrased
prompt, (b) a second model, and (c) explicit parameterization ("your β is
0.7…"). If your interaction dies under paraphrase, it is a fact about your
prompt, not about silicon behavioral agents.

**Write-up:** the standard six sections (question/benchmark → agent design →
treatments → results vs. humans → divergence diagnosis → design
implication), 3–5 pages plus appendix (full prompts, code, results CSV,
exact model string, parse-failure rate). Section 5 must address
**training-data contamination head-on**: Madrian & Shea is in every
behavioral course — if your aggregate effect matches 49 pp suspiciously
well, is that fidelity or recitation? Say what evidence in *your* data bears
on it.

**Grading rubric (20 pts):**

| Pts | Component |
|---|---|
| 4 | Pre-stated hypotheses and clean execution (parse-failure rate reported; prompts logged) |
| 4 | Results presented against the human benchmark (levels, effect, clustering) |
| 4 | The interaction test (H2) analyzed and interpreted, not just tabulated |
| 4 | Divergence diagnosis engages contamination + at least one alternative mechanism, with evidence |
| 4 | Design implication: one concrete improvement to a *human* nudge experiment that this pilot justifies |

## Problem Set 5
`module5-problem-set.tex` — due before Lecture 1 of Module 6. Part A walks
you through the commitment-demand result with β = 0.7 and W = 12 (guided
steps and hints — the algebra is one substitution per part) and Fehr–Schmidt
rejection thresholds with numbers. Part B (heaviest weight, 45 pts) asks you
to design a field experiment measuring the *sophistication distribution*.
Part C ⟨AI⟩ interprets a silicon-pilot puzzle from Lab 5. Attach AI
transcripts for Part C.

## Readings
**Core (read deeply this week):**
- Kahneman & Tversky (1979), "Prospect Theory," *Econometrica* — read for
  the experiments and the pictures; skim the math.
- Ashraf, Karlan & Yin (2006), "Tying Odysseus to the Mast," *QJE*.
- Madrian & Shea (2001), *QJE* — the Lab 5 benchmark.

**Optional / going further:**
- DellaVigna (2009), "Psychology and Economics," *JEL* — best single survey.
- Laibson (1997); O'Donoghue & Rabin (1999) — β–δ sources (PhD-bound).
- Fehr & Schmidt (1999); Charness & Rabin (2002) — social preferences.
- Karlan & List (2007) — matching grants.
- Thaler & Sunstein, *Nudge* — mechanism taxonomy, not rigor.
- DellaVigna & Linos, *Econometrica* — nudges at scale (verify with
  instructor for exact assignment).

## Deliverables checklist
- [ ] AI tutor session log + reflection — **[weekly deadline]**
- [ ] Lab 5 write-up (six sections + appendix) — **[one week after Lecture 2]**
- [ ] Problem Set 5 — **[before Lecture 1 of Module 6]**

## Limits of silicon subjects (read before interpreting anything)
LLM agents have read the literature you are benchmarking against; they face
no real stakes; their "types" are prompt text, not preferences; and their
behavior can shift under paraphrase. This lab treats those limits as
research questions — the robustness cell exists to measure them and your
divergence-diagnosis section exists to reason about them. A silicon pilot
that matches human data is *not* validated, and one that diverges is *not*
useless: in both cases the interesting output is the mechanism, and the
design change it suggests for the human study.
