# oney-erge/.github

Shared files for every repository owned by [oney-erge](https://github.com/oney-erge).

- **Default community files.** GitHub shows [CONTRIBUTING.md](CONTRIBUTING.md),
  [SECURITY.md](SECURITY.md), [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) and the
  issue and pull request templates in `.github/` for any repository that does not
  have its own copy.
- **Dependabot auto-merge.** [`.github/workflows/dependabot-automerge.yml`](.github/workflows/dependabot-automerge.yml)
  is a reusable workflow. Each repository calls it from a small
  `.github/workflows/dependabot-automerge.yml` that lists its PR workflows. It
  squash-merges a Dependabot pull request once everything on its head has passed
  and the branch is up to date, and leaves major version updates for review. To
  re-check one pull request: `gh workflow run dependabot-automerge.yml -R oney-erge/<repo> -f pr=<number>`.

A change here applies to every repository at once.

## Repository baseline

`.github/workflows/repository-baseline.yml` is a reusable, opt-in contract
validation workflow. Callers must pass a reviewed full commit SHA of the
`oney-erge/engineering-kit` repository. It validates declarations and uploads
the result; it does not run repository-declared checks or prove product behavior.
The kit repository and a reviewed revision must be available before adding a
caller. Existing repositories do not invoke this workflow automatically.
