# Repolex Knowledge Graph of lericson/pylibmc

RDF knowledge graph data for [lericson/pylibmc](https://github.com/lericson/pylibmc), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download lericson/pylibmc
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4e682481051b96c25e9e997fc7cabe96298e945e
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 4e682481051b96c25e9e997fc7cabe96298e945e.nq.gz
│   └── repolex
│       └── 4e682481051b96c25e9e997fc7cabe96298e945e
│           └── chunk-001.nq.gz
├── blob
│   ├── 4460877a186f30ce230ed8e005320de84d92091a.nq.gz
│   ├── 579e45a2b78bdfaafe725091e0fcf70acac4958b.nq.gz
│   ├── 6bb3d2180e00553bc6cf01ad401ec7dea37372a5.nq.gz
│   ├── 8212673df926118282819a1da779d27c634c7ee8.nq.gz
│   ├── 84549d353064a8dd4e1172fa59e6eb93d67f3ad8.nq.gz
│   ├── bdd597bed5040f434c4822fc6908d7a4a78a1df6.nq.gz
│   ├── d23bf4a644058ac88a4372d5b83a6d3cd48f0a6b.nq.gz
│   ├── e32bcd5aad1c828be5b84ac38a8007af4f20bb0d.nq.gz
│   ├── ee12d8e68fbfb81926a91c1fa6e43b9586224cce.nq.gz
│   └── f04b1ca33cd119d1160ad9a8147426d6d7e4079b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 4e682481051b96c25e9e997fc7cabe96298e945e.nq.gz
├── filetree
│   └── 4e682481051b96c25e9e997fc7cabe96298e945e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 20 files
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

## Source repository

[lericson/pylibmc](https://github.com/lericson/pylibmc)

---
*Parsed on 2026-04-15 by [repolex](https://repolex.ai)*
