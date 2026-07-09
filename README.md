# Microeconomic Theory for Experimentalists & Applied Microeconomists
### Foundations, Behavior & AI-Augmented Experiments

Student materials for a master's-level course that trains you to **design,
critique, and pilot real experiments** — in the lab, in the field, and with
LLM generative agents as silicon subjects.

## What you will be able to do by the end

1. **Read modern applied and experimental papers critically** — identify
   what was tested, whether the design supports the claims, and what would
   strengthen it.
2. **Design your own theory-informed experiments, end to end** — treatments,
   incentive-compatible elicitation, hypotheses, power reasoning.
3. **Use LLM generative agents to pilot, stress-test, and scale designs**
   before spending money on human subjects — and reason honestly about where
   silicon subjects diverge from humans.

## What's in this repo

One folder per module, each containing the student-facing materials:

| File | What it is |
|---|---|
| `moduleN-simulation-lab.ipynb` | The LLM simulation lab — run it in Google Colab |
| `moduleN-problem-set.pdf` (+ `.tex`) | The problem set |
| `moduleN-student-handout.md` | Session roadmap, key concepts, lab instructions, readings |

## How to run a lab

No local setup and no prior Python experience needed — labs run in Google
Colab and execute top to bottom as given. Your own modifications are
confined to clearly marked **CHANGE HERE** blocks.

1. Open the lab notebook in Colab using the link pattern below (or the badge
   at the top of each notebook).
2. Run the cells top to bottom. The first cell installs dependencies; you
   will be prompted for an Anthropic API key via a hidden input (`getpass`)
   — the key is never stored in the notebook.
3. Make your assigned modification **only** inside the CHANGE HERE blocks,
   rerun, and export your results CSV and prompt log for the write-up
   appendix.

### Open-in-Colab link pattern

```
https://colab.research.google.com/github/moncap/micro-course/blob/main/module-NN/moduleN-simulation-lab.ipynb
```

Example (Module 5):
<https://colab.research.google.com/github/moncap/micro-course/blob/main/module-05/module5-simulation-lab.ipynb>

## A note on silicon subjects

LLM agents have read the literature you are benchmarking against; they face
no real stakes; their "types" are prompt text, not preferences. Every lab
treats these limits as research questions, not footnotes — the robustness
checks exist to measure them.

## License

MIT — see [LICENSE](LICENSE).
