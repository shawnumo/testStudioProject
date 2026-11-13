# Studio Module Test Project · stories

## Must

- [ ] S1 · Join a league via link with name and PIN
  - As a player, I want to join a league through an open link using my name and a short PIN, so that I can take part without creating an account.
  - Given a league exists, when I open its link and enter a name and a PIN, then I am added to the league as a player.
  - Given I have already joined, when I open the link on another device and enter the same name and PIN, then I am recognised as the same player.
  - Given I enter a name that is taken with a different PIN, when I try to join, then I am not let in as that player.
  - TBD: Decide the PIN length and format (for example, 4 digits).

- [ ] S2 · Admin creates a league and adds fixtures
  - As the admin, I want to create a league with an admin PIN and add fixtures with kickoff times, so that players know which matches to predict.
  - Given I am creating a league, when I set an admin PIN, then that PIN is required for admin actions in that league.
  - Given I have entered the admin PIN, when I add a fixture with a kickoff time, then it appears in the league for players.
  - Given I am a player without the admin PIN, when I try to add or change a fixture, then the app does not allow it.
  - TBD: Decide how the admin PIN is stored, and what happens if the admin forgets it (no PIN reset in v1).

- [ ] S3 · Submit a prediction before kickoff
  - As a player, I want to submit an exact score prediction before kickoff, so that I can compete for points.
  - Given a fixture has not kicked off, when I submit a score prediction, then it is saved against my name.
  - Given I have already predicted a fixture that has not kicked off, when I submit a new score, then it replaces my earlier prediction.
  - Given a fixture has kicked off, when I try to submit or change a prediction, then the app rejects it.

- [ ] S4 · Admin enters a result
  - As the admin, I want to enter the final score of a match, so that predictions can be scored without a sports data service.
  - Given I have entered the admin PIN, when I enter a final score for a fixture, then the result is saved.
  - Given I am a player without the admin PIN, when I try to enter a result, then the app does not allow it.
  - Given a result has been entered, when I view the fixture, then the result is shown to all players.

- [ ] S5 · Automatic points
  - As a player, I want my predictions scored automatically once a result is entered, so that I don't have to count points by hand.
  - Given a result is entered, when my predicted score matches it exactly, then I get 3 points for that fixture.
  - Given a result is entered, when my predicted score is wrong but I picked the right outcome (home win, draw or away win), then I get 1 point.
  - Given a result is entered, when my prediction has the wrong outcome or I made no prediction, then I get 0 points.

- [ ] S6 · Standings with shared ranks on ties
  - As a player, I want to see league standings, so that I know how I rank against my classmates.
  - Given results have been scored, when I open the standings, then players are listed by total points, highest first.
  - Given two or more players have the same total points, when standings are shown, then they share the same rank.
  - Given the admin enters or changes a result, when I view the standings, then they reflect the new points.

## Should

- TBD: No Should stories decided yet. Decide after the first league has run.

## Could

- TBD: No Could stories decided yet.

## Not in v1

- No sports data API. The admin enters results by hand.
- No login or accounts. Players use a name and a PIN only.
- Players cannot enter results or add matches.
- No PIN reset.

## Open questions

- TBD: Is the pain real? Ask 3 classmates whether they would join a league (about 10 minutes). Only the builder is confirmed as a user.
- TBD: Find out how friends track predictions and scores now.
- TBD: Choose the app name.
- TBD: Decide how the admin PIN is stored and recovered.
- TBD: Decide how to check the Cost and Reachability NFRs (docs/nfrs.md is not written yet).
