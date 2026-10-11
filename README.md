# Repolex Knowledge Graph of bottlepy/bottle-werkzeug

RDF knowledge graph data for [bottlepy/bottle-werkzeug](https://github.com/bottlepy/bottle-werkzeug), parsed by [repolex](https://repolex.ai).

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
rlex download bottlepy/bottle-werkzeug
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 77361e3e030189bd9320cb40e73ba441777ace61
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 77361e3e030189bd9320cb40e73ba441777ace61
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b41316c975f80763c6ec0393f286003bc02fed5.nq.gz
│   ├── 4480ac3949984304b96f2d12ab91643e1c62d13b.nq.gz
│   ├── 5502228aafcd1e35411eaf244444a2eb935dee28.nq.gz
│   ├── 82d0730d119efb3c06488a3fca3e6dee98f5d4a9.nq.gz
│   ├── 8e4575954a60537ca883c7484c6feaafb0dd1029.nq.gz
│   └── c23ff98acbd62c7f3d4388ef43919e219225155b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 77361e3e030189bd9320cb40e73ba441777ace61.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 14 files
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

[bottlepy/bottle-werkzeug](https://github.com/bottlepy/bottle-werkzeug)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
