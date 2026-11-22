# Repolex Knowledge Graph of alexcrichton/ssh2-rs

RDF knowledge graph data for [alexcrichton/ssh2-rs](https://github.com/alexcrichton/ssh2-rs), parsed by [repolex](https://repolex.ai).

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
rlex download alexcrichton/ssh2-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5b39b5fabb6b5a6b953519a571cd6af30d460ac3
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 5b39b5fabb6b5a6b953519a571cd6af30d460ac3.nq.gz
│   └── repolex
│       └── 5b39b5fabb6b5a6b953519a571cd6af30d460ac3
│           └── chunk-001.nq.gz
├── blob
│   ├── 09e06f5fcc3a74a04cffbd52b22c975f8ef6b001.nq.gz
│   ├── 0c4394c5b53d6e2f29e7e03a7323b906da01ab15.nq.gz
│   ├── 113a0aecd40c2370076de1b185097f8057c2b22f.nq.gz
│   ├── 1447bdc1dd9d74f708397adc3c8ac4b0e8204178.nq.gz
│   ├── 1692a9de9fab7a10d5ac066337996bb10d4b2055.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 1e1c92466ed7efaef14d841f30748ceee4409878.nq.gz
│   ├── 1f5b85d3433f93cc364fadde40f3621234e4cf41.nq.gz
│   ├── 27280b85e763cf43282e30ac22d4ec9967f4782d.nq.gz
│   ├── 27a1e7c6ec3be9547bbb5d8c20b957daeb012f34.nq.gz
│   ├── 2a0ab75f0d8bb9554fe82ff07313b45dc217446b.nq.gz
│   ├── 2e2d651b9a1a83f3969ad23646c5150a1ae5d414.nq.gz
│   ├── 39e0ed6602151f235148e6c08413aa7eda5b9038.nq.gz
│   ├── 49155945653b38bf43235b618d89d4d50decbd7d.nq.gz
│   ├── 6fbdf1661c65917650266bc57c33c092c9f6da9e.nq.gz
│   ├── 70325a0d4da31ea925d8b9f3baedca56b0015210.nq.gz
│   ├── 75ba0af9f009e9b8b6ec46d8cdab9662f3edec23.nq.gz
│   ├── 8d5918b9d4340603c88496024cb7166fdf69c0cd.nq.gz
│   ├── 901add7ffa44a14fd68c2140bbdc48e70a73aa95.nq.gz
│   ├── 9a6e44f6c66b221f59ece50c1e48979e5d367023.nq.gz
│   ├── 9ee862fe66013bcd1c77233d19aacfd5bbd07c7a.nq.gz
│   ├── a6bfd12104492ae5e8825e73341424fe543dedb9.nq.gz
│   ├── ab835773909b1cfbf0edd83e7b5bb411bbf335fa.nq.gz
│   ├── acc380b5351938f0bfd58f7fd77f8530593fd68f.nq.gz
│   ├── b3a796395addd2c4f4aad7028abf998a701833aa.nq.gz
│   ├── c6d15906164a1803b93b62e43e993053ff86b261.nq.gz
│   ├── ccd2912afb962762c9ed13c3a140b881767a2d22.nq.gz
│   ├── d020e501336045b46ed952c39cb94cca5b3b795f.nq.gz
│   ├── dd4d24931a52a832f5c4feeb18240f961f7da1f3.nq.gz
│   ├── e0dc315234de11e59a79e14d0322180bce81ec8c.nq.gz
│   ├── e72ebeafc6650660d090704e15c3d6be00c21f40.nq.gz
│   ├── eb7ea25bb67b3dcf04027e6c30326049159bde58.nq.gz
│   ├── ee0fc5d28fa776c20ae5292fc86c30b18b75ef46.nq.gz
│   └── f58613d4937488efa07381803db0e8afe0678b75.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 5b39b5fabb6b5a6b953519a571cd6af30d460ac3.nq.gz
├── filetree
│   └── 5b39b5fabb6b5a6b953519a571cd6af30d460ac3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 44 files
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

[alexcrichton/ssh2-rs](https://github.com/alexcrichton/ssh2-rs)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
