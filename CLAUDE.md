# Studio Module Test Project

For classmates who play football predictions, who [track scores and standings by hand, to be confirmed], [app name] lets them run a live prediction league with automatic scoring, unlike [their current way, to be confirmed].

Read docs/PRD.md, docs/stories.md, docs/nfrs.md, docs/architecture.md and docs/adr/ before changing anything.

## Stack
- Client: a web app that works on phone and laptop, opened from a shared link. TBD: choose the framework, or plain HTML, CSS and JavaScript.
- Backend and storage: a free hosted backend with a database. TBD: choose the service.
- Auth: no accounts. Players use a name and a PIN. The admin uses an admin PIN set when the league is created.
- Scoring and ranking: 3 points for an exact score, 1 for the right outcome, 0 otherwise. Tied players share a rank. TBD: decide whether this is calculated when read or stored when a result is entered.
- Live updates: standings should reflect new results (story S6). TBD: decide whether the page refreshes on its own or the player reloads. He wants realtime skills, so this is worth deciding on purpose.
- Build tool: Claude Code.
- TBD: PIN length and format (S1), and how PINs are stored (S2).

### Hosting
- Target: $0, free tiers only.
- TBD: choose hosting and storage, then list each service's free-tier limits and confirm v1 stays under them (see docs/nfrs.md).
- TBD: how many players and leagues v1 should handle. Nothing is confirmed yet, so no limits are set.
- Manual results avoid paying for sports data.
- TBD: check that free tiers do not pause or delete an idle project, which could break a league mid-season.

## Commands
- Install: TBD (no package.json yet; S0 sets up the app)
- Dev: TBD
- Test: TBD
- Deploy: TBD (hosting not chosen yet, see ADR 0001)

## Setting up the app (S0)
- S0 · Walking skeleton sets the app up in this folder, never in a subfolder: `npm create vite@latest .` (or the create tool docs/architecture.md names, run on `.`). Keep docs/, CLAUDE.md and .claude/ as they are.
- S0 also deploys the empty app and gets CI green, so every later slice lands on a live URL.

## Studio protocol (every slice)
The Studio reads `docs/stories.md`, `docs/progress.md`, `.git/HEAD` and `.git/logs/HEAD` from this folder. Keep the formats exact.

1. Work on one slice from `docs/stories.md` at a time, in the order listed.
2. When it's built and tested, change its line to `- [~]` (built, check it on a phone). Only Shawn marks `- [x]`; The Studio does it when he presses Mark done.
3. Add an entry at the top of `docs/progress.md`, under the intro:
   ```
   ## YYYY-MM-DD · S# · Title
   - Built: what changed, in a sentence or two
   - Tests: what ran and the result, e.g. 31 passed
   - Check on your phone: what Shawn should try
   - Next: S# · title of the next slice
   ```
4. Commit the code and both docs together as `feat(S#): <title>`. The Studio reads commit hashes from git, so no Commit line is needed.
5. The Stop hook in `.claude/hooks/studio-check.cjs` won't let you end a turn while the last commit is `feat(S#)` and steps 2–4 aren't done for that slice.
6. End the session with a Studio update block. Shawn pastes it into The Studio when it can't reach this folder (on his phone, say):
   ```
   Studio update · testStudioProject
   - [~] S# · Title
   ## YYYY-MM-DD · S# · Title
   - Built: …
   - Tests: …
   - Check on your phone: …
   - Next: …
   ```

## Rules
- $0 only: no paid services, no API keys.
- Meet docs/nfrs.md; the Cost and Reachability NFRs come first.
- Every new screen needs its loading, empty and error states.
- Stop and flag anything that conflicts with the PRD or an ADR.
