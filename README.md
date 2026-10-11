# Repolex Knowledge Graph of samuelcolvin/mcpython

RDF knowledge graph data for [samuelcolvin/mcpython](https://github.com/samuelcolvin/mcpython), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/mcpython
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b461097e1de0d62eb31cc8658d4895d4d3a36466
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b461097e1de0d62eb31cc8658d4895d4d3a36466
│           └── chunk-001.nq.gz
├── blob
│   ├── 24ee5b1be9961e38a503c8e764b7385dbb6ba124.nq.gz
│   ├── 389dc7c281d35820f7ad03213d95fae8e77b9d2d.nq.gz
│   ├── 544d830759e7605f7be80737c0153601fce92cce.nq.gz
│   ├── 7de37d02501b6f31e15f8e7df0ee6d8bec7e1bb3.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f1da3f82a068648412c295ec9da1b6f59eb8924d.nq.gz
│   └── ffd8fdecff3710a841322ec286f2f7c1999671c7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b461097e1de0d62eb31cc8658d4895d4d3a36466.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 13 files
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

[samuelcolvin/mcpython](https://github.com/samuelcolvin/mcpython)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
