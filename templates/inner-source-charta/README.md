# Inner Source Charter Template

This directory holds the **organisation-wide Inner Source Charter** template and the **per-component CONTRIBUTING.md** boilerplate.

## When to use

When your platform reaches Stage 3 (Operationalise) or Stage 4 (Scale), informal contribution conventions stop scaling. An Inner Source Charter is the explicit, organisation-wide agreement that turns informal collaboration into operational discipline.

The charter answers four questions every Inner Source initiative eventually faces:

1. Who owns what?
2. How fast must reviews happen?
3. What happens when contributors and owners disagree?
4. How does a component join — and leave — Inner Source?

## Structure

- [`org-charter.md`](org-charter.md) — organisation-wide template. Adopt once, review yearly.
- [`contributing-template.md`](contributing-template.md) — per-component boilerplate. Copy into each Inner Source repository's `CONTRIBUTING.md`.

## Usage notes

**Who writes the charter.** The platform team drafts the organisation-wide version in consultation with two to three Stream-aligned teams who are early Inner Source contributors. A top-down rollout without contributor participation produces a charter no one reads.

**How the charter is maintained.** The charter lives by Inner Source rules: changes go through pull requests against the charter repository. The charter practices what it preaches.

**What does not belong in the charter.** Specific technical choices (test frameworks, CI tooling, repository hosting) are not in the charter; they live in the platform documentation. The charter describes *how* people collaborate, not *what tools* they use.

## Sources

- InnerSource Commons — innersourcecommons.org
- InnerSource Patterns Library — github.com/InnerSourceCommons/InnerSourcePatterns
- Hohpe, *Platform Strategy* Ch. 25 *„Ownership and Tenancy"*
- Hohpe, *The Software Architect Elevator* Ch. 32 *„Governance Through Inception"*
- Skelton & Pais 2019, Ch. 7 — *„X-as-a-Service"* as the default consumption mode
- Companion book Band 4: Anhang E

Companion book Band 4 reproduces this charter as Anhang E for readers who don't reach this framework.

**Note on contributing to this framework.** During the bootstrap phase, contributions to this charter template itself are processed via GitHub issues on the public mirror (see the project's main README for current visibility status).
