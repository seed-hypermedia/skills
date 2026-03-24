# Seed Hypermedia Agent Skills

Agent skills for reading and writing content on the [Seed Hypermedia](https://hyper.media) protocol.

## Skills

### seed-cli

Document operations via the [Seed CLI](https://www.npmjs.com/package/@seed-hypermedia/cli) (`seed-cli`).

- Create, update, and read documents
- Create comments and replies
- Search across the network (keyword + semantic)
- Manage drafts and signing keys
- Round-trip editing with block-level diffing
- **No local daemon required** — connects to remote servers (`hyper.media` by default)

### seed-grpc

Low-level gRPC access to the local Seed daemon via `grpcurl`.

- List and query accounts, documents, directories
- Inspect document changes, refs, and versions
- Access daemon APIs not exposed by the CLI
- **Requires a running local Seed daemon**

## Installation

### Claude Code

```
/plugin marketplace add seed-hypermedia/skills
/plugin install seed-hypermedia@seed-hypermedia-skills
```

After installation, skills are available as `/seed-hypermedia:seed-cli` and `/seed-hypermedia:seed-grpc`.

### Other agents

Copy the skill directories from `plugins/seed-hypermedia/skills/` into your agent's skill loading path. Each skill is a self-contained directory with a `SKILL.md` entry point.
