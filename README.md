# Repolex Knowledge Graph of asimov-modules/asimov-modules

RDF knowledge graph data for [asimov-modules/asimov-modules](https://github.com/asimov-modules/asimov-modules), parsed by [repolex](https://repolex.ai).

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
rlex download asimov-modules/asimov-modules
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── aee01ed4ed38f18c082bfe60fe496b83593a370f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── aee01ed4ed38f18c082bfe60fe496b83593a370f.nq.gz
│   └── repolex
│       └── aee01ed4ed38f18c082bfe60fe496b83593a370f
│           └── chunk-001.nq.gz
├── blob
│   ├── 7ee134fcc3dc51b77deaf3b09d9190715c17ebe6.nq.gz
│   ├── 884954d1ff6f6c89e76cf1ac03ab3d8adbee3410.nq.gz
│   ├── 910431dd729d2ff14f841d19bfdebf4eedc24215.nq.gz
│   ├── baa604443559156602ea097e44f6f77e588b3040.nq.gz
│   ├── bb67c988519445888ae76a7c7c4041de9dee75cf.nq.gz
│   ├── c7af98591eb6c18296be750e48a7b3b27822ba5f.nq.gz
│   ├── cf99e1c5ab2b9a0bce05b553f521f3d499c878a4.nq.gz
│   ├── e3e57a8ce4ccbf74759a6df8fa4a3980ff1c9209.nq.gz
│   ├── e57a9f155af584334d3ac6658af548f2a7a4e9e6.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eba4cad5b53be16b54cc79c58f1f768019777e44.nq.gz
│   ├── efb98088164f5786b17e83ed384971fc3c74f93c.nq.gz
│   └── fc92c1f6096725b77c45fd50f25c387a228b622b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── aee01ed4ed38f18c082bfe60fe496b83593a370f.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 20 files
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

[asimov-modules/asimov-modules](https://github.com/asimov-modules/asimov-modules)

---
*Parsed on 2026-09-28 by [repolex](https://repolex.ai)*
