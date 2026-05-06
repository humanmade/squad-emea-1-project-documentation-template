# Deployment

How code moves from a branch to production. Including our goals for this process, the different environments, branches, CI/CD, deployment and rollback plans.

## Goals

Our deployment process should aim to enable the following objectives.

- **Ship fast and often.** Small PRs, short-lived branches, minimal rebasing. Automate as much as possible.
- **Ensure clarity.** Versioned releases, tags, and clear changelogs — a clear paper trail that doesn't slow the team down.
- **High confidence.** Always-deployable branches with simple, automated checks.

## Environments

| Environment | Branch | URL | Deploy trigger |
|-------------|--------|-----|----------------|
| Development | `dev` | *[URL]* | Merge feature branch, or add label `Push to dev` on PR |
| Staging | `main` | *[URL]* | Add label `Push to staging` on PR |
| Production | `production` | *[URL]* | Merge PR from `main` into `production` |

## Branching model

- `main` — default branch. Feature branches are taken from here and merged back when complete. Always deployable.
- `production` — live site tracks this branch. Deploy by opening a PR from `main`. No code review required if checks pass — code is already reviewed.
- `dev` — development environment tracks this branch. Merge feature branches into `dev` for early testing. Reset to `main` periodically.
- `XXX-123-feature-name` — feature branches, prefixed with the ticket number.
- `hotfix-XXX` — urgent fixes branched from `production`, PR'd back to `production`.

## Release process

1. Complete the [pre-release testing checklist](../Testing.md) on staging.
2. Open a PR from `main` into `production` titled `Release X.X.X` using [semantic versioning](https://semver.org/):
   - **Major** — significant change, e.g. rebuild, redesign, replatform.
   - **Minor** — feature release, WordPress update, major plugin updates.
   - **Patch** — bug fixes, security patches.
3. Merge once all checks pass. Code review is not required at this stage.
4. Create a GitHub Release and tag targeting `production`, e.g. `1.0.0`. Auto-generate the changelog.
5. Share the version number and changelog with the client before deploying.
6. *[e.g. Deploy manually from altis dashboard]*
7. Complete the [post-release testing checklist](../Testing.md) on production to verify key functionality.

## Deployment pipeline

GitHub Actions handles automated deploys. *[Link to workflow config in the repo.]*

- Label `Push to dev` on a PR → deploys to the development environment.
- Label `Push to staging` on a PR → deploys to staging.
- Merge to `production` → *[e.g. must be manually deployed from Altis dashboard.]*

*[Note any additional stages — e.g. lint, test, build — and where to find logs and build status.]*

## Rollback

- **Immediate rollback**: *[e.g. revert the merge commit and redeploy, or use a hosting panel rollback.]*
- **Database changes**: *[note whether migrations are reversible and if so, how.]*
- **Who to notify**: *[e.g. EM, client contact.]*
- **Estimated rollback time**: *[rough figure.]*

## Related

- [Architecture overview](Architecture-Overview.md)
- [Developer documentation](README.md)
- [Testing](../Testing.md)
