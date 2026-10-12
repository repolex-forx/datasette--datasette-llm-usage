# Repolex Knowledge Graph of datasette/datasette-llm-usage

RDF knowledge graph data for [datasette/datasette-llm-usage](https://github.com/datasette/datasette-llm-usage), parsed by [repolex](https://repolex.ai).

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
rlex download datasette/datasette-llm-usage
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a9269a83164c364c8758f36e327c79eb8fb174dc
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a9269a83164c364c8758f36e327c79eb8fb174dc
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 29dafe9560c8491b19e61f9b0a1072ff8c7cdb4d.nq.gz
│   ├── 3959c716eb0656c8aa08bba7377f722c450bfdce.nq.gz
│   ├── 6df5b9d447c8d8e2a127885f2630a0df1b40692e.nq.gz
│   ├── 9fd6c52c5c9c99c4080348096dcd00dcc25877d6.nq.gz
│   ├── aa38172836cfcfdeaa3872503fdf5326172d2684.nq.gz
│   ├── b188ea6c11220be74175212d5eb9680e863cf050.nq.gz
│   ├── b6cea7f41251e10917c10577f34e0c359b460407.nq.gz
│   └── d0d5ce3ee8fa6494d61b4f902ee7d8de943e1b36.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a9269a83164c364c8758f36e327c79eb8fb174dc.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[datasette/datasette-llm-usage](https://github.com/datasette/datasette-llm-usage)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
