# Repolex Knowledge Graph of pypa/pipfile

RDF knowledge graph data for [pypa/pipfile](https://github.com/pypa/pipfile), parsed by [repolex](https://repolex.ai).

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
rlex download pypa/pipfile
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4706d2cbd35e0b47a05a6421fa17f93827bc454f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4706d2cbd35e0b47a05a6421fa17f93827bc454f
│           └── chunk-001.nq.gz
├── blob
│   ├── 091df136ec7a261a930c100a60fa6a1128f735fc.nq.gz
│   ├── 0e11301413d5e3dbafa3112bd5460380e54f5253.nq.gz
│   ├── 0f90c2961cfaee9cc1040304eb6081b6bddce150.nq.gz
│   ├── 15f8541484326d0586d659e26b2b5cea424626d2.nq.gz
│   ├── 1764fa54693ed69bef9147720198a5ca69875169.nq.gz
│   ├── 1c159dc05f88c8ee241e80d1e23105d80cecec3f.nq.gz
│   ├── 20e3224e67a5eba1c4f0f0aa1614a60d46638711.nq.gz
│   ├── 2556d74aecf22428d1b7c8d00620c9c9d0ccbbda.nq.gz
│   ├── 3846a8f4b63e67e8d91fdad523c6d2bdc5f9d166.nq.gz
│   ├── 3c6e79cf31da1c0433d2fa666bf50b53f6359f26.nq.gz
│   ├── 47280e7ea40abc9904b8e62d329c9cf22ab2ebd8.nq.gz
│   ├── 4947287f7b5ccb5d1e8b7b2d3aa5d89f322c160d.nq.gz
│   ├── 4f1810c6698bca1ed0d786fcf460425190ac366a.nq.gz
│   ├── 4fa453e2d0c74c09c88bc1de8bc15e05dd7f150a.nq.gz
│   ├── 565b0521d0c2cdbfe493d19765b04d5c119fa7eb.nq.gz
│   ├── 665b3af42a3ed81400f26fc6724bcdd534c8fa71.nq.gz
│   ├── 698fc43e20cc62fc549fb2b54d52411e9e19e58f.nq.gz
│   ├── 6f62d44e4ef733c0e713afcd2371fed7f2b3de67.nq.gz
│   ├── 9672d9cc1019d650d52f3742d67d646be0c6e3eb.nq.gz
│   ├── 97b0f754a0e0f1a87ad7aafee67eb7b0f09fcf73.nq.gz
│   ├── 9dfbe1e3ed7e4b8f274af43189a5de4c3959e978.nq.gz
│   ├── b876acebb90ccb2064b105b993b82c71b7fedb1f.nq.gz
│   ├── c1e2b52e96cd59908c8ee1a224da838170841508.nq.gz
│   ├── c3b4cbc1c197465b8d58e1e0b471076a20ec6343.nq.gz
│   ├── c713aff9d8b88c85c7fa66bd35ca53178413e970.nq.gz
│   ├── e357555238e424dc7efcc09ae508d6501ba71ec4.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f889c54da83962226add93cb45d899cf17530aee.nq.gz
│   ├── f94cd4f1df44c6b27b304cd7e8e9c59e72a225f7.nq.gz
│   ├── fddd4f90b9a23255ae12a237b315d98c858f803f.nq.gz
│   └── fde08fd7bf700446a3bb703ceac8988dc6544af9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4706d2cbd35e0b47a05a6421fa17f93827bc454f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 39 files
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

[pypa/pipfile](https://github.com/pypa/pipfile)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
