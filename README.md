# Repolex Knowledge Graph of beeware/galley

RDF knowledge graph data for [beeware/galley](https://github.com/beeware/galley), parsed by [repolex](https://repolex.ai).

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
rlex download beeware/galley
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f56c310ce23389ea8ba11c3e8bffea036a8b04c7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f56c310ce23389ea8ba11c3e8bffea036a8b04c7
│           └── chunk-001.nq.gz
├── blob
│   ├── 059e15b1a4b87a965e950425d0882d419449d14a.nq.gz
│   ├── 216107e99c72db0dd8fe55c77b83101892d3557d.nq.gz
│   ├── 21d42af8cea534da6f8868f10199fca9fcd3254a.nq.gz
│   ├── 23924d0dcdacd4f7f2311c99dea304990f122eca.nq.gz
│   ├── 266ab509cac994f411719d1144584ccde31add77.nq.gz
│   ├── 28ab163544fd9275d5a3dc7b8054511b093cc20a.nq.gz
│   ├── 3be73d8dfcdb985baaeecfffa0e950cda51c824f.nq.gz
│   ├── 4c571235702c29e5b066612cc8de186af494f6fd.nq.gz
│   ├── 54f6dfbe24e5d93fbe7fcdd7f2f6b4e73f6f13de.nq.gz
│   ├── 5b3db852c781f21a670dbed4a50863dc70995c7b.nq.gz
│   ├── 667ef49741f568336d49a63a4206940979ddc477.nq.gz
│   ├── 785768626bd2b454ad2b2351190b93c3e79ff768.nq.gz
│   ├── 791f075d0cee746358d873db14962cbec7481d46.nq.gz
│   ├── 8dced5e470a657fd9a5f7cfb1f9188098ed60dca.nq.gz
│   ├── 92acaa527459878349b4e4312e0130b9cd9e6e6b.nq.gz
│   ├── 96471135ec137a56415577c5d3a3b8dfb6f6368d.nq.gz
│   ├── ad3ff087dd1c557147c9540e0fe241609515ebe4.nq.gz
│   ├── adabc12ae45e8749e55cd7272176e3c0e9a3b69d.nq.gz
│   ├── b26efd011bdbacbf8274ba0c35513c47bb48d304.nq.gz
│   ├── b7c009ea5d91338124cb2feff0d82b4c41f5b797.nq.gz
│   ├── c0ee0ee11c4b5dcd00b9d14251aed268855dd9ce.nq.gz
│   ├── d23014fc073fbb6e7aa4bae1227d8960aa04aaf9.nq.gz
│   ├── da4fa2d99d9de700f0e3ae5d7113e47c741dc665.nq.gz
│   ├── db180110f776b47db83f8f28ee37a5c7ff2b9be2.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ff0f7870a6830e8772ce32ad8bb31ac4b1525693.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f56c310ce23389ea8ba11c3e8bffea036a8b04c7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[beeware/galley](https://github.com/beeware/galley)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
