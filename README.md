# Plugins

A plugin marketplace for Claude Code and Codex.

## Plugins

| Plugin | Source | Claude Code | Codex | Description |
|--------|--------|:-----------:|:-----:|-------------|
| [openwiki](https://github.com/nijesmik/openwiki) | `nijesmik/openwiki` | ✅ | — | Generate and maintain OpenWiki documentation for a codebase. Claude Code plugin packaging of langchain-ai/openwiki with the original prompts preserved verbatim. |
| [deepwiki](https://github.com/nijesmik/deepwiki-open) | `nijesmik/deepwiki-open` | ✅ | ✅ | DeepWiki as a plugin: wiki generation, repository Q&A, and deep research using the original DeepWiki prompts with agentic codebase exploration instead of RAG. |
| [brag-doc](https://github.com/nijesmik/brag-doc) | `nijesmik/brag-doc` | ✅ | ✅ | Cluster your git/PR contributions in any repo into analysis docs: a theme overview plus per-topic deep dives from PR diffs. |

## Claude Code

Add the marketplace:

```
/plugin marketplace add nijesmik/plugins
```

Then install a plugin:

```
/plugin install openwiki@nijesmik
/plugin install deepwiki@nijesmik
/plugin install brag-doc@nijesmik
```

Refresh your local copy of the marketplace to pick up new plugin versions:

```
/plugin marketplace update nijesmik
```

## Codex

Add the marketplace:

```
codex plugin marketplace add nijesmik/plugins
```

Then install a plugin:

```
codex plugin add deepwiki@nijesmik
codex plugin add brag-doc@nijesmik
```

Browse and toggle installed plugins with `codex /plugins`, and refresh the
marketplace snapshot to pick up new plugin versions:

```
codex plugin marketplace upgrade nijesmik
```

`openwiki` is not listed for Codex yet: it ships its workflows as Claude Code
`commands/`, and Codex only migrates commands under 4 KB into skills, so both of
its commands would be silently dropped. It needs `skills/` in its own repo first.

## Layout

Each host reads its own catalog from this repo, so the two listings can differ:

| File | Read by |
|------|---------|
| `.claude-plugin/marketplace.json` | Claude Code |
| `.agents/plugins/marketplace.json` | Codex |

Codex also falls back to `.claude-plugin/marketplace.json`, but only
`.agents/plugins/marketplace.json` uses source types Codex understands
(`url`, `git-subdir`, `local`, `npm`) — so keep the Codex catalog there.
