# Contributing to Langtrain

Thanks for helping. This guide applies to every repository in
[langtrain-ai](https://github.com/langtrain-ai) unless the repository has its
own CONTRIBUTING.md.

## Workflow

1. **Branch from `main`.** Name it for the change: `fix/…`, `feat/…`,
   `docs/…`, `chore/…`, `ci/…`.
2. **Keep PRs small and focused.** One change per PR is easier to review and
   to revert.
3. **Write commit messages that say why.** We use
   [Conventional Commits](https://www.conventionalcommits.org/):
   `fix(auth): reject expired API keys`.
4. **Open a PR.** Fill in the template. CI must pass, and the code owners are
   requested for review automatically.
5. **Squash-merge.** `main` stays one commit per PR.

`main` is protected on public repositories: changes land through a pull
request with passing checks.

## Before you push

Run the same checks CI runs. Each repository's README lists them; typically:

| Stack | Checks |
|---|---|
| Python | `ruff check .` and `pytest` |
| TypeScript | `pnpm exec tsc --noEmit`, `pnpm lint`, `pnpm test` |

## Tests

Behaviour changes need a test. Bug fixes need a test that failed before
the fix.

## Secrets

Never commit keys, tokens, `.env` files or customer data. CI scans for them.
If you commit one by accident, tell a maintainer: rotating the secret
matters more than rewriting history.

## Repository standard

Every repository in the organization has the same baseline, so any of them can
be picked up without asking how it works:

| File | Purpose |
|---|---|
| `README.md` | What it is, how to set it up, how to run its checks |
| `LICENSE` | Public repositories only; matches the license in the package metadata |
| `.github/CODEOWNERS` | Who reviews changes |
| `.github/workflows/ci.yml` | The checks a PR has to pass (code repositories) |
| `.github/dependabot.yml` | Monthly, grouped dependency updates |
| `.editorconfig` | Shared editor settings: UTF-8, LF, 2 spaces (4 for Python and Rust) |
| `.gitignore` | Keeps environments, build output, logs and `.env` files out |

These come from this `.github` repository and apply to every repository that
doesn't have its own copy, so don't copy them in: the PR template, the issue
forms, this guide, [SECURITY.md](SECURITY.md) and
[CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md). Change them here and every
repository picks up the change.

Repository names are `langtrain_<name>`. Retired repositories are archived on
GitHub, with a README that points at their replacement.

## Security issues

See [SECURITY.md](SECURITY.md). Don't open public issues for them.

## Conduct

See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).
