# Repolex Knowledge Graph of zenml-io/zenml-product-engineer-challenge

RDF knowledge graph data for [zenml-io/zenml-product-engineer-challenge](https://github.com/zenml-io/zenml-product-engineer-challenge), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download zenml-io/zenml-product-engineer-challenge
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ae6d7799b7f644eb44b52ca19cf162c2eeb66111
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ae6d7799b7f644eb44b52ca19cf162c2eeb66111
│           └── chunk-001.nq.gz
├── blob
│   ├── 0240683541cde3b021bd09e68885698ef87467c4.nq.gz
│   ├── 1986be461ec06d87e5e1124ad2b484444552246b.nq.gz
│   ├── 24aa676a3bbf26135014d1543fa032b830a29164.nq.gz
│   ├── 4f25649c4202e1c606b1082cff719ba552017234.nq.gz
│   ├── 55da4dcf0704977f926ee14de100a9a293cd2f49.nq.gz
│   ├── 7d9bee287e074355982dbdd398c39445f97d5381.nq.gz
│   ├── a61615007b58d41fb65d1ff6dfa6a89472069b8f.nq.gz
│   ├── ae345f50a1b35752cf9b032d2571b05eed07fa2f.nq.gz
│   ├── b819d083d9c0a0af06ffb61c64d426e0fa31a473.nq.gz
│   ├── cb1337bfd557b2fda9bf518e3dff3356e9f40e7f.nq.gz
│   └── d34cbe47fe15c560c04b7d900cd8cdb8581107b1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ae6d7799b7f644eb44b52ca19cf162c2eeb66111.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 17 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[zenml-io/zenml-product-engineer-challenge](https://github.com/zenml-io/zenml-product-engineer-challenge)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
