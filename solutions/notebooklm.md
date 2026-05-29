# NotebookLM

## Snapshot

- Website / docs: https://notebooklm.google.com/ and https://support.google.com/notebooklm/
- Company / maintainer: Google
- Status: Active hosted product
- Open source: No
- Deployment: Hosted Google product
- Primary users: Researchers, students, analysts, and teams working from bounded source sets
- Best second-brain role: Source-grounded research notebook baseline
- Last reviewed: 2026-05-29

## One-line Summary

NotebookLM lets users create notebooks from uploaded or discovered sources, then ask source-grounded questions and generate summaries or study artifacts.

## Second-Brain Fit

NotebookLM is strong for bounded research over known sources. It is weaker as a living cross-agent memory layer because sources are imported into notebooks and agent access is platform-scoped.

## Capabilities

| Area | Evaluation |
|---|---|
| Deployment | Hosted Google product. |
| Data capture | Built-in upload/import for docs, slides, sheets, images, Word, text, Markdown, PDF, CSV, PowerPoint, web URLs, ePub, YouTube, audio, and Gemini Chats. |
| Auto-organization | Built-in source summaries, source labels/categories, and generated artifacts. |
| Consolidation / dreaming | Partial. Useful summaries and artifacts exist, but not an ongoing agent memory consolidation loop. |
| Retrieval model | Source-grounded notebook chat and source selection. |
| Agent access | NotebookLM/Gemini platform only for ordinary users. |
| Workspace / team support | Sharing/collaboration depends on Google account/product tier. |
| UI / filtering | Strong notebook UI, sources panel, source selection, labels, and generated artifacts. |
| Privacy / control | Hosted platform; imported sources are static copies except supported Drive sync behavior. |
| Setup burden | Low. Create a notebook and add sources. |

## Strengths

- Excellent source-grounded Q&A.
- Broad source type support.
- Good for reports, study guides, briefings, and research synthesis.

## Limitations

- Not a persistent cross-agent memory layer.
- Sources can be static copies; non-Drive sources may need manual re-upload.
- Not designed for agent write-back or team-wide memory governance.

## Relationship to Membase

NotebookLM is a strong research notebook. Membase is a living shared memory layer for agents. Use NotebookLM when the source set is bounded; use Membase when context should compound across agents and sessions.

## Official Setup / Evaluation Links

- [NotebookLM source docs](https://support.google.com/notebooklm/answer/16215270?hl=en)

## Sources

- [NotebookLM source docs](https://support.google.com/notebooklm/answer/16215270?hl=en)
