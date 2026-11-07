# Repolex Knowledge Graph of kivy/oscpy

RDF knowledge graph data for [kivy/oscpy](https://github.com/kivy/oscpy), parsed by [repolex](https://repolex.ai).

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
rlex download kivy/oscpy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9d6e1213d40f1a76de3f4615379808cf3e002460
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9d6e1213d40f1a76de3f4615379808cf3e002460
│           └── chunk-001.nq.gz
├── blob
│   ├── 011ef4ad254cc22c2a441679fb8958e90ed9e308.nq.gz
│   ├── 0e70401981887c02833d5d5f6b4ab9a9ab0db94b.nq.gz
│   ├── 244fa5477ee5e95fe82d972a6c093c7cd0d0584a.nq.gz
│   ├── 2838d5d5f024bc57e71032092c0ee75848d6a141.nq.gz
│   ├── 359ae4a3d71a6ff0d5059d1d330f09d0aa1b42c8.nq.gz
│   ├── 3c6e79cf31da1c0433d2fa666bf50b53f6359f26.nq.gz
│   ├── 3e08e5a1013bff7400e5f44947646e581305e977.nq.gz
│   ├── 457e33c1c98220794a9509a376b46cf966957517.nq.gz
│   ├── 57055b4f98877590c10cb4ef1accf37f3615c8cb.nq.gz
│   ├── 57278fbab5b69fda322d991d9e522a08925ed43c.nq.gz
│   ├── 61c3764e62a78a45e9227077253cbe4fe716da89.nq.gz
│   ├── 62e9278e15affe8a40f69151b657456063af0a52.nq.gz
│   ├── 642a5f87f4c9f28c5b0905d0430d077c5e28aeca.nq.gz
│   ├── 66367cbd519b1d29898fe370d75b7567ad5606fb.nq.gz
│   ├── 6743b0bbadd8f972c1a234b2c5822e40f39bfd53.nq.gz
│   ├── 70e6c9121990507f36c81be422204713289c2c27.nq.gz
│   ├── 8316b71fe4a7074a9ea5776aadd02b9b5f8ccf04.nq.gz
│   ├── 90d231af05d3a0fcc463dcad0cd6514a9364ca58.nq.gz
│   ├── a7fd37a06450e1f996d7334b0d238a9986e84e73.nq.gz
│   ├── bbcbbe7d61558adde3cbfd0c7a63a67c27ed6d30.nq.gz
│   ├── bf30c4a29638bf4fd900175d1bec539cf25a089e.nq.gz
│   ├── c06fe05df4fa49dd82d54162b1be7d92b1e9b9cc.nq.gz
│   ├── d1a142df1065322d099f94e400cafe5bccd5148e.nq.gz
│   ├── d1c185647e34f61af2f8555c0e6ae9d0349e3da1.nq.gz
│   ├── d5864b7828279d0c551596b515a482b81655c8e7.nq.gz
│   ├── f0e21bf2f011d74071be304c302e0b3665c68c2e.nq.gz
│   ├── fb89e8984d8e7b7c7ddd6d88c37ded1baaf09eaa.nq.gz
│   ├── fd2d7e4fef1b77b8b77cafa864008da965930c24.nq.gz
│   └── ff12d11aceedb9a79b1946d01e9188dbced0859f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9d6e1213d40f1a76de3f4615379808cf3e002460.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 37 files
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

[kivy/oscpy](https://github.com/kivy/oscpy)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
