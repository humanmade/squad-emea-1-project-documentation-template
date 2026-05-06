# Developer documentation

**The technical detail engineers need to work on the project effectively.** Conventions, processes, and decisions for working on the codebase day to day.

## Onboarding

See [Onboarding](Onboarding.md) for the full engineer onboarding guide — prerequisites, local setup, first reading, and who to ask for what.

## Local environment

How to get the project running locally — prerequisites, install commands, first-run steps, required env vars, mock services, sample content, gotchas.

## Coding standards

Standards we hold code to:

- WordPress core coding standards.
- WordPress.com VIP guidelines.
- Project-specific additions.

What's enforced via linting and formatting, where the config lives, how to run it locally. Code review expectations — what reviewers look for, when to approve, when to block.

## Testing

What's tested at each layer (unit, integration, end-to-end) and what each layer covers. How to run tests locally. Coverage expectations and how they're measured. CI integration — what runs on PRs, what blocks merge, where to see results.

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
