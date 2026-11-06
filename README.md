# Repolex Knowledge Graph of sphinx-contrib/sphinxcontrib-skeleton

RDF knowledge graph data for [sphinx-contrib/sphinxcontrib-skeleton](https://github.com/sphinx-contrib/sphinxcontrib-skeleton), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/sphinxcontrib-skeleton
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f59056109f5a18174e1756f33b9691fbccb0fd96
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f59056109f5a18174e1756f33b9691fbccb0fd96
│           └── chunk-001.nq.gz
├── blob
│   ├── 056a4d8742029b5f9ded11a82eba064130c22e0e.nq.gz
│   ├── 0af9db66857239a0ff444247ce11b26071891ed0.nq.gz
│   ├── 143e5836101ca22f493fe88a23e8549f7db94c68.nq.gz
│   ├── 15c7415a822c4f7145627f722c9eb152229232df.nq.gz
│   ├── 1c8eeacc371db2d43cabf8bd733742941510a08d.nq.gz
│   ├── 25ea0037d2b211976b61ceaea593a6862843c5fe.nq.gz
│   ├── 2768b3960ad28c3d227a73190754a934fecef8b4.nq.gz
│   ├── 2bc5d5f7118646c11eac4472d076e00ffdd1a944.nq.gz
│   ├── 378da85f196918c5f31729cd23b10a02ec9216d3.nq.gz
│   ├── 3871e3212f07c6847ae40d5898fb9c3af201a05a.nq.gz
│   ├── 40f1fa977ebb0ccf4ef6718f8394db6eb10d29f4.nq.gz
│   ├── 418abc2e520c86fbf51baa1379cca73ae93b22af.nq.gz
│   ├── 591f2f5bb3e70e27d3f8d5383a5bd8b6b5d2cbfb.nq.gz
│   ├── 5b77c9c98d5a4bce8e13ae869260dfc580be0da7.nq.gz
│   ├── 67a39410ee195d351cca9b3ebec261e1945c1db1.nq.gz
│   ├── 6fec64165f3dfd92bd19b7a2d6a0aa784a013266.nq.gz
│   ├── 73750c8a3dce1b6e9a39ac170c5ca48c48262970.nq.gz
│   ├── 7a7d3aa00f7473a391afaf6915d53f82add64ca0.nq.gz
│   ├── 8237ac85582b45e76e6ce6e1b71afae48c107bc8.nq.gz
│   ├── 827d0738dc10284f7551bcd10c589d0e80f0610b.nq.gz
│   ├── 8287c4a2304b2b00b765bb43d1bcd7a702fab093.nq.gz
│   ├── 8d623501e9a76a7605bbcb5974a1e811da820e9b.nq.gz
│   ├── 98c064795a45a40f724d54f7df1cec99f0c26947.nq.gz
│   ├── a2396edf691a5ddf60c0dd7e4616b205eede5c47.nq.gz
│   ├── a33fd54299891a63d5fb3991e6aa516ef57833b1.nq.gz
│   ├── a9607973883998d4a1d9204cf96aeab5edaf2d57.nq.gz
│   ├── c16b575addc40f479ee27e4e1076647660a58d23.nq.gz
│   ├── c531f34f4ade93c19bd199e659f672d3320fb8e8.nq.gz
│   ├── c64649f1cb52c5735bf526d135d7f3ad5da684c5.nq.gz
│   ├── d9b2e79f96a2ffcf7b0d59ec5f88d2f9072ee1c8.nq.gz
│   ├── de09d048c1e869dccf0e2f59753a85fbcec66cf0.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f5c90c8de8f454101302a3ebdf34f1bfb1d72514.nq.gz
│   └── f9c309e0b4fcd39242dabd1d593cd7877b7493fb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f59056109f5a18174e1756f33b9691fbccb0fd96.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 42 files
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

[sphinx-contrib/sphinxcontrib-skeleton](https://github.com/sphinx-contrib/sphinxcontrib-skeleton)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
