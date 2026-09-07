# Repolex Knowledge Graph of BurntSushi/walkdir

RDF knowledge graph data for [BurntSushi/walkdir](https://github.com/BurntSushi/walkdir), parsed by [repolex](https://repolex.ai).

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
lexq download BurntSushi/walkdir
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4f26be4d450910916ea11533b2efc52b9a6483bc
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 4f26be4d450910916ea11533b2efc52b9a6483bc.nq.gz
│   └── repolex
│       └── 4f26be4d450910916ea11533b2efc52b9a6483bc
│           └── chunk-001.nq.gz
├── blob
│   ├── 12621cfb52d615f7131ab24792549dc61ea2fdd9.nq.gz
│   ├── 14bd4a9d26a4a141b197ac6338b933ff25933556.nq.gz
│   ├── 303d323e246e39d8682a13851975821c468e627f.nq.gz
│   ├── 3342d9b75620fe1f0ae7f529f7155771570bae06.nq.gz
│   ├── 3b0a5dc09c1e16357459ddc9182a50f360f3cdba.nq.gz
│   ├── 4b96df4be589e759fb54ed1c7c0e099c210511f8.nq.gz
│   ├── 5b7f7fbe8ed7164b9eced2ba74bbb3470ffad282.nq.gz
│   ├── 68a49daad8ff7e35068f2b7a97d643aab440eaec.nq.gz
│   ├── 7d36e2fdf4082e6c1147712907bd3e50c760f649.nq.gz
│   ├── aa37a218b97e5f6ad37a74a62b50727279a5e460.nq.gz
│   ├── adf54f7393902e1fb3373bee3c74967e52742192.nq.gz
│   ├── b9fcad8bf2d7574efb9d269467139ae02c0a233c.nq.gz
│   ├── bb9c20a094e41b7632d63bcff20c0b4b95e80777.nq.gz
│   ├── d63756d285dd799ac5668ae3c0ff3490724a9916.nq.gz
│   ├── e415b91824d626f42ac8130e0d3ccf531882f1b7.nq.gz
│   ├── e9df650eec8ecb0a01525ba17f5ad30dedeeefc6.nq.gz
│   ├── ebf952dfc55313eeb38da056ce0f8d45b10f5772.nq.gz
│   ├── f4e9c06f447a062fec9b837dabe1fe4f91647c30.nq.gz
│   └── fdf06f555e345da2445d82034891dffa786f0178.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 4f26be4d450910916ea11533b2efc52b9a6483bc.nq.gz
├── filetree
│   └── 4f26be4d450910916ea11533b2efc52b9a6483bc.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 29 files
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

[BurntSushi/walkdir](https://github.com/BurntSushi/walkdir)

---
*Parsed on 2026-09-07 by [repolex](https://repolex.ai)*
