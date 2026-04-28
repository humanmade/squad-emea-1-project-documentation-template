# [Feature name]

**Summary.** Two or three sentences: what it does and why it exists.

## Who uses it

Editors, end users, admins, external systems.

## How it works

Brief walkthrough of the behaviour — editor workflow for content features, front-end behaviour for public-facing ones. Screenshots only where they earn their place.

## Implementation

How it's built, in this order:

- **Native WordPress** — CPTs, taxonomies, core blocks, patterns, templates, theme.json, block bindings, block styles.
- **Custom theme code** — template parts, block variations, hooks. Link to source.
- **Custom blocks or plugins** — only where native wasn't sufficient. Note *why*.
- **Third-party plugins or services** — what they do for this feature, version pins where relevant.
- **Key files** — links to the relevant code.

## Dependencies

Plugins, external services, other internal features.

## Configuration

Where settings live (admin, theme.json, env vars, constants, feature flags) and any per-environment differences.

## Data

Post types, meta, options, external sources. Privacy notes if relevant.

## Editorial guidance *(if applicable)*

What editors need to know to use this day to day.

## Known limitations & gotchas

Edge cases, performance, accessibility, browser quirks. Be honest — this section saves time later.

## Related

Other features, ADRs, tickets.
