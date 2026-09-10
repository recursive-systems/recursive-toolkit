# Recursive Systems Toolkit

Free AI workspace cleanup and app maturity reviews, packaged as Claude skills. The plugin contains instructions only: no hooks, MCP servers, or bundled executable scripts.

## Install in Claude Code

```sh
claude plugin marketplace add https://github.com/recursive-systems/recursive-toolkit.git
claude plugin install recursive-systems@recursive-systems
```

Start a new Claude Code session and use:

```text
/recursive-systems:workspace-cleanup
/recursive-systems:app-maturity-review
```

The assistant needs access to the project you want reviewed. Cleanup proposes changes unless editing is already authorized; app maturity review makes recommendations only.

## Keep it updated

In Claude Code, open `/plugin`, select **Marketplaces → recursive-systems → Enable auto-update**. Third-party marketplaces do not enable this by default. Updates are checked in the background after startup; the current session retains its loaded version. Follow the reload notification or start a new session to use updated skills.

For an immediate update:

```sh
claude plugin marketplace update recursive-systems
claude plugin update recursive-systems@recursive-systems
claude plugin details recursive-systems@recursive-systems
```

Then start a new session. Do not edit installed cache files: an update replaces them. Keep personal preferences in your project's own instructions.

## Claude Desktop / Cowork

1. Open **Customize → Plugins → Add plugin → Add marketplace → Add from a repository**.
2. Enter `https://github.com/recursive-systems/recursive-toolkit.git`, select **Use URL**, leave **Sync automatically** enabled, and select **Sync**.
3. Under **Personal → recursive-toolkit**, install **Recursive systems**.
4. In a new Cowork conversation, type `/` and choose **app-maturity-review** or **workspace-cleanup**.

Desktop installation, visibility of both skills, and a Cowork app maturity review were verified on September 10, 2026. If Desktop says the plugin is enabled but cannot sync, **View → Reload** resolved that condition in our pilot.

The marketplace menu offers **Check for updates**. Automatic syncing was enabled, but neither a completed Desktop release update nor its automatic timing has been verified yet. Our update test was interrupted by the desktop-control connection timing out; Desktop last showed 0.1.2 after 0.1.3 was published. Claude Code's manual update path above is verified separately.

There is no public directory listing or verified one-click installation link yet.

## Develop and release

Edit the canonical files in `plugins/recursive-systems/skills/`. Preserve the approved prompt bodies when changing packaging. Run:

```sh
claude plugin validate .
claude plugin validate plugins/recursive-systems
```

For every skill change, bump `version` in `plugins/recursive-systems/.claude-plugin/plugin.json`, update `CHANGELOG.md`, and merge a pull request into the default branch. Do not push releases directly to the default branch. The marketplace deliberately does not repeat the version: the plugin manifest is authoritative. Validate an update with the commands above and inspect the installed files before declaring success.

The website keeps generated copies for standalone builds. From the website checkout, run `npm run tools:sync -- /path/to/recursive-toolkit`, then `npm run tools:check -- /path/to/recursive-toolkit`. Commit and release website changes separately. Its `src/tools/source.json` records the toolkit version, commit, and hashes. Adding a skill does not automatically add a website card.

## References

- [Claude plugin authoring](https://code.claude.com/docs/en/plugins)
- [Marketplace updates](https://code.claude.com/docs/en/discover-plugins#configure-auto-updates)
- [Claude Cowork installation](https://claude.com/docs/cowork/guide/plugins)
