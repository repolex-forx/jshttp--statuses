# Repolex Knowledge Graph of jshttp/statuses

RDF knowledge graph data for [jshttp/statuses](https://github.com/jshttp/statuses), parsed by [repolex](https://repolex.ai).

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
lexq download jshttp/statuses
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 33ec007ae094c35edb35d9edd293b9524b3adcb9
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 33ec007ae094c35edb35d9edd293b9524b3adcb9.nq.gz
│   └── repolex
│       └── 33ec007ae094c35edb35d9edd293b9524b3adcb9
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d779e417077dd48d063fbf3efea08b1e0ef4ce6.nq.gz
│   ├── 0e064f47bff27efdbdb6abc4063f834b7ea6a0b5.nq.gz
│   ├── 1333ed10bab28344b55c217d80ce4f6cc2555793.nq.gz
│   ├── 1eece14ad8cb98de2093fac5eef5ccee89472ff8.nq.gz
│   ├── 24bf1b225ce2584ca96c39654fa7f49d1a20bd1c.nq.gz
│   ├── 285d1bdae36c1acf9ac0db36433dfd0f6a3fcad8.nq.gz
│   ├── 28a31618205d7dbeed5b966fe9d2c682bd9367f5.nq.gz
│   ├── 4d801e674094206b422bac276c02e2c96c333991.nq.gz
│   ├── 4e6945384f6e19095af18af978571621d3b830e7.nq.gz
│   ├── 62562b74a3b5a79e82ca417b02e0f597d85f5e2f.nq.gz
│   ├── 70de9aae7e3a3f56310f67ce2258e9c6349fe04a.nq.gz
│   ├── 781850b061e489fd22d21e283a4a7064d52f2ef6.nq.gz
│   ├── 89d542f6a4022fa409b0c38875c1c15991081a23.nq.gz
│   ├── 947fac752e1d4488b4189838e3de1ef522d1ba92.nq.gz
│   ├── 97a487b882ec8e46093cfe5b9ba690212a8f6d68.nq.gz
│   ├── 9808c3b2b6602da61eb4afcb4caf33368e3e2bd4.nq.gz
│   ├── 9c120aafda38d3aff2b4bff0791e9f07642b5aed.nq.gz
│   ├── a46715d358e0284f7dcbe69a400223f2957cff6c.nq.gz
│   ├── ac92c286d6c5ea7801e1b10547270666b445040b.nq.gz
│   ├── b5d016edd9c4eef0bb227af4a01c49e73c5f78dc.nq.gz
│   ├── b8a2b0e883a945eaf7e0cc82f67ac31c964bccf7.nq.gz
│   ├── dc549b8216582796d92fb78868317155cc6d1044.nq.gz
│   ├── e0877b326b6d812d6613315304b69ded5f546152.nq.gz
│   ├── e1ecb979ba5bc9b4b2836586aae0894bce8aee7b.nq.gz
│   ├── ea351c553520e1bc62d53b97a316194c48ac49e6.nq.gz
│   └── f79d1361ce1a3a3a15b2ea0a8dca38c8fc74e952.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 33ec007ae094c35edb35d9edd293b9524b3adcb9.nq.gz
├── filetree
│   └── 33ec007ae094c35edb35d9edd293b9524b3adcb9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 36 files
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

[jshttp/statuses](https://github.com/jshttp/statuses)

---
*Parsed on 2026-09-15 by [repolex](https://repolex.ai)*
