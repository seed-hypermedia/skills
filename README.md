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

## Installation (Claude Code)

### 1. Add the marketplace

```
/plugin marketplace add seed-hypermedia/skills
```

### 2. Install the plugin

```
/plugin install seed-hypermedia@seed-hypermedia-skills
```

### 3. Reload

```
/reload-plugins
```

After installation, the agent can invoke the skills automatically based on context. You can also invoke them
explicitly:

- `/seed-hypermedia:seed-cli` — document operations via the Seed CLI
- `/seed-hypermedia:seed-grpc` — low-level gRPC access to the local daemon

### Updating

The plugin updates automatically when a new version is published. To force an update:

```
/plugin marketplace add seed-hypermedia/skills
/reload-plugins
```

Or check the current version:

```
/plugin
```

### Project-wide installation

To auto-enable the plugin for everyone working in a repository, add this to `.claude/settings.json`:

```json
{
  "extraKnownMarketplaces": {
    "seed-hypermedia-skills": {
      "source": {
        "source": "github",
        "repo": "seed-hypermedia/skills"
      }
    }
  },
  "enabledPlugins": {
    "seed-hypermedia@seed-hypermedia-skills": true
  }
}
```

Team members still need to run `/plugin marketplace add seed-hypermedia/skills` once to download the marketplace,
then `/plugin install seed-hypermedia@seed-hypermedia-skills` to install it.

## Other agents

Copy the skill directories from `plugins/seed-hypermedia/skills/` into your agent's skill loading path. Each skill
is a self-contained directory with a `SKILL.md` entry point. The shared `references/` directory at the plugin root
contains the Seed document format reference used by both skills.
