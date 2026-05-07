# Testing

**Summary.** How testing happens on the project — code-level tests, QA, browser and device coverage, performance, and accessibility.

## Types of tests

What each kind of test covers:

- **Unit tests** — what they cover, where they live.
- **Integration tests** — what they cover.
- **End-to-end tests** — what they cover.

## Running tests

Commands, prerequisites, links to test code.

## QA process

Manual testing approach, acceptance criteria, who signs off.

## Browser & device coverage

Supported browsers and devices, testing tools, known caveats.

## Performance

*[Define targets — e.g. Core Web Vitals thresholds, Lighthouse score ranges, or a statement that scores are directional only. Specify whether targets are per-environment or production-only.]*

Tools and how to run them: *[e.g. Lighthouse CLI, PageSpeed Insights, WebPageTest, browser DevTools]*

What triggers a performance review: *[e.g. any PR touching critical rendering path, or on a scheduled cadence]*

## Accessibility

*[Define the standard — e.g. WCAG 2.2 AA — and what is in scope per ticket vs. what requires a dedicated accessibility audit.]*

Tools and how to run them: *[e.g. Axe, Lighthouse accessibility audit, screen reader testing, keyboard-only walkthrough]*

Who reviews and signs off: *[e.g. engineer self-review, dedicated QA pass, third-party audit cadence]*

## CI integration

What runs on PRs, what blocks merge, where results live.
