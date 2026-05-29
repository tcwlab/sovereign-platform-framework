# Sovereign Platform Framework

> An open framework for building sovereign platforms — self-assessment and templates for platform teams in regulated, mid-market, and DACH-affine organisations.

**Status:** Skeleton (Version 0.1, May 2026). Companion to Band 4 of the *Architecture Line* — *„Der souveräne Plattform-Bau"* (German-language book).

## What this framework provides

A sovereign platform isn't built by a single decision but through a sequence of maturity stages on which org structure and architecture grow together. This framework provides the *operational* side of that journey. The *didactic* side lives in the companion book.

Concretely:

- **Self-assessment** — five stage diagnostics (Recognise, Pilot, Operationalise, Scale, Anchor) with concrete markers to locate yourself.
- **Templates** — organisation-wide constitutional documents that every platform-building organisation needs: an **Inner Source Charter** for code collaboration and an **Architectural Manifesto** for shared architecture decisions.

Both are tools, not recipes.

## How to use

1. **Self-assess** with the documents under `assessment/`.
2. **Adopt the templates** appropriate for your stage from `templates/`.
3. **Iterate** — both templates are versioned, living documents managed via pull requests in your own organisation.

## Canonical source and visibility

**Canonical:** `git.mon.k8b.co/tcwlab/sovereign-platform-framework` (Forgejo, EU-sovereign hosting). Currently internal; access by invitation.

**Public source:** `github.com/tcwlab/sovereign-platform-framework` (US-GitHub). This mirror is read-only — all changes flow exclusively from the canonical Forgejo path. Synchronisation runs every 8 hours plus on every commit.

**Contributing during this phase.** Contributions welcome as **GitHub issues** at [`github.com/tcwlab/sovereign-platform-framework/issues`](https://github.com/tcwlab/sovereign-platform-framework/issues). Issues are triaged on the internal Forgejo path and either incorporated or refused with reasoning. Substantial contributions may, by arrangement, lead to an invitation to the canonical Forgejo path.

**Why this two-step setup.** The choice of Forgejo-as-canonical is part of what this framework teaches — sovereignty starts at the choice of the development platform, not at the choice of the product. The initially internal mode is a deliberate migration sequence: stabilise content first, then open. A later revision of this README will document the move to a fully public Forgejo path.

## License

MIT-licensed ([`LICENSE`](LICENSE)).

## Sources

See [`README.de.md`](README.de.md) for the full list of inspirations.
