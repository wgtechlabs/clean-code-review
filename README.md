# Clean Code Review

A standalone Codex plugin containing the `clean-code-review` skill for concise, evidence-backed reviews of code changes and pull requests.

## Install

```bash
codex plugin marketplace add wgtechlabs/clean-code-review
codex plugin add clean-code-review@clean-code-review
```

Start a new chat after installation and invoke `$clean-code-review`.
Agents supporting the Agent Skills format can load `skills/clean-code-review/` directly.

## Scope

Review correctness, security, maintainability, unnecessary complexity, and relevant UI accessibility and interaction behavior. Findings include exact locations, concrete consequences, and validation limits.

The skill is self-contained and requires no other skills. Repository access and task-specific verification tools are still needed. Publishing reviews requires authorization; permission to comment alone does not authorize approval. Read-only requests are respected. Installing this skill does not authorize merging, deploying, or resolving other reviewers' threads.

## Attribution

Extracted from [Clean Workflow](https://github.com/wgtechlabs/clean-workflow), adapted from `focused-code-review`. The skill includes its source lineage and the Codelynx article that inspired the workflow.

## Contributing

Use short-lived feature branches from `dev`, squash merge feature PRs into `dev`, and promote `dev` to `main` with a regular merge commit. Follow [Clean Commit](https://github.com/wgtechlabs/clean-commit) message conventions.

## License

MIT. See [LICENSE](LICENSE).
