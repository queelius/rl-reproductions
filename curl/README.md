# CURL on DeepMind Control (authors' code), cartpole swingup and walker

## The paper and code being reproduced

- **Paper:** Michael Laskin, Aravind Srinivas, Pieter Abbeel. *CURL: Contrastive Unsupervised
  Representations for Reinforcement Learning.* ICML 2020, PMLR 119:5639-5650.
  https://proceedings.mlr.press/v119/laskin20a.html
- **Official code:** https://github.com/MishaLaskin/curl, commit
  `8416d6e3869e38ca0e46fcbc54a2f784dc09d7fc` (2020-10-28), MIT license; environments through
  `dmc2gym` and DeepMind Control. Related baselines the notes refer to: RAD
  (https://github.com/MishaLaskin/rad) and DrQ (https://github.com/denisyarats/drq).
- **Target:** Table 1 of the paper, cartpole swingup at 100k environment steps (published mean
  582, seed SD 146 over 10 seeds); `code/manifest.json` records the paper PDF hashes and the
  retrieval date.

```bibtex
@inproceedings{laskin2020curl,
  title={CURL: Contrastive Unsupervised Representations for Reinforcement Learning},
  author={Laskin, Michael and Srinivas, Aravind and Abbeel, Pieter},
  booktitle={Proceedings of the 37th International Conference on Machine Learning},
  series={Proceedings of Machine Learning Research}, volume={119}, pages={5639--5650},
  year={2020}, publisher={PMLR}
}
```

## What was run and what came out

Three arms (original CURL, a smaller-update single-encoder variant, and no image matching) on
cartpole swingup with three fresh training seeds (234, 567, 890) to 100k steps, plus walker runs
and encoder controls; nine models in the fresh-seed study. Findings and the seed-level numbers
are in [docs/FINDINGS.md](docs/FINDINGS.md) and the dated notes (`docs/CARTPOLE_FRESH_SEEDS.md`,
`docs/WALKER_*.md`, `docs/CORRESPONDENCE_CONTROL.md`, `docs/ENCODER_UPDATE_CONTROL.md`). This is a
small exploratory comparison with large seed variance, not a reproduction of the paper's mean.
The raw per-step training curves (50 `metrics.jsonl` files) are attached to release v0.1.0 as
`curl-raw-curves.tar.gz`; summaries stay in `docs/`.

## Reproducing

- Hardware: one NVIDIA A100-PCIE-40GB.
- Environment: [env/requirements-curl-8416d6e.txt](env/requirements-curl-8416d6e.txt) (torch
  2.13.0+cu130, mujoco 3.14.0); `code/requirements.lock.txt` is the lock recorded at run time.
- Scripts: `code/run_queue.py` and `code/run_frozen_queue.py` drive the authors' `train.py`;
  `code/train_reference.py`, `code/evaluate_frozen.py` and the `summarize_*.py` scripts produce the
  tables in `docs/`; `code/manifest.json` carries campaign provenance.

Credit for the method and implementation belongs to the paper's authors.
