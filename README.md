# Project documentation template

A starter structure for project documentation. Copy these files into your project's wiki, docs folder, or wherever your team's docs live; fill in the placeholders; adapt as needed.

## What's in the template

- **[Project Overview](Project-Overview.md)**
- **[Project Management](Project-Management/README.md)** — sprint reports and project status.
- **[Developer Documentation](Developer-Documentation/README.md)** — local setup, standards, branching, and build.
  - [Onboarding](Developer-Documentation/Onboarding.md)
  - [Deployment](Developer-Documentation/Deployment.md)
- **[Testing](Testing.md)**
- **[Feature Catalogue](Feature-Catalogue/README.md)**
- **[ADR](ADR/README.md)** — architecture decision records.
- **[Glossary](Glossary.md)**

See [Documentation Principles](Documentation-Principles.md) for how to write the docs.

## Using the Claude skill

This repo includes a `SKILL.md` that turns Claude into an interactive documentation assistant for HM projects. When the skill is active, Claude will:

- Run an intake to gather project context before generating anything
- Read the relevant template files automatically
- Follow the [Documentation Principles](Documentation-Principles.md) and tone guide throughout
- Draft one document at a time and ask for feedback before moving on

**To use it**, install the skill by pointing Cowork at this directory, or package it into a `.skill` file:

```bash
python -m scripts.package_skill /path/to/project-documentation-template
```

Once installed, trigger it with phrases like "set up project docs", "create an ADR for...", or "write a feature catalogue entry for...".

**To use it without installing**, tell Claude directly: "Read the SKILL.md in my project-documentation-template folder and follow its instructions."

## Conventions

Documentation lives as Markdown files in a git repository. This is the default format — do not migrate to a wiki or CMS without a clear reason.

Pages use capitalised, hyphen-separated filenames. Top-level pages live at the root. Sections with multiple child pages get a subfolder with a `README.md` as the entry point, which GitHub renders automatically when browsing to that folder.
