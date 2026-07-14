Save as: module10-student-handout.md

# Module 10 Student Handout — AI-Econ Nexus & Capstone
**Week 14 · One lecture + one capstone workshop + Lab 10 + PS10 + tutor session**

## What this module is about
All semester, every lab ended with a "limits of silicon subjects" note.
This module is where those notes become the curriculum. You will meet
the Homo silicus research program your course has been quietly running
inside (Horton's simulated agents, Argyle's silicon sampling, Aher's
Turing experiments, Park's generative agents), assemble the divergence
taxonomy from your own nine lab write-ups — contamination, alignment
artifacts, missing channels, prompt fragility — and then do the
epistemics properly: a Bayes calculation showing why reproducing a
famous result barely moves the needle while one novel preregistered
prediction moves it a lot, and a stability audit that turns "prompt
sensitivity" from a vibe into a measured instrument property. The
capstone workshop puts it all to work on your own proposal.

## Session roadmap
- **Lecture:** the Homo silicus program and where the field stands;
  the course's own divergence taxonomy, built live from your lab
  write-ups; the Bayes-on-replication calculation; the can/cannot
  list, settled; ethics and disclosure (preregistration when runs are
  cheap, provenance, the honest methods paragraph).
- **Capstone workshop:** Lab 10 walk-through; the steel-man exchange
  (your partner attacks your proposal with the committee script; you
  defend by conceding first); and your pre-registered decision rule —
  the paragraph stating what sim pattern justifies fielding your human
  study, what sends you back, what kills it.
- **AI tutor session (required this week):** the capstone defense
  rehearsal. Bring your decision-rule paragraph and audit-battery
  plan.

## Key concepts in plain language
- **Homo silicus.** LLMs as simulated economic agents: endow
  preferences and information, run the experiment, vary what human
  budgets never could — with the failure modes you've now produced
  yourself, on purpose, nine times.
- **The divergence taxonomy.** Contamination (the model read the
  answer), alignment artifacts (tuning pushes behavior in a
  direction), missing channels (no stakes, no temptation, no error
  process), prompt fragility. This is the instrument's metrology.
- **The Bayes lesson.** Famous-result replications are correlated
  evidence — recitation predicts them almost as well as fidelity, so
  the likelihood ratio is ~1. Novel, preregistered, out-of-corpus
  predictions carry likelihood ratios worth having. Structure your
  evidence accordingly.
- **Stability as measurement.** Models × paraphrases × temperatures →
  ranges you compare against human cross-lab variability. Each
  instability knocks claims off the ladder: effect size falls first,
  then heterogeneity, then magnitude, sign last.
- **The can/cannot list (final form).** CAN: instrument debugging,
  pipeline validation, power machinery on human effect sizes,
  framing-sensitivity detection, hypothesis generation, and audits of
  deployed AI systems. CANNOT: effect-size forecasts, welfare claims,
  calibration rung 4.

## Lab 10 — The audit battery
**Code:** `module10-simulation-lab.ipynb` (Colab-ready; opens in
DRY_RUN mode — runs end-to-end with no API key on clearly-labeled
synthetic data; set `DRY_RUN = False` for the real run). **This lab is
a reusable harness, not a one-off experiment:** it runs any
task/parser pair across a models list × 3 content-preserving
paraphrases × 2 temperatures and produces the stability report —
per-cell means, paraphrase ranges (the prompt-sensitivity index),
cross-model gaps, and a claims-classification guide.

**The default task** is Module 1's dictator game, so you can see the
report work before you touch anything. **Your actual assignment:**
swap in YOUR capstone pilot's task and parser (the CHANGE HERE cells
accept any task from Labs 1–9 or your own), run the battery, and
attach the report to your capstone paper — it is a **required
appendix**.

**State your hypotheses before running:**
- **H1 (paraphrase):** commit to the paraphrase range you'd call
  "stable" for your task (the human cross-lab band is the reference).
- **H2 (models):** commit to what a cross-model gap would mean for
  your pilot's claims.
- **H3 (claims ladder):** write down, in advance, which of your
  pilot's claims survive which instabilities.

**Required modifications (this lab, everyone does all three):**
1. **Swap in your capstone task** (task text + parser + mock).
2. **Write your three paraphrases** — same content, different
   wording; have a classmate verify content-equivalence before
   running.
3. **Fill the claims table** in the analysis cell with your pilot's
   actual claims.

**Robustness section:** the battery IS the robustness section — this
lab is the course's robustness conventions, promoted to the main
event.

**Write-up:** the standard six sections, but Section 5 (divergence
diagnosis) becomes the star: place every instability you found in the
taxonomy, and Section 6 states which of your capstone claims
survived. 3–5 pages plus the appendix (prompts including all
paraphrases, code, results CSV, exact model strings, parse-failure
rates per cell).

**Grading rubric (20 pts):**

| Pts | Component |
|---|---|
| 4 | Pre-committed stability thresholds and claims ladder; clean execution (parse-failure rates per cell; all prompts logged) |
| 4 | The battery run correctly on YOUR capstone task (paraphrases content-equivalent, verified) |
| 4 | Stability report read correctly: ranges vs. the human band, claims classified |
| 4 | Instabilities placed in the taxonomy with evidence, not hand-waving |
| 4 | The surviving-claims statement matches the evidence (over-claiming costs double) |

## Problem Set 10
`module10-problem-set.tex` / PDF — due before finals week. Part A does
the Bayes calculation (the famous replication moves you from 0.30 to
0.31; the novel prediction to 0.61) and reads a stability report.
Part B (heaviest weight, 45 pts) designs the complete pre-registered
sim-pilot workflow for a gig-worker bonus experiment. Part C ⟨AI⟩ is
the committee member's objection: steel-man it, concede what's right,
defend what survives, and write the honest methods paragraph. Attach
AI transcripts for Part C.

## Readings
**Core (read deeply this week):**
- Horton (2023), "Large Language Models as Simulated Economic Agents:
  What Can We Learn from Homo Silicus?" NBER WP 31122.
- Argyle et al. (2023), "Out of One, Many," *Political Analysis*.

**Optional / going further:**
- Aher, Arriaga & Kalai (2023), ICML — Turing experiments and
  hyper-accuracy distortion.
- Park et al. (2023), "Generative Agents," UIST.
- Expected Parrot EDSL documentation (docs.expectedparrot.com).
- One post-2024 LLM-experiment validity/stability paper — assigned in
  class (verify with instructor).

## Deliverables checklist
- [ ] AI tutor session log + reflection — **[weekly deadline]**
- [ ] Lab 10 report (the audit battery, on YOUR capstone task) —
      **[with the comparison memo]**
- [ ] Problem Set 10 — **[before finals week]**
- [ ] Capstone: comparison memo — **[next week]**; final paper +
      presentation — **[finals week]** (see `capstone/` in this repo)

## Limits of silicon subjects (the final note)
This box has appeared ten times. Its content is now the module. What
remains to say is the course's closing position: silicon subjects are
the cheapest pilot ever built and the easiest to over-read. The
divergences you catalogued are not embarrassments to be hidden — they
are the instrument's specification sheet, and the researchers who
thrive with these tools will be the ones who measure their
instruments before trusting them. That habit — not any particular
model, prompt, or result — is what this course hopes you keep.
