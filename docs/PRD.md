# Studio Module Test Project: PRD

## One-liner
For classmates who play football predictions, who TBD: confirm how they struggle today (guess: they track scores and standings by hand), TBD: app name lets them run a live prediction league with automatic scoring, unlike TBD: their current way of tracking, to be confirmed.

## Problem
- Friends and classmates play fantasy or predictions, so the builder expects a need for a shared league.
- TBD: the actual struggle is unconfirmed. The guess is manual scoring and tracking.
- TBD: find out how friends track predictions and standings now.
- Pain is unproven. No friend has said they would use an app yet.

## Users
- Builder: the admin. Sets an admin PIN when the league is created. The only confirmed user.
- Classmates and friends: players. They join through an open link with a name and a short PIN, no login.
- TBD: find out whether any classmate besides the builder wants to join.

## Goals (v1)
1. Players join a league through a link using a name and a PIN.
2. The admin creates a league with an admin PIN and adds fixtures with kickoff times.
3. Players submit an exact-score prediction before kickoff.
4. The admin enters results, and points are awarded automatically: 3 for an exact score, 1 for the right outcome.
5. Standings show players ranked by points, with tied players sharing the same rank.

## Non-goals (v1)
- No sports data API. Results are entered manually by the admin.
- No login or accounts. Name plus PIN only.
- Players cannot enter results or add matches.
- No PIN reset.

## Success metric
TBD: decide one measurable line, for example how many classmates join and submit predictions in the first league. Settle this after the 3-classmate check.

## Constraints
- Cost must be $0, on free tiers only. Manual results avoid paid data.
- Works on phone and laptop, since the builder uses both equally.
- Reachability: players open the app from a shared link on either device, and the same name and PIN work on both.
- Privacy: no personal data beyond a display name and a PIN. PINs are never shown to other players.
- Reliability: no prediction can be submitted or changed after kickoff. Points and standings are the same every time from the same results.
- Built solo with Claude Code.
- TBD: choose the hosting and storage services and confirm v1 stays within their free-tier limits (Cost check, in docs/nfrs.md).
- TBD: decide which phone and laptop browsers to test on (Reachability check, in docs/nfrs.md).

## Open questions
- TBD: Is the pain real? Ask 3 classmates whether they would join a league (about 10 minutes).
- TBD: How do friends track predictions and standings now?
- TBD: What is the app name?
- TBD: How is the admin PIN stored, and what happens if the admin forgets it? No PIN reset in v1.
- TBD: Decide the PIN length and format (for example, 4 digits).
- TBD: How many players and leagues should v1 handle? No numbers are set yet.
