# Repolex Knowledge Graph of colcon/colcon-package-information

RDF knowledge graph data for [colcon/colcon-package-information](https://github.com/colcon/colcon-package-information), parsed by [repolex](https://repolex.ai).

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
rlex download colcon/colcon-package-information
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── df35edd9a88f7edafc391be30277654ffa6dced0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── df35edd9a88f7edafc391be30277654ffa6dced0
│           └── chunk-001.nq.gz
├── blob
│   ├── 00b8f28d8ee62120a7e11b11afde5757b9753708.nq.gz
│   ├── 0f17157ed42b486a0c57cbffddd97987a4844e6b.nq.gz
│   ├── 36788887ce014bba74c49c3ca46b5cdd4cc07033.nq.gz
│   ├── 429e0ff02e17f9b3cd8afb775b2c1f584e32a5b8.nq.gz
│   ├── 4ace9f49e2a0afc501b75ead1a0f792790188ff5.nq.gz
│   ├── 60c548aea3102514f84685b52948bf2d592149c0.nq.gz
│   ├── 6344a81468c0d31d88911f220556ed6806c49b2b.nq.gz
│   ├── 64a4aaf89078e19903c0513b11f1e0b498261a01.nq.gz
│   ├── 66bb734962cbcb1c8d50c1bd7e9ca85cbbf41c2e.nq.gz
│   ├── 75099c47860b790fb693eafd0eaf7b5e62ad4d52.nq.gz
│   ├── 9bee60fe7743e7edf2c3fbde46d908589e604f89.nq.gz
│   ├── a75034d688df4114bac4ac6a0374daf0a3e5ddd4.nq.gz
│   ├── ab6e4797998260f4daf15dd36c9afeee7adaff29.nq.gz
│   ├── bd7c8693b373f16474a10254e75b502ef8389f27.nq.gz
│   ├── cfe299b6618ab7fff918643841b7114ae0ff9e83.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e82fd0b0abbf1472480d19d468efe7819276e80d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── df35edd9a88f7edafc391be30277654ffa6dced0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[colcon/colcon-package-information](https://github.com/colcon/colcon-package-information)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
