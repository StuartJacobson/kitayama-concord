# AI Japan and House campaigns — alpha.75

From alpha.77, AI-controlled Japan needs 15 Stability to proclaim the Concord; human-controlled Japan still needs 25. All other formation requirements remain in force.

AI Japan can prepare for the existing Concord proclamation, use treasury and
crisis-completion actions, authorize national projects, budget the two Concord
bureaucracies, and order a limited amount of physical project infrastructure.
Normal prices, eligibility, staffing and construction time still apply. Ordinary
program spending and the single-building construction attempt are each limited
to once per quarter; emergency programs retain their existing cooldowns.

For this release, a human Japanese clan, daimyo or Chartered House activates a
persistent House-campaign rule. AI Japan takes the House-oriented constitutional
choices when available, and AI law preferences favor House autonomy. After the
capstone, Japan moves one point per month toward House Privilege. That movement
continues if a House-origin player later controls Japan. Human event choices
and ballots stay under player control. A normal human-Japan start is unaffected.

The origin is recorded at game start and while playing a House in an existing
save. In multiplayer, any qualifying House player activates the shared rule.
If an older save already changed the player from a clan to Japan before this
version could record it, the console command `event kc_ai_japan.2` records the
flag once. It is unnecessary for new games or saves still played as a House.

These are temporary release rules. They do not add an active House political
campaign. AI support is implemented, but long-campaign and save/reload testing
are still required before the v1 release. Collapse stops normal administration;
AI collapse retains the weekly House-conversion batches introduced in alpha.74.

## Northern settlement from alpha.78

On its first monthly pulse as an active Concord, AI Japan receives Mapmaking and Colonies if missing, plus charts of Ezo. It evaluates a dedicated Ezo charter action monthly. After completing the Hundred-Year Concord Situation, it receives northern charts and starts evaluating a separate Manchurian action. These actions bypass the western-only AI colonization restriction without changing the game rule for other countries.

Each region permits one active AI charter at a time. Charters use the native price, range/eligibility checks, migration and completion mechanics. Existing northern charters count toward the limits and the AI keeps them until completion. No land or settlers are created by the AI preparation. Other regions retain the ordinary AI rules. New orders and preparation stop after collapse or a switch to human Japan.

Players can colonize whenever normal requirements permit. The Northern Colonial Administration event is available from the first Japanese holding in upper Manchuria or Sakhalin after formation, without the former Phase 2 requirement. AI Japan always chooses to charter it; players retain the direct-administration option.
