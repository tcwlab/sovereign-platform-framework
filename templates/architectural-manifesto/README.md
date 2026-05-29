# Architectural Manifesto Template

This directory holds the template for an **organisation-wide Architectural Manifesto** — the document that codifies an organisation's foundational architecture choices.

## What this template is for

An Architectural Manifesto answers, in writing, three questions every platform-using organisation eventually faces:

1. **What quality goals** does our platform serve?
2. **What architectural principles** do all platform-using systems follow?
3. **What concrete practices** implement those principles?

Without a written manifesto, these questions get answered implicitly by each team — usually differently. The manifesto turns implicit architecture decisions into explicit, reviewable, versioned commitments.

## When to use

A manifesto becomes essential at the transition from Stage 3 (Operationalise) to Stage 4 (Scale). On Stage 3, the platform team and the first one or two consuming teams can hold architectural alignment in their heads. From the third consuming team onward, undocumented architecture choices erode visibly. The manifesto is the formal commitment that prevents the erosion.

## Structure

The template follows a four-section pattern that has proven productive in practice:

1. **Quality Goals** — the *„why"* (what properties the platform must exhibit)
2. **Principles** — the *„how"* at the foundational level (typically two or three foundational architectural choices)
3. **Practices** — the operational consequences of the principles (typically eight to twelve concrete practices)
4. **External standards** — references to widely adopted external standards (Twelve-Factor App, REST, Conway's law, etc.) that the manifesto adopts rather than reinvents

Each principle and practice is structured as **Statement / Rationale / Implication** — a pattern that has its roots in architecture decision records (ADRs) and pattern languages (Hohpe & Woolf, *Enterprise Integration Patterns*).

## Files in this directory

- [`manifesto-template.md`](manifesto-template.md) — the genericised template. Replace bracketed placeholders.
- [`examples/`](examples/) — example filled instances. Initially empty; community contributions welcome via pull request.

## Source

The structural pattern of this template comes from a real Architectural Manifesto used productively in a DACH platform-engineering engagement (anonymised). The Self-Contained Systems (SCS) commitment, the Decentralization principle, and the practice catalogue (Hide implementation details, Encapsulate Data Storage, Standardize Service communication, Follow REST Principles, Be Scalable, Isolate failure, Embrace a Culture of Automation, Deploy independently, Be highly observable) come from that source.

## Related references

- Self-Contained Systems — scs-architecture.org (Tilkov et al.)
- The Twelve-Factor App — 12factor.net
- Hohpe, Gregor & Woolf, Bobby. *Enterprise Integration Patterns* (Addison-Wesley, 2003) — the Statement/Rationale/Implication pattern has affinity with EIP's pattern structure.
- Conway, Melvyn. *How Do Committees Invent?* Datamation, April 1968 — the manifesto opens with Conway because architecture mirrors organisation; the manifesto is the org-level commitment that makes the mirror intentional.
- Companion book Band 4: Cross-ref to be added.
