# CONTRIBUTING.md template

Copy this file into each Inner Source repository's `CONTRIBUTING.md`. Replace bracketed placeholders.

---

```markdown
# Contributing to [Component Name]

This component follows the **Inner Source Charter of [Organisation Name]**
(see `[path/to/charter.md]`).

## What this component does

[One paragraph: what the component does, who consumes it, what it does
*not* cover.]

## Owner Team

- **Owner Team:** [team name]
- **Maintainer-in-Charge:** [name], substitute: [name]
- **Communication channel for pull requests:** [Slack channel / Forgejo issue]

## Before the pull request

- Open an issue if the change is larger than a bug fix.
- For architecture-relevant changes, hold an architecture conversation
  with the Owner Team beforehand.
- Check with the Owner Team whether someone is already working on a
  similar change.

## Pull request requirements

- Title follows Conventional Commits (`feat:`, `fix:`, `docs:`, …).
- Description contains: what is changing, why, how it was tested.
- Tests for new functionality are included.
- Documentation is updated in the same pull request.
- CI pipeline runs green (tests + security scans).

## Review expectations

- Initial sighting by the Owner Team: within **[X] working days**.
- Full review and merge decision: within **[Y] working days** after sighting.
- On deadline overrun: escalation per the organisation charter,
  *„Conflict Mechanism"*.

## Conflict mechanism

On disagreement between contributor and Owner Team, the escalation path
from the organisation charter applies. Before escalation, an architecture
conversation with the platform team is mandatory.

## License and usage

This component is Inner Source of `[Organisation Name]`. Usage outside
the organisation is not permitted. Reference to the organisation-wide
Inner Source licence: `[path/to/licence.md]`.

## References

- Organisation Inner Source charter: `[path]`
- Security advisories: `[security path]`
- Escalation body: `[contact]`
```
