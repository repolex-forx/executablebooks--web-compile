# Repolex Knowledge Graph of executablebooks/web-compile

RDF knowledge graph data for [executablebooks/web-compile](https://github.com/executablebooks/web-compile), parsed by [repolex](https://repolex.ai).

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
rlex download executablebooks/web-compile
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 22218c310227990799cd48705ef86d6af0ca5abc
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 22218c310227990799cd48705ef86d6af0ca5abc
│           └── chunk-001.nq.gz
├── blob
│   ├── 112cfa9abb56789bed29937b26f9b49ffda54700.nq.gz
│   ├── 1222df9544fd6b4ffe1f35407cac9d2816767f4a.nq.gz
│   ├── 1dece0df14aa9f7fc46e47ce45ea10ab563b6948.nq.gz
│   ├── 2a08e1cec4aa469911e5692d0c23f0635b63ad41.nq.gz
│   ├── 303833ade0785f393827b171ada3e80f8316af9d.nq.gz
│   ├── 4778ab5d11b692fd73f5f4b1997fb8e9620293ba.nq.gz
│   ├── 539b7990a5e8adc5f71d0cc6e4c86da3b1e70ee5.nq.gz
│   ├── 90d6ca3c139edfec5efc57063e564636c3e2714a.nq.gz
│   ├── a27379730ab519ab54edbc3919f6acb0e974bcf3.nq.gz
│   ├── ab93c53ba3b92597fdd8f0087533f11447573d54.nq.gz
│   ├── ce2907cb00ccda8e25260d3c81f37870a2ed127b.nq.gz
│   ├── cf25f54c4a6fddcf13c9aa99897125e7d506e828.nq.gz
│   ├── d444ecaae47833d703970518ac134f899098e3e8.nq.gz
│   ├── d5ff1ddd6c742ba7c15d4d270fa2ab71dfff040e.nq.gz
│   ├── da970b8f2564ca5b6fd046ef8f6c24ef3b17cc7f.nq.gz
│   ├── dda9865ad01e8f6ecebfc69f0889c81050a594f0.nq.gz
│   ├── e2786cf9f780317ae9ea8340ec8e3a056026b46a.nq.gz
│   ├── e3658dc6690a15b0ea6b7211738da480769455e8.nq.gz
│   ├── e821a610a1775fccd0871057add6b15f1bbc84f4.nq.gz
│   ├── ebfc9573f88778d70c071251c58ccf6116c0412c.nq.gz
│   ├── ec09f900b842a77b79ecf9fb717606785c4f233f.nq.gz
│   └── f77c37c65be37596841837655a93840c424fac3d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 22218c310227990799cd48705ef86d6af0ca5abc.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 30 files
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

[executablebooks/web-compile](https://github.com/executablebooks/web-compile)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
