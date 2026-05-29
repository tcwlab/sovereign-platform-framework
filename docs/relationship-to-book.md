# Relationship to the Companion Book

This framework and the book *„Der souveräne Plattform-Bau"* (Band 4 of the *Architecture Line*) form a complementary pair. Each is independently usable; together they give the complete arc.

## Two sides of the same coin

| Aspect | The book | This framework |
|---|---|---|
| Purpose | Didactic | Operational |
| Audience | Engineer + Manager (Doppelspur) | Platform team in active build |
| Format | Linear prose, German | Templates + assessments, English-primary |
| Output | Understanding | Action |
| Update cadence | Stable on print, English translation follows | Living, version-controlled |
| Distribution | epubli (DACH self-publishing) | GitHub |

The book teaches the *why* of each maturity stage and each cross-cutting principle, with sources, vignettes, and discussion. The framework provides the *what* to actually do — assessments to locate yourself, templates to adopt.

## How they reference each other

- **The book references this framework** in Anhang A (Self-Assessment), Anhang D (Literatur), Anhang E (Inner-Source-Charta), and at each stage overview where operational tooling is helpful.
- **This framework references the book** as the canonical theoretical source for the five-stage model, the five sovereignty axes, the five cross-cutting principles, and the consultancy vignettes that explain *why* each template is shaped as it is.

## What lives where — division of labour

**Belongs in the book.** The maturity model itself (why five stages, why these names). The five sovereignty axes (where they come from in Band 2). The five cross-cutting principles (How-To-Hook, Lower the barrier, 80/20 + Inner Source, Plattform-als-Produkt, Conway). The consultancy vignettes (drei Plattformen parallel, Spotify-Cargo-Cult). The Hohpe / Skelton-Pais / Conway / Feynman source discussion. The German tone of voice.

**Belongs in this framework.** The actual stage-diagnostic markers (live document, evolves with practice). The actual templates (org-charter, contributing, architectural-manifesto) in copy-and-paste form. The axes-reference as operational distillation. English-language reach for international discovery. Versioned, contributor-amendable artefacts.

**Lives in both.** The Inner-Source-Charter template exists in the book as Anhang E (verbatim, for readers who never reach this framework) and in this framework as `templates/inner-source-charta/` (canonical, evolving, with examples). When the two drift, the framework version is canonical; the next print run of the book synchronises.

## Five cross-cutting principles — quick reference

The book identifies five cross-cutting principles that run across all five maturity stages. The framework's templates encode each at the operational level.

1. **How-To-Hook** — the book's voice; not directly encoded in this framework, but present in how the templates speak (action-first, decision-supporting).
2. **Lower the barrier** — encoded in the *„Friction"* section of each stage assessment.
3. **80/20 + Inner Source** — encoded in the Inner-Source-Charter template and its contributing boilerplate.
4. **Plattform-als-Produkt, nicht Projekt** — encoded structurally: this framework is itself a long-lived product with semantic versioning and a changelog, not a one-shot publication.
5. **Conway-gerechte Org** — encoded in the Architectural Manifesto's opening Conway citation and the Vertical Boundaries principle.

## Suggested reading order

**If you have the book and not the framework yet.** Read the book linearly. Encounter Anhang E (Inner-Source-Charter) and use it directly; you don't need this framework for that. Encounter Anhang A (Self-Assessment) and use the book's questions to locate yourself.

**If you have the framework and not the book yet.** Run the self-assessment in `assessment/` to locate yourself. Adopt the templates relevant for your stage. If you want the theoretical foundation — *why* Stage 4 has the friction it has, *why* the manifesto opens with Conway — read the book.

**If you have both.** The framework is your operational record, the book is your shared mental model. The book sits on the desk for orientation, the framework lives in the repository for daily use.

## Versioning and synchronisation

The book is frozen at print. The framework evolves. The framework's CHANGELOG.md documents changes; when the book reprints, the framework's current version is the baseline for any in-book reproduction.

## Cross-licence note

The book is published under the epubli standard licence. This framework is published under MIT (`LICENSE`). The two licences are intentionally different because the book is an authored, copyright-bound work while the framework is a tools artefact intended for organisational adaptation and contribution.
