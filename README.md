# Operation Forward: .github

Organization-wide files for [Operation Forward](https://github.com/Operation-Forward):

- [`profile/README.md`](profile/README.md): the organization's public profile page.
- [`SECURITY.md`](SECURITY.md), [`CONTRIBUTING.md`](CONTRIBUTING.md): the defaults every repository
  without its own copy shows.
- Shared CI, called by each repository's `ci.yml` and pinned to a commit of this repository:
  - [`gates.yml`](.github/workflows/gates.yml): actionlint + shellcheck, Semgrep and Trivy filesystem
    scan (the Vibe Sec Ops gates). Required check: `security / gates`.
  - [`railway-deploy.yml`](.github/workflows/railway-deploy.yml): deploys a service to Railway after
    a green `main` pipeline, then checks the public URL.

Changing a shared workflow: open a pull request, merge it, tag the merge commit `vX.Y.Z`, then
bump the pinned SHA in each calling repository.
