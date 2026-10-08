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

## Security issues

See [SECURITY.md](SECURITY.md). Don't open public issues for them.
