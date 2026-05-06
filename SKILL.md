---
name: hm-project-docs
description: Use this skill whenever the user wants to create, scaffold, or populate project documentation for a Human Made WordPress project. Trigger on phrases like "set up project docs", "create project documentation", "scaffold docs for [project]", "start the wiki", "write up the architecture overview", "add a feature catalogue entry for X", "create an ADR for", or any request to produce or fill in structured project documentation. Also trigger when the user says "document this feature", "write up our release process", or "help me set up the project wiki". If there's a documentation task and an HM project is involved, use this skill.
---

# HM Project Documentation

This skill creates project documentation for Human Made WordPress projects using an interactive intake process and the HM documentation template.

## Before you start

Read these two files from this directory before doing anything else — they govern the style, tone, and quality of every document you produce:

- **`Documentation-Principles.md`** — what good documentation looks like, and how to write it: concise, outcome-focused, direct, no filler, consistent terminology. Includes tone guidance and anti-patterns to avoid.

The template files for each document type also live alongside this SKILL.md. Read the relevant template immediately before drafting that document — not all upfront.

**Core principle:** Work interactively. Draft one document at a time, present it, get feedback, then move on. Never invent details — if you don't have the information for a section, leave the placeholder in place and flag it clearly.

---

## Phase 1: Project intake

Before generating anything, gather the core project context. Ask these as a single grouped message — not one question at a time:

- **Client name** and industry
- **Project purpose** — what the site does and who it serves
- **Hosting platform** — e.g. WordPress VIP, Altis, WP Engine, Kinsta
- **WordPress and PHP versions** (if known)
- **Repo URL** (if available)
- **Issue tracker** — Jira project key, Linear workspace, GitHub project, etc.
- **Figma or design system link** (if available)
- **Where will the documentation live?** — project repo (default), GitHub Wiki, Confluence, or somewhere else. This affects structure and formatting (see Output section).
- **Is there any existing documentation?** — if so, ask the user to share it or point you at it. Read it before generating anything. The goal is to carry all existing content forward into the new structure — nothing should be lost. Warn the user upfront that page paths or URLs may change as content is reorganised.

If the user can share a project brief, existing spec, or prior documentation, ask for it — it will answer most of these questions faster than the intake.

---

## Phase 2: Decide what to create

After intake, ask which documents to create. Default recommendation: start with **Project Overview** and **Architecture Overview** — they establish the facts that inform everything else.

Present the full list so the user can pick:

- Project Overview
- Architecture Overview
- Developer Documentation (README)
- Onboarding
- Deployment
- Testing
- Feature Catalogue entry *(ask: which feature?)*
- ADR *(ask: which decision?)*
- Glossary
- Risk Log
- Definition of Done
- Definition of Ready

---

## Phase 3: Generate documents

For each document the user wants:

1. Read the relevant template file from this directory.
2. Ask any document-specific questions needed (see below) before drafting.
4. Replace all placeholders with real content. Remove sections that don't apply — sparse or deleted sections are better than empty ones.
5. Present the draft. Ask for feedback before moving to the next document.

### Document-specific questions

**Project Overview**
- Who are the HM and client points of contact?
- What does success look like — business outcomes, KPIs?
- Any brand, editorial, or accessibility values that shape the work?
- Known constraints: budget, timeline, technology, legacy systems?

**Architecture Overview**
- Full tech stack: WordPress version, PHP, key plugins, build tooling?
- Third-party services or integrations (search, CRM, analytics, payments, media)?
- Hosting and CDN setup, environments?
- Any architectural decisions that deviate from HM defaults (see below)?

**Feature Catalogue entry**
- Feature name and one-line summary.
- Who uses it: editors, end users, admins, external systems?
- How is it built? Work through in HM priority order:
  1. Native WordPress: CPTs, taxonomies, blocks, patterns, templates, theme.json, block bindings, block styles
  2. Custom theme code: template parts, block variations, hooks
  3. Custom blocks or plugins: only if native wasn't sufficient — document *why*
  4. Third-party plugins or services
- Known limitations, gotchas, or accessibility considerations?

**ADR**
- What decision is being recorded?
- What was the context — what requirement or problem prompted it?
- What alternatives were considered, and why ruled out?
- What are the consequences or trade-offs going forward?

**Deployment**
- Does this project follow the standard HM branch model (main / production / dev)?
- Any non-standard environments or deploy steps?
- Standard GitHub Actions label-based deploys, or a different CI/CD setup?
- Who approves production deploys?

---

## HM defaults

Apply these unless the project specifies otherwise. Mention deviations explicitly in the relevant document.

**WordPress approach**
- Native WordPress first: CPTs, taxonomies, core blocks, patterns, templates, theme.json, block bindings, block styles before any custom code
- Block editor first: custom blocks only when native WordPress functionality won't do it — always document why in the Feature Catalogue

**Coding standards**
- WordPress core coding standards
- WordPress.com VIP guidelines
- Composer for PHP dependencies, npm for JavaScript; lock files committed

**Branching model**
- `main` — default; always deployable; feature branches cut from here
- `production` — live site; deploy by PR from main; no re-review needed if checks pass
- `dev` — integration environment; reset to main periodically
- Feature branches prefixed with ticket number: `XXX-123-feature-name`
- Hotfixes branched from `production`: `hotfix-XXX`

**Deployments**
- GitHub Actions triggered by PR labels: `Push to staging`, `Push to dev`
- Merge to `production` triggers production deploy (or manual step if hosting requires it)

**Releases**
- Semantic versioning: MAJOR.MINOR.PATCH
- PR from main into production titled `Release X.X.X`
- GitHub Release with auto-generated changelog after merge
- Share version and changelog with client before deploying

---

## Output

Generate documents as Markdown. Present one document at a time. If the user wants to save files, ask where the project docs live and write them there directly.

### Platform-specific adjustments

**Project repo (default)**
Nested folders with `README.md` as the index for each section. Capitalised, hyphen-separated filenames (e.g. `Feature-Catalogue/Article-Paywall.md`). Standard template structure applies as-is.

**GitHub Wiki**
GitHub Wikis do not support nested folders — all pages live at the same level. Flatten the hierarchy into page names: e.g. instead of `Developer-Documentation/Onboarding.md`, use a page named `Developer-Documentation-Onboarding`. Use the wiki Home page as the top-level index rather than a README. Adjust internal links to use wiki page titles rather than file paths.

**Confluence**
Confluence supports nested pages natively, so the template hierarchy maps cleanly to parent/child pages. Formatting is Markdown-compatible in most modern Confluence setups — confirm with the user if their instance uses the Confluence wiki editor instead. Internal links reference page titles rather than file paths.

**Other platforms**
Ask the user whether the platform supports nested pages or a flat structure before generating, as this determines whether to use the default folder hierarchy or a flattened naming approach.

### Migrating existing documentation
When existing documentation has been provided, read it thoroughly before drafting. Map each piece of content to the most appropriate section in the new structure. If content doesn't fit neatly, find the closest home and note it for the user's review. Flag any content that couldn't be mapped clearly rather than discarding it. Remind the user that internal links or bookmarks pointing to old page paths will need updating.
