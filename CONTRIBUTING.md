# Contributing to Awesome AI Second Brain

This repo compares existing tools and products for building AI-native second brains. Contributions should help a reader decide what to evaluate, what tradeoffs matter, and which workflows are actually supported.

## What Belongs Here

This repo is for decision-oriented comparisons of AI-native second-brain systems. Good contributions help readers answer practical questions:

- Where does memory live: local, hosted, self-hosted, or platform-bound?
- How long does it take to get the first useful memory?
- What data can it ingest?
- Does raw data become organized knowledge automatically?
- Does it support consolidation, reflection, or a dream cycle?
- Can AI tools read and write through MCP, API, SDK, CLI, or plugins?
- Can users separate personal, project, workspace, and team scopes?
- What can users inspect, edit, delete, export, or audit?

Generic vector databases, RAG libraries, note apps, or agent frameworks are in scope only when the contribution explains their second-brain role clearly.

## MECE Decision Model

Keep two decision axes separate:

- Lifecycle gap: what part of the second-brain lifecycle the reader is trying to solve first: Collect, Organize, Evolve, Use, or Govern.
- Primary layer: what kind of system the reader is adopting first: end-to-end app, local workspace, agent memory layer, memory substrate, or platform baseline.

The lifecycle chooser answers "what problem should I solve first?" The Solution Snapshot, Solution Layers page, and Capability Matrix answer "what kind of system am I adopting, and what tradeoffs come with that layer?" Do not create a new product category when a lifecycle row, capability page, or layer grouping already explains the difference.

When a system spans multiple areas, choose one primary adoption layer and describe secondary roles in the profile. For example, a memory API with connectors may support collection, organization, and use, but it is still an agent memory layer if developers adopt it through API, SDK, MCP, or plugins first.

## Contribution Types

Pick the smallest contribution type that fits the evidence you have:

- Core solution profile: a shipped, source-backed system that readers can reasonably evaluate today.
- Capability or comparison update: a focused addition to an existing decision path, useful when a project is relevant to one workflow but not ready for a full profile.
- Setup guide: a verified setup path under `setup-guides/`, including how to confirm retrieval, write-back, or activation worked.
- Example: a scenario-level workflow under `examples/` that shows how a second-brain pattern is used.
- Watchlist entry: a project the maintainers intentionally want to track, but not a full evaluated profile.

Not every rejected core profile becomes a watchlist item. A project may be declined entirely if it is too early, outside the repo scope, insufficiently sourced, unclear on licensing, mainly relies on future or WIP surfaces, or does not add enough decision value for readers.

## Core Solution Bar

Before opening a full solution profile, check the project against all of these filters:

- Scope fit: it directly addresses AI second-brain, agent memory, personal/team knowledge, or context-engineering workflows.
- Shipped surface: core claims should describe functionality available today. Planned features, open issues, roadmaps, or WIP branches can be mentioned as limitations, but should not be the basis for core placement.
- Activation: at least one AI-tool access path should work today, such as MCP, API, SDK, CLI, plugin, app UI, or documented connector.
- Lifecycle coverage: it meaningfully covers multiple parts of the second-brain lifecycle: Collect, Organize, Evolve, Use, and Govern. A project that is strong on only one axis may fit a capability page better than a core profile.
- Primary layer fit: it can be placed in exactly one primary layer for README and matrix grouping, even if the profile explains secondary roles.
- Decision value: the project should add a distinct option for readers, not only duplicate an existing core entry with less maturity or less evidence.
- Operational clarity: deployment model, setup burden, data ownership, license or source-availability status, and personal/team scope should be explainable from sources.

## Core Profile Coverage

A full core solution profile should be wired into the repo's decision paths, not only added as a standalone page.

Required for core profiles:

- `solutions/<solution-name>.md`, copied from [templates/system-profile.md](templates/system-profile.md)
- `README.md` lifecycle chooser rows and the appropriate layer group in the Solution Snapshot
- `solutions/README.md`
- `comparisons/solution-layers.md`
- `comparisons/capability-matrix.md`

Conditionally required when source-backed and relevant:

- `comparisons/*` pages, such as chooser, setup burden, agent access, local vs cloud, or personal vs team
- `capabilities/*` pages for workflows the solution actually supports

Korean mirrors under `ko/` are maintainer-managed. External contributors do not need to include Korean translations unless a maintainer asks for them in that PR.

If a solution does not yet have enough evidence for those decision paths, use a narrower contribution type or do not add it yet.

## Profile Content

Every solution profile should answer:

- deployment and ownership summary
- context capture behavior
- knowledge organization behavior
- consolidation or maintenance behavior
- retrieval and grounding behavior
- AI-tool activation and write-back surfaces
- workspace and team support
- UI, inspection, and correction surfaces
- privacy, portability, and control
- setup burden
- best-fit users
- non-fit users
- tradeoffs
- official setup or evaluation links

Use official setup docs, official repos, and primary source material instead of duplicating command-by-command setup instructions. Mark uncertain fields as `Unknown` instead of guessing.

## Evidence and Claims

Use primary sources whenever possible:

- official docs
- official repositories
- maintainer-written examples
- product docs and changelogs
- reproducible local test reports

When using local or internal test reports, summarize them clearly and avoid presenting unverified assumptions as product claims.

Closed-source and hosted products are welcome. Contributors do not need to prove or disclose internal models, prompts, ranking logic, graph construction, or infrastructure details. Describe the public behavior that can be verified from docs, product UI, APIs, repos, or hands-on testing. Mark private or unavailable details as `Not disclosed` or `Unknown`.

### Benchmarks and Claims

Benchmarks are useful, but describe who produced them and what they measure. Distinguish independent third-party validation from maintainer-published benchmarks, local test reports, and vendor claims. Do not compare different metrics as if they are equivalent; for example, end-to-end answer grading, Recall@K, latency, and cost measure different things.

Use conservative wording:

- Good: "Maintainer-published benchmarks report..."
- Good: "A local hands-on test found..."
- Avoid: "Best", "leader", "state of the art", or broad quality claims unless an independent source supports that exact comparison.

### License and Source Availability

Do not use `Open source: Yes` unless the project has a recognized open-source license or the license is clearly stated in the official source. For public repositories without a declared license, use wording such as `Public repo; license not declared`.

## Writing Style

- Be factual and specific.
- Prefer decision-oriented landscape wording over tutorial wording.
- Distinguish built-in support from integration support and custom collector work.
- Distinguish observable product behavior from undisclosed internals.
- Use the standard support labels from [README.md](README.md).
- Keep recommendations scoped to the workflow they are best for, and explain tradeoffs without promotional framing.

## Pull Request Checklist

- One solution or workflow per PR is preferred.
- Include sources and verification notes.
- State known limitations instead of smoothing them over.
- Keep unrelated formatting changes out of the PR.
- If a page is a placeholder or watchlist entry, label it clearly as not fully evaluated.
- Resolve conflicts with `main` before requesting review.
- Do not rely on future or WIP features for core placement.

## License Agreement

By contributing, you agree that your contributions will be licensed under the Apache License 2.0, the same license as this project.
