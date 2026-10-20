# RL reproduction exercises

Two paper reproductions done as pipeline exercises before the RLM research (October 2026), split
with history from the `rlm` monorepo on 2026-10-20. Neither uses the RLM runtime.

- **`r1/`**: a short R1-style GRPO run on a small LLM for math (7 October 2026). Stopped by the
  user after 219 updates with a monitor score of 47 of 64 at update 192; checkpoints at updates
  208 and 216 are preserved externally. Conclusion: a small-scale reproduction of RL-driven
  improvement, not a benchmark match. Start at [r1/docs/START-HERE.md](r1/docs/START-HERE.md).
- **`curl/`**: CURL (contrastive representations for pixel-based RL) on DeepMind Control cartpole
  swingup and walker, nine fresh-seed models across three arms (4 to 7 October 2026). Findings in
  [curl/docs/FINDINGS.md](curl/docs/FINDINGS.md). The raw per-step training curves (50
  `metrics.jsonl` files) are not tracked; they are attached to the first release as
  `curl-raw-curves.tar.gz`.

The audited SPO-on-GSM8K reproduction lives in its own repository.
