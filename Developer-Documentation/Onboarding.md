# Onboarding

**Everything a new engineer needs to go from zero to productive on this project.** Work through this in order. Flag anything that's missing or out of date.

## Prerequisites

Tools and accounts to have in place before starting local setup.

- Node version: *[x.x — use nvm or Volta]*
- PHP version: *[x.x — use valet, DDEV, or local Docker setup]*
- Composer
- WP CLI
- *[Any other required tools — e.g. Docker, nvm, etc.]*

## Access to request

Request these before or on day one. Note who to ask for each.

| Access | Who to ask |
|--------|------------|
| GitHub repo | *[Person or process]* |
| Jira project | *[Person or process]* |
| Confluence space | *[Person or process]* |
| Staging environment | *[Person or process]* |
| *[Other tools — Figma, analytics, etc.]* | *[Person]* |

## Local environment setup

Follow the [local environment setup guide](README.md#local-environment) in Developer documentation.

## First reading

Read these before picking up a ticket:

- [Project overview](../Project-Overview.md) — who the client is, what the project is for, what success looks like.
- [Architecture overview](Architecture-Overview.md) — the tech stack, hosting, and system diagram.
- [Documentation principles](../Documentation-Principles.md) — how we write and maintain docs on this project.
- [Feature catalogue](../Feature-Catalogue/README.md) — browse the main features to build a mental model of the codebase.

## Coding standards

We follow:

- [WordPress core coding standards](https://developer.wordpress.org/coding-standards/)
- [WordPress.com VIP guidelines](https://docs.wpvip.com/technical-references/vip-coding-standards/)
- Project-specific additions documented in [Developer documentation](README.md)

Linting and formatting are enforced in CI. Run *[command]* locally before pushing.

## First week

- Pair on a small, well-defined ticket before working independently.
- Ask questions early — surface blockers in standups rather than working around them.
- If anything in this doc is wrong or missing, fix it.

## Who to ask

| Topic | Contact |
|-------|---------|
| Local environment issues | *[Person]* |
| Architecture and technical decisions | *[Person]* |
| Project delivery and ticket questions | *[Person]* |
| Client comms | *[Person]* |

## Related

- [Architecture overview](Architecture-Overview.md)
- [Developer documentation](README.md)
- [Testing](../Testing.md)
- [Deployment](Deployment.md)
