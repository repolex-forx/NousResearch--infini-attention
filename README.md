# Repolex Knowledge Graph of NousResearch/infini-attention

RDF knowledge graph data for [NousResearch/infini-attention](https://github.com/NousResearch/infini-attention), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/infini-attention
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9387ae1cf7d5ffc1984c1da547e70fd5f74575df
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9387ae1cf7d5ffc1984c1da547e70fd5f74575df
│           └── chunk-001.nq.gz
├── blob
│   ├── 022c432ad91568a978085ec0a8fa30898bca373c.nq.gz
│   ├── 1fdb5a454003e6de87b228df72eef211bbbf6467.nq.gz
│   ├── 4e18647f1522ceb18d0321eb35469c0903cec609.nq.gz
│   ├── 4fb9ac2b450926a2598e545a00a72251a13905b6.nq.gz
│   ├── aea4262da8b5b9be26328e0ce1e20447e5945904.nq.gz
│   ├── d626258b6ae154cef0086e0bae84a5ecbe0523f1.nq.gz
│   ├── da85b36e6a527eeb5bc6f6253831019650e348d1.nq.gz
│   ├── e357793560940ddd1dd4eaef8a55fc1f921a67ba.nq.gz
│   ├── f374792deed0782d751a604978625b2c71ea4e8d.nq.gz
│   └── f3e9c3bf072d5a45d5183765047fe35537139fd9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9387ae1cf7d5ffc1984c1da547e70fd5f74575df.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 16 files
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

[NousResearch/infini-attention](https://github.com/NousResearch/infini-attention)

---
*Parsed on 2026-11-02 by [repolex](https://repolex.ai)*
