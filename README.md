# Repolex Knowledge Graph of napari/napari-geojson

RDF knowledge graph data for [napari/napari-geojson](https://github.com/napari/napari-geojson), parsed by [repolex](https://repolex.ai).

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
rlex download napari/napari-geojson
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9afb835059f622ddc1e733ac4bf0240902b51e16
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9afb835059f622ddc1e733ac4bf0240902b51e16
│           └── chunk-001.nq.gz
├── blob
│   ├── 04d4946a9b86a5e21890a78a2e80fd3ddeaa5395.nq.gz
│   ├── 0b57db6f45516801fa696a0438073a8c6f9daef1.nq.gz
│   ├── 1d6c076dce351662899df799e47e56485eb4e1c8.nq.gz
│   ├── 2ca81b0b6a4c42444df705cd55237f528788dd91.nq.gz
│   ├── 3246066353912776e5d90bd36aa166340fe2196d.nq.gz
│   ├── 3fd079962c60a55d3d795aad0727510903beb489.nq.gz
│   ├── 564f8df24daed149499d246334905e563159a014.nq.gz
│   ├── 56f680135d212301e5274e6ad806165704bae082.nq.gz
│   ├── 608df43c5ff3f205177cd6eeae5732082ca1d9d1.nq.gz
│   ├── 6d6fa7d53c7e605b7db36285eb2f9f513a2eb62d.nq.gz
│   ├── 727c93686a922b3fe572234ff56ce8682a2eb802.nq.gz
│   ├── 763599a8bcb33533c828399bbfdb83bdc2dd7228.nq.gz
│   ├── 7eef76a70a3a0005ab92a40ff43ff6622195e405.nq.gz
│   ├── 85aa7ac39e87d59f94aec771222c3810bdd215e2.nq.gz
│   ├── 8a7054e8afd2b1e5e61f5c89c2743e9ebc0e6ca8.nq.gz
│   ├── 9d7268ed97246cb3ac5d3c46acf7490114f19fb1.nq.gz
│   ├── b2f8a0ed1214ca3c009a528eb8b1dc2ce73d0185.nq.gz
│   ├── c6dbaa15fc388f632ef97c2c230d0cb0a36d60b4.nq.gz
│   ├── cd6ccc7ad9f70b61efba1ecd9665234cc7970efe.nq.gz
│   ├── da12a8d9641b9298226940a6e9e1a8995dffb98e.nq.gz
│   ├── da77522b7cf7223450714f35fd3326e798c4ea2f.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ec86bc70e6fb8e9f8c4ca6d443c37ccf06ddf2ed.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9afb835059f622ddc1e733ac4bf0240902b51e16.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[napari/napari-geojson](https://github.com/napari/napari-geojson)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
