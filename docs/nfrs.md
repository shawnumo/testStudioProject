# Studio Module Test Project: NFRs

These are the quality targets v1 must meet, and how we'll check each one.

| NFR | Requirement | How we'll check |
|---|---|---|
| Cost | Runs at $0 on free tiers. No paid services and no sports data API; the admin enters results by hand. | TBD: choose the hosting and storage services, then list each one's free-tier limits and confirm v1 stays under them. |
| Reachability | Players and the admin can use every v1 flow on both a phone and a laptop. Players join through an open link with no login, and the same name and PIN work on either device. | TBD: decide which phone browser(s) and laptop browser(s) to test on. Then run the join, predict, and standings flows on one phone and one laptop. |
| Privacy | No accounts and no personal data beyond a display name and a PIN. PINs are not shown to other players. | TBD: decide how the admin PIN and player PINs are stored. Once decided, check that no PIN appears in the pages, links, or responses a player can see. |
| Reliability | A prediction cannot be submitted or changed after the match's kickoff time. Points and standings come out the same every time from the same results: 3 for an exact score, 1 for the right outcome, and tied players share a rank. | Write tests for the kickoff cutoff, the scoring rule, and tied ranks. Use the given/when/then criteria from the stories once they are written. |

## Not decided yet

- TBD: Hosting and storage choice, and the free-tier limits that apply to it.
- TBD: Which devices and browsers count as "works" for reachability. Find out what classmates actually use.
- TBD: How the admin PIN is stored and how it can be recovered. PIN reset is not in v1, so decide what happens if the admin forgets it.
- TBD: How many players and leagues v1 should handle. Nothing has been confirmed, so no performance or storage numbers are set yet.
- TBD: Whether network conditions need a requirement (for example slow or unreliable mobile data). Find out how classmates connect.
- TBD: Whether anyone besides the builder will use it. Only the builder is confirmed as a user, so ask 3 classmates whether they'd join a league.
