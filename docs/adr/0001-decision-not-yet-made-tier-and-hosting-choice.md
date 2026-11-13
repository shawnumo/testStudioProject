# 0001: Decision not yet made (tier and hosting choice)

Status: Proposed · 2026-11-13

## Context

- The Design coach conversation has not happened yet, so no decision has been recorded. TBD: hold the Design conversation and record the first decision. This ADR is a placeholder for the first item in docs/architecture.md under "Decisions to record": the tier and hosting choice.
- Studio Module Test Project is a live prediction league. Players join through a link with a name and a PIN, submit exact-score predictions before kickoff, and see standings. The admin creates the league, adds fixtures and enters results by hand (stories S1 to S6).
- Constraints from the approved documents:
  - Cost must be $0, on free tiers only.
  - It must work on phone and laptop, and the same name and PIN must work on both.
  - It is built solo with Claude Code.
  - No sports data API, no accounts and no background jobs in v1.
- Players on different devices must see the same league, predictions and standings. The kickoff cutoff and admin PIN checks must be enforced on the backend, not only in the page.
- The architecture document has a working suggestion only: a free hosted backend with a database. It is not confirmed.
- Pain is unproven. Only the builder is confirmed as a user.

## Decision

- TBD: confirm the tier. Working suggestion from docs/architecture.md, not yet decided: a free hosted backend (the second tier).
- TBD: choose the hosting and storage service.
- TBD: list the free-tier limits of the chosen service and confirm v1 stays under them (Cost check, docs/nfrs.md).
- TBD: check that the free tier does not pause or delete an idle project.
- TBD: decide how many players and leagues v1 should handle. No numbers are set.

## Alternatives considered

Only the first two come from the architecture notes. The notes say these are "heavier than this needs" or ruled out. Nothing here has been decided with the builder.

- A static page or PWA alone: not enough as suggested in docs/architecture.md. Players on different devices must share one league, and the kickoff cutoff and PIN checks cannot be trusted if they run only in the browser.
- Serverless functions or a server of his own: suggested as heavier than v1 needs. v1 has no sports data API, no accounts and no background jobs, and the $0 constraint rules out a server he must pay for.
- TBD: name the specific services he compares and why each is or is not chosen.

## Consequences

- If the free hosted backend is confirmed:
  - All players see the same data, and the kickoff cutoff and PIN checks can run on the backend.
  - Free-tier limits or changes could affect the project. TBD: find out what they are once a service is chosen.
- This decision links to the other open ADRs: database and storage, PIN storage and admin PIN recovery, how standings update, manual result entry, and where the kickoff cutoff is enforced.
- TBD: rename this file and title once the decision is made (for example, "0001-tier-and-hosting-choice.md").
