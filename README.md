# Recursive Systems Toolkit

Free AI workspace cleanup, app maturity reviews, and business loop maps, packaged for ChatGPT, Codex, and Claude. The plugin contains instructions only: no hooks, MCP servers, or bundled executable scripts.

## Install in the ChatGPT desktop app

1. Open **Plugins → Add marketplace**.
2. Enter `https://github.com/recursive-systems/recursive-toolkit` and click **Add marketplace**.
3. Open **Personal** and click **+** beside **Recursive Systems**.
4. Start a new chat and ask to use **Workspace Cleanup**, **App Maturity Review**, or **Business Loop Map**.

The repository marketplace installation flow was confirmed by the maintainer on September 10, 2026. The new OpenAI metadata and branded icon still need an app-level check after syncing a release. The plugin provides its own logo and descriptions; OpenAI's documented marketplace metadata supports a display name but does not specify a marketplace-level icon.

Use the app's available marketplace sync/update controls to fetch releases. Automatic update timing and per-user opt-in behavior have not been verified. Standalone skill copies are not linked to marketplace updates; remove duplicate standalone copies after confirming the marketplace-installed skills are available.

## Included capabilities

- **Workspace Cleanup** audits AI workspace instructions and supporting files.
- **App Maturity Review** recommends practical improvements for apps built with AI.
- **Business Loop Map** maps recurring work and recommends safe first uses for AI.

Actual host acceptance for Business Loop Map remains pending; no scenario execution is claimed. The 0.1.6 version metadata in this pull request is a release candidate, not a published or host-validated release.

## Packaging

- `.agents/plugins/marketplace.json`: OpenAI-format repository marketplace.
- `.claude-plugin/marketplace.json`: Claude marketplace.
- `plugins/recursive-systems/plugin.json`: portable Agent Plugins manifest with OpenAI branding under `extensions.com.openai.interface`.
- `plugins/recursive-systems/.codex-plugin/plugin.json`: Codex compatibility manifest for hosts using the older format.
- `plugins/recursive-systems/.claude-plugin/plugin.json`: Claude plugin manifest.
- `plugins/recursive-systems/skills/`: shared, canonical skill instructions for both platforms.

Keep the three plugin manifests' versions and common metadata synchronized. Keep OpenAI interface metadata identical in the portable and Codex compatibility manifests. Brand assets live in the plugin's `assets/` directory. No separate copy of the skills is needed.

## Install in Claude Code

```sh
claude plugin marketplace add https://github.com/recursive-systems/recursive-toolkit.git
claude plugin install recursive-systems@recursive-systems
```

Start a new Claude Code session and use:

```text
/recursive-systems:workspace-cleanup
/recursive-systems:app-maturity-review
/recursive-systems:business-loop-map
```

The assistant needs access to the project you want reviewed. Cleanup proposes changes unless editing is already authorized; app maturity review and business loop map make recommendations only.

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
4. In a new Cowork conversation, type `/` and choose **app-maturity-review**, **business-loop-map**, or **workspace-cleanup**.

Desktop installation, visibility of Workspace Cleanup and App Maturity Review, and a Cowork app maturity review were verified on September 10, 2026. If Desktop says the plugin is enabled but cannot sync, **View → Reload** resolved that condition in our pilot.

The marketplace menu offers **Check for updates**. Automatic syncing was enabled, but neither a completed Desktop release update nor its automatic timing has been verified yet. Our update test was interrupted by the desktop-control connection timing out; Desktop last showed 0.1.2 after 0.1.3 was published. Claude Code's manual update path above is verified separately.

There is no public directory listing or verified one-click installation link yet.

## Develop and release

Edit the canonical files in `plugins/recursive-systems/skills/`. Preserve the approved prompt bodies when changing packaging. Run:

```sh
claude plugin validate .
claude plugin validate plugins/recursive-systems
```

Before a version bump, run the matching host scenarios in `evals/` and record results using the file's run-notes instructions. For every plugin release, bump `version` in all three plugin manifests, update `CHANGELOG.md`, and merge a pull request into the default branch. Do not push releases directly to the default branch. The marketplace deliberately does not repeat the version: the synchronized plugin manifests are authoritative. Validate an update with the commands above and inspect the installed files before declaring success.

The website keeps generated copies for standalone builds. From the website checkout, run `npm run tools:sync -- /path/to/recursive-toolkit`, then `npm run tools:check -- /path/to/recursive-toolkit`. Commit and release website changes separately. Its `src/tools/source.json` records the toolkit version, commit, and hashes. Adding a skill does not automatically add a website card.

## References

- [OpenAI plugin packaging and branding](https://developers.openai.com/plugins/build/plugins)

- [Claude plugin authoring](https://code.claude.com/docs/en/plugins)
- [Marketplace updates](https://code.claude.com/docs/en/discover-plugins#configure-auto-updates)
- [Claude Cowork installation](https://claude.com/docs/cowork/guide/plugins)
