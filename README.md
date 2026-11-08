# Repolex Knowledge Graph of UKPLab/nlp-mh-evals

RDF knowledge graph data for [UKPLab/nlp-mh-evals](https://github.com/UKPLab/nlp-mh-evals), parsed by [repolex](https://repolex.ai).

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
rlex download UKPLab/nlp-mh-evals
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8930c5e61b25026516b65f6b1bceb3a2dcef7583
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8930c5e61b25026516b65f6b1bceb3a2dcef7583
│           └── chunk-001.nq.gz
├── blob
│   ├── 0846f83a1fcc7b425341caf32c03496c975be7f2.nq.gz
│   ├── 1bf1b1028f388f4321492dfc1b077fbd50c240ed.nq.gz
│   ├── 1f03afeece5ac28064fa3c73a29215037465f789.nq.gz
│   ├── 231270e246cae3af74f6f0522ddf51fabf71d6ad.nq.gz
│   ├── 33ad091d26d8a9dc95ebdf616e217d985ec215b8.nq.gz
│   ├── 5253d3ad9e6be6690549cb255f5952337b02401d.nq.gz
│   ├── 549f38fdd3f6838ee5905e576269a7e1909df62f.nq.gz
│   ├── 5a666547730235fbc33297f57a27fddd3897e160.nq.gz
│   ├── 74b5e053450a48a6bdb4d71aad648e7af821975c.nq.gz
│   ├── 8f2609b7b3e0e3897ab3bcaad13caf6876e48699.nq.gz
│   ├── 9dfc1c058cebbef8b891c5062be6f31033d7d186.nq.gz
│   ├── bd6213e1dfe6b0a79ce7d8b37d0d2dc70f0250bb.nq.gz
│   ├── d563c0fb10ba0e42724b21286eb546ee4e5734fc.nq.gz
│   ├── dcb76b6b6353389a99a3a18377b668a1a4d117c1.nq.gz
│   ├── e352b388275e40b88b9a843f45eec1ab0d864f8e.nq.gz
│   └── e9e57dc4d41b9b46e05112e9f45b7ea6ac0ba15e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8930c5e61b25026516b65f6b1bceb3a2dcef7583.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 22 files
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

[UKPLab/nlp-mh-evals](https://github.com/UKPLab/nlp-mh-evals)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
