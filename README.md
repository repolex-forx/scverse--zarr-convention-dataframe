# Repolex Knowledge Graph of scverse/zarr-convention-dataframe

RDF knowledge graph data for [scverse/zarr-convention-dataframe](https://github.com/scverse/zarr-convention-dataframe), parsed by [repolex](https://repolex.ai).

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
rlex download scverse/zarr-convention-dataframe
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0a4bb801402eceaeca359d4ea7e9a6b50d14a3ea
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0a4bb801402eceaeca359d4ea7e9a6b50d14a3ea
│           └── chunk-001.nq.gz
├── blob
│   ├── 024eb6ccc6563fe08db5867558164387fe46963e.nq.gz
│   ├── 32bf13e22c15d784e0e1ce3af41c67609ff4a4b6.nq.gz
│   ├── b4784132ebe655d45e9f4fb609d2803bf4dc92cf.nq.gz
│   └── c152f8f11362215e43fd23aadba422934b919939.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0a4bb801402eceaeca359d4ea7e9a6b50d14a3ea.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 12 files
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

[scverse/zarr-convention-dataframe](https://github.com/scverse/zarr-convention-dataframe)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
