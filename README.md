# Fahad Marketplace

A Claude Code plugin marketplace by Muhammad Fahad.

## Install the marketplace

Inside Claude Code:

```
/plugin marketplace add sheikhfahad67/fahad-marketplace
```

Then install a plugin:

```
/plugin install <plugin>@fahad-marketplace
```

Or browse with `/plugin`.

## Available plugins

| Plugin | Version | Category | Description |
| --- | --- | --- | --- |
| [`taskify`](https://github.com/sheikhfahad67/taskify) | 0.1.0 | workflow | Write a plan plus executable task specs (`/taskify:taskify`), then run them task by task with implement → review and resumable progress (`/taskify:taskify-implementer`). |

## Get updates

```
/plugin marketplace update fahad-marketplace
```

## Adding a plugin

1. Put the plugin in its own repo, with `.claude-plugin/plugin.json` at the root.
2. Add an entry to `plugins[]` in `.claude-plugin/marketplace.json`. It needs at least `name`,
   `source`, `description` and `version`:
   ```json
   {
     "name": "my-plugin",
     "source": { "source": "github", "repo": "sheikhfahad67/my-plugin" },
     "description": "...",
     "version": "0.1.0"
   }
   ```
   For a plugin in a subfolder of a repo, use
   `{ "source": "git-subdir", "url": "https://github.com/owner/repo.git", "path": "sub/folder" }`.
   Add `"ref"` or `"sha"` to pin a branch, tag or commit.
3. Add a row to the table above.
4. Commit and push.

## Releasing a new plugin version

1. In the plugin's repo, bump `version` in `plugin.json`, update its changelog, and tag `vX.Y.Z`.
2. Here, bump the same `version` in its `marketplace.json` entry and in the table above.
3. Commit and push. Users run `/plugin marketplace update fahad-marketplace`.

## Schema

See the [Claude Code plugin marketplace schema](https://json.schemastore.org/claude-code-plugin-marketplace.json).
