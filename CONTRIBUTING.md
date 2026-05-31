# Contributing to Awesome AI Second Brain

This repo compares existing tools and products for building AI-native second brains. Contributions should help a reader decide what to evaluate, what tradeoffs matter, and which workflows are actually supported.

## What Counts

Good contributions answer practical questions:

- Where does memory live: local, hosted, self-hosted, or platform-bound?
- How long does it take to get the first useful memory?
- What data can it ingest?
- Does raw data become organized knowledge automatically?
- Does it support consolidation, reflection, or a dream cycle?
- Can AI tools read and write through MCP, API, SDK, CLI, or plugins?
- Can users separate personal, project, workspace, and team scopes?
- What can users inspect, edit, delete, export, or audit?

## How To Add a Solution

1. Copy [templates/system-profile.md](templates/system-profile.md) into `solutions/<solution-name>.md`.
2. Add the solution to [solutions/README.md](solutions/README.md), [README.md](README.md), and the relevant comparison tables.
3. Update capability pages under `capabilities/` only for workflows you can source or verify.
4. Link official setup docs, official repos, and primary source material instead of duplicating command-by-command setup instructions.
5. Mark uncertain fields as `Unknown` instead of guessing.

## How To Add a Setup Guide or Example

Use `setup-guides/` for verified setup paths and `examples/` for scenario-level workflows. Do not add a setup guide unless you can explain how to verify that retrieval or write-back actually worked.

## Profile Quality Bar

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

## Sources

Use primary sources whenever possible:

- official docs
- official repositories
- maintainer-written examples
- product docs and changelogs
- reproducible local test reports

When using local or internal test reports, summarize them clearly and avoid presenting unverified assumptions as product claims.

Closed-source and hosted products are welcome. Contributors do not need to prove or disclose internal models, prompts, ranking logic, graph construction, or infrastructure details. Describe the public behavior that can be verified from docs, product UI, APIs, repos, or hands-on testing. Mark private or unavailable details as `Not disclosed` or `Unknown`.

## Writing Style

- Be factual and specific.
- Prefer decision-oriented landscape wording over tutorial wording.
- Distinguish built-in support from integration support and custom collector work.
- Distinguish observable product behavior from undisclosed internals.
- Use the standard support labels from [README.md](README.md).
- Keep recommendations scoped to the workflow they are best for, and explain tradeoffs without promotional framing.

## Pull Request Guidelines

- One solution or workflow per PR is preferred.
- Include sources and verification notes.
- Keep unrelated formatting changes out of the PR.
- If a page is a placeholder or watchlist entry, label it clearly as not fully evaluated.

## License Agreement

By contributing, you agree that your contributions will be licensed under the Apache License 2.0, the same license as this project.
