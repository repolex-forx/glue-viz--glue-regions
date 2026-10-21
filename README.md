# Repolex Knowledge Graph of glue-viz/glue-regions

RDF knowledge graph data for [glue-viz/glue-regions](https://github.com/glue-viz/glue-regions), parsed by [repolex](https://repolex.ai).

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
rlex download glue-viz/glue-regions
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 52cbd0cf942d76a07dedc8a9ff620ad993d99c4f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 52cbd0cf942d76a07dedc8a9ff620ad993d99c4f
│           └── chunk-001.nq.gz
├── blob
│   ├── 229e5765e04414dbb2906d0f1fbd11f088853d69.nq.gz
│   ├── 23095a764c84e6844824f5b94506c0c5523dc55b.nq.gz
│   ├── 4ebbf5b79dd38f8a2d56dd9ce751cbb36f62f7bf.nq.gz
│   ├── 50745c4868c13bb212ea68ebb858881bd82ba5ba.nq.gz
│   ├── 6c8f69625f200f823060fd4bfb9a8588aa2be737.nq.gz
│   ├── 8e1be5b6e3b3fbcb6347bd521ec0f5139d281654.nq.gz
│   └── e851e58bf4c7b631d2a67f501bb74c7a2b0a8217.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 52cbd0cf942d76a07dedc8a9ff620ad993d99c4f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[glue-viz/glue-regions](https://github.com/glue-viz/glue-regions)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
