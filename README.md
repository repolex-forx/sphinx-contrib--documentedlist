# Repolex Knowledge Graph of sphinx-contrib/documentedlist

RDF knowledge graph data for [sphinx-contrib/documentedlist](https://github.com/sphinx-contrib/documentedlist), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/documentedlist
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 73fa4df717416821f3888d3de88607195cd838c2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 73fa4df717416821f3888d3de88607195cd838c2
│           └── chunk-001.nq.gz
├── blob
│   ├── 78ad00e553689a2794552f29d8865bf9fc601ae1.nq.gz
│   ├── 8e7e2bc0d26ebc39199523caf9850ff62f3d650a.nq.gz
│   ├── 95b0f44c24baa0131d73811081739fe39b027b4f.nq.gz
│   ├── b5a25a12656709a59eb5201210088cad36a2c6a6.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── ba74660506d90c514ee1d32bf4eb5ecb0af14075.nq.gz
│   ├── bfb9f4b5e992f8af7ca8153e93dab5c67e47976f.nq.gz
│   ├── d09dfa49438957f46e34d2ba8434044a61fe1a58.nq.gz
│   └── d0f1db857a7801f609893f484c71af664acca7db.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 73fa4df717416821f3888d3de88607195cd838c2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[sphinx-contrib/documentedlist](https://github.com/sphinx-contrib/documentedlist)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
