# RL reproduction exercises

Two paper reproductions done as training-pipeline exercises before the RLM research (October
2026), split with history from the `rlm` monorepo on 2026-10-20. Neither uses the RLM runtime,
and neither claims novelty: the methods, code and data are the original authors'. Each folder
has its own README with the citation, the official code commit, the environment lock, the
hardware, how to run, and the result against the paper.

- [`r1/`](r1/README.md): Dr. GRPO from *Understanding R1-Zero-Like Training: A Critical
  Perspective* (Liu et al., COLM 2025) on a small LLM for math, run with the authors' code.
  Stopped by the user after 219 updates; a small-scale reproduction of RL-driven improvement,
  not a benchmark match.
- [`curl/`](curl/README.md): *CURL: Contrastive Unsupervised Representations for Reinforcement
  Learning* (Laskin, Srinivas, Abbeel, ICML 2020) on DeepMind Control cartpole swingup and
  walker, run with the authors' code: nine fresh-seed models across three arms.

The audited SPO-on-GSM8K reproduction lives in its own repository:
https://github.com/queelius/spo-gsm8k-reproduction.
