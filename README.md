# Plugins

A Claude Code plugin marketplace.

## Installation

Add the marketplace:

```
/plugin marketplace add nijesmik/plugins
```

Then install a plugin:

```
/plugin install openwiki@nijesmik
/plugin install deepwiki@nijesmik
```

## Plugins

| Plugin | Source | Description |
|--------|--------|-------------|
| [openwiki](https://github.com/nijesmik/openwiki) | `nijesmik/openwiki` | Generate and maintain OpenWiki documentation for a codebase. Claude Code plugin packaging of langchain-ai/openwiki with the original prompts preserved verbatim. |
| [deepwiki](https://github.com/nijesmik/deepwiki-open) | `nijesmik/deepwiki-open` | DeepWiki as a Claude Code plugin: wiki generation, repository Q&A, and deep research using the original DeepWiki prompts with agentic codebase exploration instead of RAG. |

## Updating

Refresh your local copy of the marketplace to pick up new plugin versions:

```
/plugin marketplace update nijesmik
```
