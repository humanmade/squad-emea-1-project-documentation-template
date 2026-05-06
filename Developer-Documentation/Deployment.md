# Deployment

**How code moves from a branch to production.** Covers environments, the release process, and what to do when things go wrong.

## Environments

| Environment | URL | Purpose | Deploy trigger |
|-------------|-----|---------|----------------|
| Local | *localhost* | Development | Manual |
| Staging | *[URL]* | QA and client review | *[Trigger — e.g. merge to `staging`]* |
| Production | *[URL]* | Live site | *[Trigger — e.g. merge to `main` / manual]* |

*[Add any pre-production environments — e.g. a UAT or performance environment.]*

## Release process

Describe the steps from "code is merged" to "code is live". Include who is responsible at each stage.

1. Code merges to *[branch]* after review and CI passing.
2. *[Automated or manual deploy to staging — describe how.]*
3. QA sign-off on staging — *[who signs off and what that looks like]*.
4. *[Client or product sign-off if applicable.]*
5. Deploy to production — *[command or pipeline trigger]*.
6. Smoke test on production — *[what to check]*.

## Who can deploy

| Environment | Who |
|-------------|-----|
| Staging | *[e.g. Any engineer]* |
| Production | *[e.g. Tech lead or EM sign-off required]* |

## Deployment pipeline

Brief description of the CI/CD setup — tools, stages, artefacts. Link to the pipeline config if it lives in the repo.

- *[e.g. GitHub Actions / Buddy / WP Engine DevKit / VIP CLI]*
- *[Stages: lint → test → build → deploy]*
- *[Where to see build status and logs]*

## Rollback

What to do if a deployment causes a problem.

- **Immediate rollback**: *[how — e.g. revert commit and redeploy, use hosting panel rollback, or restore a snapshot]*
- **Database changes**: *[whether migrations are reversible, and if so, how]*
- **Who to notify**: *[e.g. EM, client contact, on-call]*
- **Estimated rollback time**: *[rough figure]*

Document any known situations where a rollback isn't straightforward.

## Release notes

*[Whether release notes are required, where they're published, and who writes them.]*

## Related

- [Architecture overview](Architecture-Overview.md)
- [Developer documentation](README.md)
- [Testing](../Testing.md)
