# Java Knowledge Base

A senior/lead-level Java interview-preparation knowledge base covering language internals, the JVM, frameworks, distributed systems, data, design, and production troubleshooting.

## Source of truth

Markdown under [`content/`](content/) is canonical. PDFs under `pdfs/` are generated reading material and must not be edited by hand.

## Topics

| Topic | Canonical content |
| --- | --- |
| Core Java | [`content/core-java/`](content/core-java/) |
| Modern Java | [`content/modern-java/`](content/modern-java/) |
| Collection internals | [`content/collection-internals/`](content/collection-internals/) |
| Concurrency | [`content/concurrency/`](content/concurrency/) |
| JVM | [`content/jvm/`](content/jvm/) |
| Spring | [`content/spring/`](content/spring/) |
| Microservices | [`content/microservices/`](content/microservices/) |
| Database and JPA | [`content/database-jpa/`](content/database-jpa/) |
| System design | [`content/system-design/`](content/system-design/) |
| Troubleshooting | [`content/troubleshooting/`](content/troubleshooting/) |
| Data structures | [`content/data-structures/`](content/data-structures/) |
| Design patterns | [`content/design-patterns/`](content/design-patterns/) |

## Repository layout

```text
content/          Canonical Markdown knowledge source
pdfs/             Generated PDFs, grouped by topic
assets/diagrams/  Shared diagrams and source files
pdf-generator/    Markdown-to-PDF tooling
rag/              Retrieval and indexing experiments
mcp-server/       MCP server integration
evaluation/       Quality checks and evaluation datasets
```

## Content conventions

- Prefer one focused question or concept per Markdown file.
- Use lowercase kebab-case filenames, for example `hashmap-resize-mechanics.md`.
- Begin with a clear title, then cover the short answer, internals, trade-offs, failure modes, and follow-up questions where relevant.
- Store reusable diagrams in `assets/diagrams/` and link to them with relative paths.
- Update Markdown first; regenerate PDFs afterward.
- Never commit credentials, tokens, private keys, local indexes, or environment files.

## Local setup (Windows PowerShell)

```powershell
git clone https://github.com/kuldeep-singh-rathore/Java_KB.git
Set-Location Java_KB
git status
```

Git for Windows includes Git Credential Manager. When GitHub authentication is required, it opens a secure browser sign-in; do not put a personal access token in a command, file, or chat.

Optional GitHub CLI setup:

```powershell
winget install --id GitHub.cli
gh auth login --web --git-protocol https
gh auth status
```

## Contribution workflow

```powershell
git switch -c content/jvm-gc-basics
# Edit Markdown files.
git status
git add content assets
git diff --cached
git commit -m "docs(jvm): add garbage collection fundamentals"
git push -u origin content/jvm-gc-basics
```

Generated files should be reproducible from the canonical Markdown source.
