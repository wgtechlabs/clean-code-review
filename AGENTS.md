# Repository instructions

## Scope and source of truth

This repository distributes the `clean-code-review` skill as the `clean-code-review` Codex plugin.
The canonical instructions are in `skills/clean-code-review/SKILL.md`. Keep the skill
self-contained: source-lineage links are attribution, not runtime dependencies.
Read the current skill and affected packaging files before changing behavior.
Preserve unrelated changes and keep edits limited to the requested outcome.

## Packaging and documentation

- Keep the plugin name `clean-code-review` in `.codex-plugin/plugin.json` and the marketplace entry in `.agents/plugins/marketplace.json`.
- Keep the skill folder and frontmatter name `clean-code-review` consistent. Repository and skill names need not be identical.
- The marketplace entry points to the repository root (`./`); the plugin discovers skills under `./skills/`.
- Update README examples when invocation, installation, or behavior changes.
- Preserve upstream source attribution and the MIT license. Do not add dependencies on locally installed skills or machine-specific paths.
- Skill installation or invocation does not grant permission to publish, merge, deploy, or perform other external actions. Preserve explicit authorization boundaries.

## Git and delivery

- Create short-lived feature or documentation branches from `dev`.
- Open feature PRs against `dev`; squash merge only when authorized.
- Promote `dev` to `main` through a PR using a regular merge commit, only when authorized.
- Do not push directly to `dev` or `main` for routine changes.
- Use Clean Commit messages: `<emoji> <type>: <description>` with lowercase, present-tense descriptions and no final period. Common pairs are `📖 docs`, `📦 new`, `🔧 update`, `⚙️ setup`, and `🧪 test`.
- Do not merge, tag, or publish a release merely because a change is complete.

## Validation

For documentation or skill changes, inspect the final diff and run `git diff --check`.
Check that relative Markdown links resolve and frontmatter names match skill folders.
For packaging changes, parse both JSON manifests and check that their declared paths exist.
Use available Skill Creator and Plugin Creator validators when installed; report when
those checks are unavailable instead of treating them as passed.

For installation changes, exercise the Codex marketplace and plugin install flow in an
isolated setup, or the user's setup when authorized. Verify the installed skill files
against the intended source. Distinguish format checks, installation verification, and
actual agent behavior tests in the handoff; one does not prove the others.
