# Repolex Knowledge Graph of simonw/llm-mistral

RDF knowledge graph data for [simonw/llm-mistral](https://github.com/simonw/llm-mistral), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/llm-mistral
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1b8807821fddcca2b6b4ec4326abcf45553977f9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1b8807821fddcca2b6b4ec4326abcf45553977f9
│           └── chunk-001.nq.gz
├── blob
│   ├── 08e5a89944f0c4b69001d695482561324c48fcfd.nq.gz
│   ├── 0b270db47494e25979f2b06115275960a546132a.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 58b421648c216266404c8ae458e28e9e1ee9a6dd.nq.gz
│   ├── 68e50d9c0bb3cae2428fe3fa06ba534ca6333ce0.nq.gz
│   ├── 6da19adfc1a795b1688b12156b3045de037c7668.nq.gz
│   ├── 77f89963599da4e4f9a81ac0f33d4d0b98f8eb8b.nq.gz
│   ├── 7cb8f79506ce197da40d29609928790920b6613b.nq.gz
│   ├── 8a8fbe3061df604bc1122d3e75ad7ea67ede3449.nq.gz
│   ├── 8d22aaee205adeba1855d89f910db02ee45a4474.nq.gz
│   ├── 9c774ec9413e758a49655c7de34a6ccf0c476aa3.nq.gz
│   ├── 9f2608f5ce3df43cd2f2e5e8c1f1ea5c94b4f696.nq.gz
│   ├── b419f80b3e82e37b9eb11aabab43383783df49f9.nq.gz
│   ├── b7f5180cb593474d77e65d1488c2589533c01028.nq.gz
│   ├── bb6321427f71bc1a5385aaff4123fe17042cb8b0.nq.gz
│   ├── bd1c5a4321136fac14df4714fc2ee602531dc289.nq.gz
│   ├── cfefd88c6a437dada7f3b32b451aca402cb3ebf1.nq.gz
│   ├── d0d5ce3ee8fa6494d61b4f902ee7d8de943e1b36.nq.gz
│   └── d7b3abad0fd3c602f1a846d405ebb771ac44d379.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1b8807821fddcca2b6b4ec4326abcf45553977f9.nq.gz
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

[simonw/llm-mistral](https://github.com/simonw/llm-mistral)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
