# Contributing to Awesome AI Second Brain

This repo compares existing tools and products for building AI-native second brains. Contributions should help a reader decide what to evaluate, what tradeoffs matter, and which workflows are actually supported.

## What Counts

Good contributions answer practical questions:

- Where does memory live: local, hosted, self-hosted, or platform-bound?
- How long does it take to get the first useful memory?
- What data can it ingest?
- Does raw data become organized knowledge automatically?
- Does it support consolidation, reflection, or a dream cycle?
- Can agents read and write through MCP, API, SDK, CLI, or plugins?
- Can users separate personal, project, workspace, and team scopes?
- What can users inspect, edit, delete, export, or audit?

## How To Add a Solution

1. Copy [templates/system-profile.md](templates/system-profile.md) into `solutions/<solution-name>.md`.
2. Add the solution to [solutions/README.md](solutions/README.md), [README.md](README.md), and the relevant comparison tables.
3. Update capability pages under `capabilities/` only for workflows you can source or verify.
4. Link official setup docs, official repos, and primary source material instead of duplicating command-by-command setup instructions.
5. Mark uncertain fields as `Unknown` instead of guessing.

## Profile Quality Bar

Every solution profile should answer:

- deployment model
- data capture model
- auto-organization model
- consolidation or dreaming model
- retrieval model
- agent access surfaces
- workspace and team support
- UI and filtering surfaces
- privacy, control, and portability
- setup burden
- official setup or evaluation links
- relationship to Membase

## Sources

Use primary sources whenever possible:

- official docs
- official repositories
- maintainer-written examples
- product docs and changelogs
- reproducible local test reports

When using local or internal test reports, summarize them clearly and avoid presenting unverified assumptions as product claims.

## Writing Style

- Be factual and specific.
- Prefer decision-oriented landscape wording over tutorial wording.
- Distinguish built-in support from integration support and custom collector work.
- Use the standard support labels from [README.md](README.md).
- Keep `Relationship to Membase` analytical, not promotional.

## Pull Request Guidelines

- One solution or workflow per PR is preferred.
- Include sources and verification notes.
- Keep unrelated formatting changes out of the PR.
- If a page is a placeholder or watchlist entry, label it clearly as not fully evaluated.

## License Agreement

By contributing, you agree that your contributions will be licensed under the Apache License 2.0, the same license as this project.
