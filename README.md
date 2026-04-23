# Repolex Knowledge Graph of tokio-rs/slab

RDF knowledge graph data for [tokio-rs/slab](https://github.com/tokio-rs/slab), parsed by [repolex](https://repolex.ai).

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
lexq download tokio-rs/slab
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2e5779f8eb318827c78cad38007445a93ec04503
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 2e5779f8eb318827c78cad38007445a93ec04503.nq.gz
│   └── repolex
│       └── 2e5779f8eb318827c78cad38007445a93ec04503
│           └── chunk-001.nq.gz
├── blob
│   ├── 1d4a204e4794f6231b467d520a516cd108ed8d9b.nq.gz
│   ├── 3a080ca104bb7a37964dd65ebf752848cd66aca9.nq.gz
│   ├── 428138937ae8765e077de5c9e91a3f7badf73c65.nq.gz
│   ├── 819ce21187da4043f615b816bbd0114a4d9fd782.nq.gz
│   ├── 894d59c119849354b9dd060ecaa577c5a89e5ef1.nq.gz
│   ├── 8e50a2016ed7efac24e7ee4e8d3e836e23cc3a2e.nq.gz
│   ├── b235e4dc4c64c95fd88a7bf2958cd6e9de17950f.nq.gz
│   ├── b9c9bd561d0ab40faa7db69774406f66b865ddf5.nq.gz
│   ├── ba5992a2b9f5d4aad839d098d7c62016499a18f9.nq.gz
│   ├── c9a2e91753b2da89371c13e6352255c95ea85563.nq.gz
│   ├── dd13739c283d2ae24097ebf7b519a26c1f11dfd9.nq.gz
│   └── e4315d63f7e87139aff9551ce11a931c1c9cd953.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 2e5779f8eb318827c78cad38007445a93ec04503.nq.gz
├── filetree
│   └── 2e5779f8eb318827c78cad38007445a93ec04503.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 22 files
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

[tokio-rs/slab](https://github.com/tokio-rs/slab)

---
*Parsed on 2026-04-23 by [repolex](https://repolex.ai)*
