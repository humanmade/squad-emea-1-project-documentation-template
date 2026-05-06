# Documentation principles


1. **Short and succinct.** Too much documentation is also a problem; if a section has nothing to say, delete it. Each fact lives in one place — link to it from elsewhere. Avoid duplication. It creates conflicting sources of truth.
2. **Link to the source.** Some information already lives elsewhere, such as code, shared playbooks, or company processes. Avoid restating it in detail, where it can drift or conflict. Link to the source and focus on intent, constraints, and context.
3. **Write for the whole team.** Engineers, delivery, product, stakeholders, new starters — all should be able to follow. Serious and professional in tone, plainly written. Avoid (or spell out when necessary) business jargon and unfamiliar acronyms on first use.
4. **Outcome focused.** Lead with the outcome, deliverable, or decision. Describe what it does and what it enables before explaining how it is implemented or managed.
5. **Make decisions visible.** Document the choices that shape the system, even when they rely on existing tools or plugins. Do not assume these are self-evident. Explain what was chosen and why.
6. **Living, not finished.** Out-of-date docs are worse than missing docs. Prune aggressively.

## Tone and voice

1. **Clear and direct.** Write in plain English. Avoid unnecessary words, filler, and emphasis. Get to the point.
2. **Explain where needed.** Assume the reader is capable but may lack context. Provide framing when something is non-obvious. Do not over-explain basics.
3. **Structure for clarity.** Lead with what most readers need to act, then layer in detail. Keep the main flow focused. Use links or separate sections for deeper explanation and edge cases.
4. **Measured tone.** Keep a professional tone without sounding formal or distant. Avoid chatty or overly conversational language. Use “we” sparingly.
5. **Be precise.** Use consistent terminology. Follow the glossary. If a term does not exist, add it rather than inventing alternatives.
6. **Acknowledge trade-offs.** State constraints and limitations where they matter. Do not present decisions as universally correct.

## Anti-patterns

- Do not use filler or emphasis words (“simply”, “just”, “obviously”, “clearly”)
- Do not narrate actions the reader can infer from code or headings
- Do not repeat information already defined elsewhere
- Do not introduce new terminology for existing concepts — use the glossary
