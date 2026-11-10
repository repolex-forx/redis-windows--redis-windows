# Repolex Knowledge Graph of redis-windows/redis-windows

RDF knowledge graph data for [redis-windows/redis-windows](https://github.com/redis-windows/redis-windows), parsed by [repolex](https://repolex.ai).

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
rlex download redis-windows/redis-windows
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 04bee108f1f8a0a191909cb58e2d05d25d41faa7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 04bee108f1f8a0a191909cb58e2d05d25d41faa7
│           └── chunk-001.nq.gz
├── blob
│   ├── 084b7fff22f7c7c78bc980e27c1d1e918062ab66.nq.gz
│   ├── 2028165a4ad24e8afac7d5530eac1e0c7b57c9f7.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 547dc6e6bb6fb2e234003473629b3dace9684527.nq.gz
│   ├── 61e7e905a3ce2e116e122b8aac267392693fc6af.nq.gz
│   ├── 7ace52e6535fdb2a58e8f94e849ea79f2eacbf00.nq.gz
│   ├── 87a95d935789355cdf2780da7cdd9ef12d7eda83.nq.gz
│   ├── 8a3620b30931bf5212fdcebda4e26c2a7d7224cc.nq.gz
│   ├── 8edb02c4fcf231681f5f8de028087a1364783a30.nq.gz
│   ├── 904b57ad86c376a798cc4ff524f6d990c6d042f6.nq.gz
│   ├── 941229d42ff357166df623e7297ecb5656fa0287.nq.gz
│   ├── 99d9d8cae393234f9bda927289c8a969582c0802.nq.gz
│   ├── ae8418ebeb6d6f3a28c63aee7381a52922bc9dd9.nq.gz
│   ├── c7eae39d0c215b3d3f3cb8de14c2f8bcefbfa091.nq.gz
│   ├── ceaed43b5a5266f6e95ea88188d9b7c295502584.nq.gz
│   └── f09c16697bb64bf6d3482ce7f4f777d79bf9e35f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 04bee108f1f8a0a191909cb58e2d05d25d41faa7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[redis-windows/redis-windows](https://github.com/redis-windows/redis-windows)

---
*Parsed on 2026-11-10 by [repolex](https://repolex.ai)*
