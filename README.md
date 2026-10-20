# Repolex Knowledge Graph of hynek/first

RDF knowledge graph data for [hynek/first](https://github.com/hynek/first), parsed by [repolex](https://repolex.ai).

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
rlex download hynek/first
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d18599541b15b0fa351b66e20b04b1edd735df4b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d18599541b15b0fa351b66e20b04b1edd735df4b
│           └── chunk-001.nq.gz
├── blob
│   ├── 30b9bff925ff2274108b589265770eaa4fbf6b45.nq.gz
│   ├── 38d9b0a850a7dd55c0e9205700cc637428b4b5af.nq.gz
│   ├── 43708606c605f2a5272eb1f56dec1ba6fb033825.nq.gz
│   ├── 4648e41610d7e483f44de3a210f45ce4c9e3d717.nq.gz
│   ├── 5c912c147b8035b91ed12ee7d8321fd118ea95c6.nq.gz
│   ├── 8cf9d2d1c916885bb9c2f0da6fbd5f6d29b11584.nq.gz
│   ├── a665c546b657dbfe0e599bb52d8fa7425f069853.nq.gz
│   ├── a9c8c9db74449dcdab881be385a5a35244087ff3.nq.gz
│   ├── c660921c753113304b04f1e4ad2c94ef7d7d616f.nq.gz
│   ├── cd81bfecd13235ba10cf277d952c6144ef8d84fd.nq.gz
│   ├── e687cc5eeaf2d0ad2a20f953adec830b4b5a3218.nq.gz
│   └── f0bab18e5d89b6c3f9cd375f7430a44d7b8a7979.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d18599541b15b0fa351b66e20b04b1edd735df4b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[hynek/first](https://github.com/hynek/first)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
