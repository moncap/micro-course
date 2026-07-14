Save as: capstone-guidelines.md

# Capstone Guidelines — Design + Simulate an Original Experiment
**Microeconomic Theory for Experimentalists & Applied Microeconomists**

## What the capstone is
You choose a real research question, develop theory-grounded behavioral
hypotheses, design an experiment to test them, pilot the design with a
generative-agent simulation (adapting course scaffolds — original code
is not required), compare simulated behavior to existing human
evidence, and present a refined proposal ready to take to an IRB, an
employer, or a PhD application. The capstone is the course's spine:
every module's exit competency converges here.

## Milestones (dates set in the syllabus)

| # | Milestone | Week | Deliverable |
|---|---|---|---|
| 1 | Research question memo | ~8 | 1 page: the question, why it matters, who has asked it before, what an answer would change |
| 2 | Theory + hypotheses | ~10 | 2–3 pages: the model(s) generating predictions; competing theories stated so they *disagree observably* |
| 3 | Experimental design draft | ~12 | 3–4 pages: subjects, treatments, elicitation + incentive compatibility, outcomes, identification, power sketch, ethics |
| 4 | Simulation pilot + audit battery | 14 | The adapted lab notebook, preregistration (see below), and the Lab 10 stability report on your task |
| 5 | Comparison memo | 15 | 2 pages: silicon results vs. existing human evidence, placed in the divergence taxonomy; your pre-registered decision rule, executed |
| 6 | Final paper + presentation | finals | 12–18 pages + 12-minute talk with 5 minutes of committee-style questioning |

Milestones 1–3 receive written feedback but are graded
complete/incomplete (together 10% of the capstone grade); the graded
weight is in 4–6 (see the rubric).

## The simulation pilot: requirements
1. **Adapt, don't build.** Start from whichever course lab is nearest
   your design (persona-grid, sampled-population, multi-agent, or
   audit harness). Original code earns no extra credit; a
   well-adapted scaffold with clean conventions does.
2. **Preregister before running.** Commit to the instructor, in
   writing: hypotheses, exact prompts, models and temperatures, N per
   cell, parsers, analysis code, and your decision rule (the pattern
   that justifies fielding, the pattern that sends you back to
   redesign, the pattern that halts). Cheap runs make forking paths
   worse, not better — the timestamp is the point.
3. **Run the audit battery** (Lab 10) on your task: ≥2 models, ≥3
   content-preserving paraphrases, ≥2 temperatures. The stability
   report is a required appendix.
4. **Course conventions throughout:** fixed reported temperature in
   the main runs, parse-failure logging, prompt logs in the appendix,
   DRY_RUN mode kept functional so the grader can execute your
   notebook without an API key.

## The comparison memo
Compare silicon behavior to the human literature your Milestone 1 memo
identified: levels, directions, heterogeneity — and place every
divergence in the course taxonomy (contamination / alignment artifact /
missing channel / prompt fragility). Then execute your pre-registered
decision rule and say what you decided. A memo that reports "the sim
matched, so the design is validated" will be returned unread; the
course's standard is the Bayes logic of PS10.

## The final paper (12–18 pages)
1. Question and motivation (from Milestone 1, sharpened)
2. Theory and hypotheses (competing predictions stated observably)
3. Experimental design (full protocol: subjects, treatments,
   elicitation + IC argument, outcomes, identification, power with
   simulation-based reasoning, ethics — including equipoise and
   consent where applicable)
4. Simulation pilot: methods, preregistration reference, results
5. Comparison to human evidence + divergence diagnosis
6. The refined proposal: what changed because of the pilot
7. **The honest methods paragraph** (required, graded hard): what the
   simulation was used for, what it was not used for, the stability
   evidence, and where every effect-size and power assumption came
   from
8. Appendices: audit battery report, prompts, code link, transcripts

## The presentation (12 min + 5 min questions)
Structure: question → design → what the pilot changed → the proposal
as it now stands. The questioning period is committee-style; expect
the steel-man ("the model just parrots your literature") and be ready
to concede first, then defend what survives. Your tutor session in
Week 14 rehearses exactly this.

## Ground rules
- AI tools may be used throughout **with disclosure**: attach
  transcripts for substantive AI assistance, per the course AI-use
  policy. The simulation is required AI use; the writing is yours.
- Human-subjects data collection is NOT required and NOT expected. If
  you have access to pilot humans (e.g., classmates as subjects),
  discuss with the instructor first — informal human piloting has its
  own ethics.
- Partner projects are allowed (max 2) with an individual-contribution
  statement and a proportionally deeper design.

## Choosing a question: three tests
1. **The theory test:** do at least two frameworks from this course
   make *different* predictions about it?
2. **The feasibility test:** could the human version actually be run
   for < $25k by a competent team — and can a course scaffold pilot
   it?
3. **The care test:** would you still want the answer if the sim, the
   committee, and the first referee all pushed back?

See `capstone-example-sketches.md` for three worked examples (lab,
field, and AI-native) that pass all three tests, and
`capstone-rubric.md` for exactly how points are assigned.
