# Alpha.76 observer tests

Use version **0.3.0-alpha.78**, a fresh campaign for each run, and a playset containing only this mod. Record the EU5 version and checksum shown in the game. The automated checks passed; these runs test what requires the game engine. The existing balance result is accepted.

AI Japan now needs **15 Stability** to proclaim the Concord; a player still needs **25**. This addresses the observed alpha.76 stall at the stability requirement. Peace, Plutocracy, Nanboku-cho resolution and the inactive-Sengoku requirement still apply. To test this change, reload a pre-formation checkpoint from before the manual stability increase, or start fresh. A save where the Concord already formed cannot test the new threshold.

## Run A: ordinary AI Japan

Start as Japan or a country outside Japan, then enter observer mode. Do not start or temporarily play as a Japanese clan or House: doing so records the House-campaign rule. Let Japan meet the normal proclamation requirements and form the Concord without event commands, free money, or milestone cheats.

Follow formation and ratification, The Unquiet Peace, The Great Reckoning, the Hundred-Year Concord and its Articles, then the maritime stories. Record dates and any prolonged stall. If Japan cannot form, record the unmet requirements and preserve the save; do not force formation and call the ordinary progression test passed.

## Run B: a House-origin campaign under AI Japan

Start as a Japanese clan. Play through the first monthly pulse and save before entering observer mode. This gives the mod a chance to record the persistent House-campaign rule. Keep that starting save.

Follow the same milestones as Run A. AI Japan should choose the available House-oriented settlements and favor House autonomy in its law preferences. After the capstone, the script adds **one point per month toward House Privilege** until that side reaches its limit. Other movement can affect the net displayed change. Save and reload after the capstone and confirm that this direction persists.

To check the actual House-player experience, use a separate copy of a post-formation checkpoint, resume as the original House, and check its country identity, House actions, and law-vote controls. That short check matters: an observer game alone cannot establish that the player interface works. Return to the untouched observer save to continue the long run.

## Evidence to keep from both runs

- Preserve checkpoints immediately after formation, after each early crisis, after the capstone, and at the end. Include at least one save/reload during ordinary administration. Continue into the later maritime content; a short run that never reaches it leaves that content untested.
- Check the Concord Treasury, Japan's funds, national program authorizations, actual project construction and staffing, and both bureaucracies once unlocked. Note repeated insolvency or a stall despite meeting the visible requirements.
- Watch several elections. They should finish, preserve countries, and allow voter preferences to differ. Different voters can still legitimately support the same candidate.
- Check War Service alongside the other eight law families, especially sponsorship by Japan when a different House presides or by a human House on a checkpoint copy. Unavailable laws can still have normal unlock conditions.
- Confirm Houses stay out of the Middle Kingdom while Japan retains its intended diplomatic access. On a checkpoint copy, exercise an unrelated organization's law vote when possible; the automated vanilla comparison is not a runtime ballot test.
- Record successful and unsuccessful overseas investment attempts when visible. With at least 120 members, the dedicated overseas scheduler permits up to four attempts per quarter, spaced a week apart. AI Japan's dedicated project builder attempts at most one building per quarter. These caps do not include ordinary native AI construction; an attempt also need not produce a building.
- Check a colonial transfer if one happens: House building ownership should survive. Mark it **not exercised** if none occurs.
- Note crashes, freezes, repeated monthly pauses, duplicate events, missing text or icons, and logs that grow rapidly. Save before a reproducible problem where possible.

For timing, use the same game speed, camera position and machine settings for a fixed ten-year interval in each run. Record wall time and obvious month-boundary pauses, excluding loading and autosaves. Comparing these two modded runs cannot establish a slowdown relative to vanilla; that requires a separate matched vanilla measurement.

## Collapse coverage

If collapse occurs naturally, keep saves before it, partway through conversion, and after completion. AI Japan should convert up to 12 Houses immediately and up to 12 more per weekly follow-up. With 140 eligible Houses this means roughly 77 days after the initial batch, subject to game scheduling and eligible locations. Save/reload midway. The Concord should remain inert afterward, without resumed elections or administration, and the conversion should finish without a growing error flood or severe recurring pauses.

If neither campaign collapses, mark collapse **not exercised**. A targeted test on a disposable checkpoint copy can cover it without a third full campaign: use the Fracturing setup described in [DEBUG_EVENTS.md](DEBUG_EVENTS.md), then return Japan to AI control before the collapse resolves. Do not use the direct mass-landing debug event as proof that the AI's weekly queue works.

## Returning results

After exiting each run, preserve the game's `logs` folder before launching another session, since logs can be overwritten. Keep the relevant saves. The workspace utility `collect_kc_observer_evidence.py --run A` (or `--run B`) archives logs and the installed mod manifest; it does not copy saves or change the game.

For each run, report: start country, game version/checksum, final date, milestone dates, longest unexplained stall, crashes or recurring pauses, and which optional paths were not exercised. A clean observer run supports release, but unexercised collapse, transfers, human controls, or unrelated ballots remain explicit gaps until a checkpoint test covers them.

## Alpha.78 northern settlement checks

Use the western-only AI colonization rule. After formation, advance through a monthly pulse and check AI Japan has the basic colonial advances and Ezo charts. With an affordable, valid charter target, it should place an Ezo charter on a subsequent monthly AI evaluation. Check that gold is charged, migration progresses, and the charter remains active beyond the native nine-month abandonment evaluation. A completed Ezo charter should allow the next Ezo province to be selected.

Before the Hundred-Year Concord finishes, AI Japan must not start a new Manchurian charter, including with the all-countries rule. Reaching 100 Entrenchment alone does not qualify. After the Situation completes, northern charts and the Manchurian action become available. Ezo and Manchuria each allow one active charter, so unfinished Ezo settlement does not prevent the second stage. Save/reload with active charters and confirm no duplicate orders.

On a human-Japan checkpoint before the capstone, colonization remains available under its normal requirements. Acquire a northern holding after formation and check that the Northern Colonial Administration event appears before Phase 2. Verify the player can accept or defer, the AI accepts, and later holdings transfer without deleting House concessions. Check the shared native charter controls on a non-Japan country. These paths need engine validation; static tests do not establish AI scheduling or settlement speed.
