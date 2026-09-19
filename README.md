# Engineer Pay Log — Deadhead Finder Sandbox v3.0

## What changed
- Connected the sandbox to EPL's certified GO 202 Rev. 7 + Paper Rev. 8 passenger schedule dataset.
- 257 passenger assignments are selectable. Extra Crew-only assignments are intentionally excluded.
- 49 passenger relief crews are selectable and resolve to the covered job by day.
- Regular-owner relief days no longer hide the underlying assignment.
- Preserves the v2.8 GTFS routing, overnight service crossover, Jamaica/Woodside preference logic, priority deadhead locations, and Community Deadhead Notes.
- Job 166 keeps its certified final-working-train timing so the 2702 / 8702 practical-routing tests still work.
- Other jobs route home from printed release only until their final working-train movement timing is modeled.
- Known report-access rules included: normal station 1 minute; West Side Yard 20 minutes from Penn; Jamaica Storage Yard 20 minutes from Jamaica; Babylon Yard 35 minutes from Babylon Station.
- Ronkonkoma Yard and Hillside are deliberately marked "access rule needed" rather than guessed.
- Going-home routing remains paused for yard/employee terminals until release-side egress rules are modeled.

## Good first tests
1. Job 166 on a Monday — should show GCM 3:44 PM report / 12:37 AM release and preserve the 2702 behavior.
2. Job 166 on a Saturday or Sunday — should show 3:51 PM / 12:40 AM and preserve the verified 8702 practical recommendation.
3. Relief Crew 471 on Wednesday or Thursday — should resolve to Job 166 automatically.
4. Relief Crew 471 on Friday — should show no covered assignment.
5. Job 108 on a Monday — should use West Side Yard and the Penn 20-minute access rule; going-home yard egress should remain paused.
6. Job 43 on a weekday versus Saturday — weekday should route Port Jefferson; Saturday should show no published schedule.
7. Job 113 on a weekday — should use the Paper Rev. 8 Penn Station 5:01 PM report override.
8. Job 357 — should identify Ronkonkoma Yard but warn that the yard-access rule still needs certification.

This remains a sandbox. It does not modify Engineer Pay Log production.
