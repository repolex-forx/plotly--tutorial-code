# Repolex Knowledge Graph of plotly/tutorial-code

RDF knowledge graph data for [plotly/tutorial-code](https://github.com/plotly/tutorial-code), parsed by [repolex](https://repolex.ai).

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
rlex download plotly/tutorial-code
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b4d81b4fb5e4eae9c786f5a35cc731b5ede5faf4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b4d81b4fb5e4eae9c786f5a35cc731b5ede5faf4
│           └── chunk-001.nq.gz
├── blob
│   ├── 00ff76d00d8eaef1dd5b75dfcc6f337d7fa7932b.nq.gz
│   ├── 0524bf150ed06e57e9de696bd13962ef910d9340.nq.gz
│   ├── 07994a287286f03ecabd1b5f9227112a37ad67a2.nq.gz
│   ├── 1b68a8e36faf87d57d310b4279e271724371c7fa.nq.gz
│   ├── 1e4520333a12aaa29caf4a55d6269b6272c4eefb.nq.gz
│   ├── 22d92ca03f72548b7b918c9b87b889474e68016a.nq.gz
│   ├── 3705aa0af2e099bb6ad298554afebcecdd359303.nq.gz
│   ├── 3720a46243097c5f2443354432e217612c268e17.nq.gz
│   ├── 5d29217705c888ca0aee9e9bf3339b51963b10ff.nq.gz
│   ├── 5e9ddfb2a92be5eecf9d638bff405f4064a3442c.nq.gz
│   ├── 6e954ac74e47f73ceff931cf16194244e95f2210.nq.gz
│   ├── 793994ed3f7d89e8d7757967ba14c260813dc687.nq.gz
│   ├── 9c070615be0aaa4f35b35a0317084f613238457f.nq.gz
│   ├── aadbf3a3ef21ede969b874ff89ebc835933ae533.nq.gz
│   ├── b1febe4e2a7832b6f38c08e02ab79582a04d9159.nq.gz
│   ├── b1ffde0b37fb4ddedac284560ecf4b551cb6cf21.nq.gz
│   ├── b4f0cba38faec7b2f7ac7e21c39bf8cde7106e16.nq.gz
│   ├── b9d309d36e5bda0e344846e2dff901f9ce7bcfd4.nq.gz
│   ├── bc8371522911dae5c57fa15028a9c84eeb316709.nq.gz
│   ├── ca2da28f93f86cf53d6f8f2fb8a4a54cd75c4685.nq.gz
│   └── edd222784ef71e70c7208722e8d9b50fa831d8b2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b4d81b4fb5e4eae9c786f5a35cc731b5ede5faf4.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 28 files
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

[plotly/tutorial-code](https://github.com/plotly/tutorial-code)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
