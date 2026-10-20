# R1-Zero-style RL on math with Dr. GRPO (authors' code), one A100

## The paper and code being reproduced

- **Paper:** Zichen Liu, Changyu Chen, Wenjun Li, Penghui Qi, Tianyu Pang, Chao Du, Wee Sun Lee,
  Min Lin. *Understanding R1-Zero-Like Training: A Critical Perspective.* COLM 2025.
  arXiv:2503.20783. https://arxiv.org/abs/2503.20783
- **Official code:** https://github.com/sail-sg/understand-r1-zero, commit
  `dfca49dd460ee7cc8e4a5a162c876a7fd6993b87` (2025-08-27), MIT license; training is implemented
  on the authors' Oat framework (https://github.com/sail-sg/oat). The clone was used unmodified
  apart from dataset cache files it generated.
- **Precedents the notes rely on:** DeepSeek-R1 (arXiv:2501.12948), STaR (arXiv:2203.14465),
  DAPO (arXiv:2503.14476).

```bibtex
@inproceedings{liu2025understanding,
  title={Understanding r1-zero-like training: A critical perspective},
  author={Liu, Zichen and Chen, Changyu and Li, Wenjun and Qi, Penghui and Pang, Tianyu and Du, Chao and Lee, Wee Sun and Lin, Min},
  booktitle={Conference on Language Modeling (COLM)},
  year={2025}
}
```

## What was run and what came out

A much smaller setting than the paper (one A100 40GB, a small model, a 64-question monitor and
512-question subsets; see `docs/data-manifest.json` and the training receipts). Correct answers
on the fixed 64-question monitor rose from 20 to 47 over 192 updates; the user stopped training
at update 219 and the checkpoints at updates 208 and 216 are preserved outside git
(`docs/user-stop-2056.json`). Conclusion: a small-scale reproduction of RL-driven improvement with
the authors' method, not a match to the paper's benchmark scores. Start at
[docs/START-HERE.md](docs/START-HERE.md); the handoff and lessons are in
[docs/HANDOFF.md](docs/HANDOFF.md); the illustrated learning guide is `docs/learning-guide.pdf`.

## Reproducing

- Hardware: one NVIDIA A100-PCIE-40GB (MIG 7g.40gb).
- Environment: Python package list in
  [env/requirements-understand-r1-zero-dfca49d.txt](env/requirements-understand-r1-zero-dfca49d.txt)
  (torch 2.6.0, vLLM 0.8.4, DeepSpeed 0.16.8, transformers 4.51.3); `docs/requirements-resolved.txt`
  is the resolution recorded at run time.
- Scripts: `code/run_larger4096.sh`, `code/evaluate.sh`, the quick-screen preparation and the
  receipts under `docs/` record every launch and scoring step with its command line.

Credit for the method and implementation belongs to the paper's authors.
