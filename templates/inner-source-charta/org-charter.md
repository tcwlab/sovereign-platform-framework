# Inner Source Charter — [Organisation Name]

> **Version:** [Version] · **Effective from:** [Date] · **Review cadence:** annual, by [Body]

## Preamble

This charter establishes how software components within the organisation `[Organisation Name]` are published, maintained, and evolved under the Inner Source model. It applies to all components published by the platform team or by any product team under Inner Source designation.

## Scope

Inner Source covers all software components published in the platform-operated source repositories under the marker `inner-source`.

**Not covered by this charter:** production workloads not intended as reusable components; external open source components used unchanged; components under special confidentiality status (see *„Exceptions"*).

## Five binding principles

1. **Ownership is explicit.** Every Inner Source component has a clearly named Owner Team. Inner Source does not change ownership; it opens a controlled contribution path.
2. **Pull requests are the contribution path.** Direct push to `main` is forbidden — including for the Owner Team. Every change goes through review.
3. **Review SLAs are binding.** The Owner Team responds within `[X]` working days with an initial sighting (acceptance, change request, justified refusal). A full merge decision follows within `[Y]` working days.
4. **Standards are visible.** Tests, documentation status, security requirements live in the repository, not in a separate documentation universe.
5. **Conflicts escalate cleanly.** When Owner and contributor cannot agree, a documented escalation path exists.

## Roles and responsibilities

- **Owner Team** — responsible for the component, merges pull requests, keeps documentation current, defines the roadmap. On team dissolution, a documented handover process applies (see *„Lifecycle"*).
- **Maintainer-in-Charge** — a named person from the Owner Team who serves as the contact point for incoming pull requests. Substitution is regulated.
- **Contributors** — anyone in the organisation who opens pull requests against the component. They follow the component's `CONTRIBUTING.md`.
- **Platform Team** — provides the Inner Source infrastructure (repository hosting, CI/CD, security scanning) and operates the escalation body for unresolvable conflicts.

## Contribution model

Incoming pull requests follow the component's `CONTRIBUTING.md`. The charter establishes the minimum requirements:

- Each pull request has a meaningful title and a description of the change with justification.
- Tests for new functionality are included.
- Documentation changes are included in the same pull request.
- Security scans (`[Tool Name]`) run automatically in CI.

## Review SLA

| Level | Action | Deadline |
|---|---|---|
| 1 | Initial sighting by Owner Team | `[X]` working days |
| 2 | Full review and merge decision | `[Y]` working days after sighting |
| 3 | Escalation on deadline overrun | after `[Z]` working days without response |

Recommended starting orders of magnitude for an organisation entering Stage 4: initial sighting 2 working days, full review 5 working days, escalation after 10 working days. Components may tighten or relax these in their `CONTRIBUTING.md`.

## Conflict mechanism

When Owner Team and contributor cannot agree — typical cases: the contributor sees the feature as necessary, the Owner Team sees it as scope creep — this escalation path runs:

1. **Written explanation** from both sides in the pull request (not just in chat).
2. **Architecture conversation** between Owner Team and contributor team, moderated by the platform team, within `[N]` working days.
3. **Escalation body** decides if step 2 doesn't yield agreement. Possible outcomes: pull request is merged; pull request is rejected with reasoning; pull request is moved to a separate Inner Source fork (the *„Shared Solution"* path).

## Quality standards

Pull requests are merged only when:

- Tests pass (unit, integration where defined)
- Security scans yield no critical findings
- Documentation is updated in the same pull request
- At least `[N]` review votes from the Owner Team are present

## Component lifecycle

Three statuses are defined:

- **Active** — Owner Team exists, responds to pull requests, keeps the component operational.
- **In transition** — Owner Team is changing; a handover process is running. Pull requests are coordinated by the platform team.
- **Archived** — no Owner Team, no maintenance. Component is read-only; use is at own risk. Archival decisions are made by the escalation body.

## Metrics

The organisation publishes quarterly:

- Number of active Inner Source components
- Incoming pull requests, acceptance rate, median review time
- Escalation cases and their outcomes
- Adoption: how many Stream-aligned teams consume at least one Inner Source component

Published in the platform product reporting.

## Governance and escalation

Escalation body: `[Designation]`. Composition: one representative each from platform team, engineering leadership, architecture function. Meeting cadence: monthly, plus ad-hoc on incoming escalations.

## Exceptions

Components under special confidentiality status are not published under the Inner Source model. This classification is made by `[Body]` on application from the Owner Team. It is justified and time-bounded.

## Entry into force and maintenance

This charter applies from `[Date]`. Annual review by `[Body]`. Changes happen via pull request against the charter repository and are subject to the same review rules as any Inner Source component — the charter practices what it preaches.
