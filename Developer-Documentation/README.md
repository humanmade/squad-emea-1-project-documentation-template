# Developer documentation

**The technical detail engineers need to work on the project effectively.** Conventions, processes, and decisions for working on the codebase day to day.

## In this section

- [Developer documentation](README.md)
  - [Local environment](#local-environment)
  - [Coding standards](#coding-standards)
  - [Code review](#code-review)
  - [Testing](#testing)
  - [Branching & release](#branching--release)
  - [Build & deploy](#build--deploy)
  - [Dependency management](#dependency-management)
  - [Related](#related)
- [Architecture overview](Architecture-Overview.md)
- [Onboarding](Onboarding.md)
- [Deployment](Deployment.md)
- [Integrations](Integrations.md)

## Local environment

How to get the project running locally — prerequisites, install commands, first-run steps, required env vars, mock services, sample content, gotchas.

## Coding standards

Standards we hold code to:

- WordPress core coding standards.
- WordPress.com VIP guidelines.
- Project-specific additions.

What's enforced via linting and formatting, where the config lives, how to run it locally.

## Code review

Every PR into `main` requires a human code review before merging. All changes require review — there is no self-merge exception. See the [HM Engineering Handbook for full guidelines](https://engineering.hmn.md/how-we-work/process/reviews/).

- Automated checks must pass before requesting a human review.
- Reviewers focus on code quality — security, performance, architecture, and best practices. They are not doing QA.
- Test your own work on `develop` before requesting review. Share a `develop` link and testing instructions in the PR so the reviewer can check acceptance criteria if needed.
- After approval, the author merges, updates the Jira ticket with testing instructions if needed, and moves it to the Product Owner for review.

List any project-specific things reviewers should also check here — for example, asset versioning rules, architectural principles to enforce, or accessibility and performance gates.

## Testing

See [Testing](../Testing.md) for the full testing approach.

What kinds of automated tests the project has — unit, integration, end-to-end — and what each one covers. How to run them locally. Coverage targets and how they're measured. Which CI checks block a PR from merging, and where to find the results.

## Branching & release

How code moves from a branch to production. Branching model, feature branch naming, pull request review expectations, required approvals, merge strategy. QA process and sign-off. Release cadence — when releases go out, who runs them, what gets included.

## Build & deploy

The pipeline from commit to production — stages, tools, triggers, artefacts. What's deployed where, automatic vs manual promotion. Who can deploy to which environment. How to roll back, how long it takes, who has the authority.

## Dependency management

How Composer (PHP) and npm (JavaScript) dependencies are managed. Lock file policy. Update cadence — when and how dependencies are reviewed and updated. How we hear about vulnerabilities, how quickly we respond, who owns it.

## Related

- [Architecture overview](Architecture-Overview.md)
- [Onboarding](Onboarding.md)
- [Deployment](Deployment.md)
- [ADR](../ADR/README.md)
