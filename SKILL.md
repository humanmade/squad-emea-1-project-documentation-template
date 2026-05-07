---
name: hm-emea-squad-1-project-docs
description: Use this skill whenever the user wants to create, scaffold, or populate project documentation for a Human Made EMEA Squad 1 WordPress project. Trigger on phrases like "set up project docs", "create project documentation", "scaffold docs for [project]", "start the wiki", "write up the architecture overview", "add a feature catalogue entry for X", "create an ADR for", or any request to produce or fill in structured project documentation. Also trigger when the user says "document this feature", "write up our release process", or "help me set up the project wiki". If there's a documentation task and an HM EMEA Squad 1 project is involved, use this skill — it encodes the squad's preferred structure, tone, and HM defaults (native WordPress first, branching model, deployment conventions).
---

# HM Project Documentation

This skill creates project documentation for Human Made WordPress projects using an interactive intake process and the HM documentation template.

## Before you start

Read **`Documentation-Principles.md`** from this directory before doing anything else. It governs the style, tone, and quality of every document — concise, outcome-focused, direct, no filler, consistent terminology, and the anti-patterns to avoid.

The template files for each document type live alongside this SKILL.md. Read the relevant template immediately before drafting that document — not all upfront. Each template's structure and section descriptions tell you what that document needs to cover.

**Core principle:** Work interactively. Draft one document at a time, present it, get feedback, then move on. Never invent details — if you don't have the information for a section, leave the placeholder in place and flag it clearly.

---

## Phase 1: Project intake

Ask these two questions up front, every time:

- **Where will the documentation live?** — project repo (default), GitHub Wiki, Confluence, or somewhere else. This affects structure and formatting (see Output section).
- **Is there any existing documentation?** — if yes, ask the user to share it or point you at it, and read it before generating anything. Carry all existing content forward into the new structure; nothing should be lost. Warn the user upfront that page paths or URLs may change as content is reorganised.

Then infer the rest from the codebase: tech stack from `composer.json` and `package.json`, hosting from deployment configs, repo URL from git, issue tracker and project purpose from the README. If you can't see the codebase, ask for the repo URL so you can fetch this context.

Only ask the user for what you can't infer — typically client name and stakeholders, design links, success metrics or KPIs.

---

## Phase 2: Decide what to create

Start from what already exists. If existing documentation was provided in intake, work from it: map content to the new structure (see [Migrating existing documentation](#migrating-existing-documentation)) and consolidate where the same thing lives in multiple places. Only generate what's missing or specifically asked for.

**Project Overview is mandatory.** It's the home page of the documentation. If it doesn't exist, draft it first.

**ADRs are different.** Ask explicitly whether the project records decisions as ADRs, or infer from existing docs if an ADR folder is already there. If yes, ADRs get added going forward — one per decision as it's made. Don't try to retrospectively document old decisions; the team rarely has good answers and the result is archaeology, not documentation.

For everything else, ask the user which they want. Don't generate by default — sparse is better than padded.

Optional documents:

- Architecture Overview
- Developer Documentation (README)
- Onboarding
- Deployment
- Testing
- Feature Catalogue entry *(ask: which feature?)*
- Glossary
- Risk Log
- Definition of Done
- Definition of Ready

---

## Phase 3: Generate documents

For each document the user wants:

1. Read the relevant template file. Its structure and section descriptions show what the document needs to cover.
2. Identify which placeholders the intake didn't already answer. Ask only those follow-up questions — don't repeat the intake.
3. Draft the document, replacing placeholders with real content. Remove sections that don't apply; sparse or deleted sections are better than empty ones.
4. Present the draft. Ask for feedback before moving to the next document.

The templates encode HM defaults — branching model in `Deployment.md`, native-WordPress-first principles in `Architecture-Overview.md` and the Feature Catalogue, coding standards in `Developer-Documentation/README.md`, and so on. Apply those defaults when the project doesn't specify otherwise, and flag any deviation explicitly in the relevant document.

---

## Output

Generate documents as Markdown. Present one document at a time. If the user wants to save files, ask where the project docs live and write them there directly.

### Documentation entrypoint

`Project-Overview.md` is the entrypoint for a project's documentation — not the template's own `README.md`. When scaffolding into a project:

- Do not carry forward the template's `README.md`. It documents the template itself, not the project.
- If the docs sit somewhere GitHub auto-renders `README.md` (a `docs/` folder, repo root, or section folder), suggest renaming `Project-Overview.md` to `README.md` so it becomes the rendered landing page.
- Otherwise, link to `Project-Overview.md` from the project's existing `README.md` so newcomers can find it.

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
