# AGENTS.md

## Repo Shape

- Markdown-only catalog. No root package manifest, build config, test runner, lint config, or CI workflow is present.
- Primary English docs live at root plus `solutions/`, `comparisons/`, `capabilities/`, `setup-guides/`, `examples/`, `templates/`.
- Korean mirrors live under `ko/`; maintainers may handle translations, but if you edit both EN/KR keep category names, support labels, and links semantically aligned.

## Evidence Rules

- Trust executable/config sources first, but this repo has mostly prose; use `README.md`, `CONTRIBUTING.md`, `solutions/README.md`, `comparisons/solution-layers.md`, and templates as the source of truth.
- Product claims need official docs, official repos, maintainer examples, product docs/changelogs, or reproducible local reports.
- Use `Unknown`, `Not disclosed`, or narrow caveats instead of guessing private internals, WIP features, licensing, benchmarks, or setup behavior.
- For benchmark claims, say who produced them; do not compare unlike metrics such as Recall@K, latency, cost, and answer grading as equivalent.

## Contribution Routing

- Full core profiles require wiring beyond `solutions/<name>.md`: update `README.md`, `solutions/README.md`, `comparisons/solution-layers.md`, `comparisons/capability-matrix.md`, plus relevant comparison/capability pages.
- If a project lacks deployment/setup/limitations evidence, use `watchlist.md` or a focused comparison/capability note instead of promoting it to `solutions/`.
- Classify by primary adoption layer, not marketing breadth: end-to-end app, local workspace, agent memory layer, memory substrate, or platform baseline.
- Keep lifecycle gap separate from layer: Collect, Organize, Evolve, Use, Govern are decision rows, not product categories.

## Profile Conventions

- New solution profiles should start from `templates/system-profile.md` and answer every capability row: deployment, capture, organization, evolution, retrieval/use, activation/write-back, scope, correction, privacy/control, setup/ops.
- Capability pages use `templates/capability-page.md` and should stay decision-oriented, not tutorial-style.
- Prefer official setup/evaluation links over copied install tutorials.
- Avoid promotional superlatives like "best", "leader", or "state of the art" unless an independent source supports that exact comparison.

## Verification

- There is no configured test suite. For docs changes run focused `rg` checks for stale names/claims, then local Markdown link smoke checks where links changed.
- Run `git diff --check`; CRLF warnings may appear on Windows, but whitespace errors still matter.
- Before finishing, run `git status --short` because this repo may have unrelated dirty Markdown changes.
