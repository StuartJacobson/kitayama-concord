# Kitayama Concord Alpha Testing Guide

For the alpha.78 release-candidate observer runs, use [OBSERVER_TESTS.md](OBSERVER_TESTS.md).

## Test goals

This alpha needs feedback on whether the alternate Japan is understandable,
fun, stable, and economically distinct across a long campaign. Targeted
commands are useful, but ordinary play is especially valuable because it
reveals AI, pacing, and economic interactions that scripted tests miss.

Use a fresh EU5 1.3 campaign with no other gameplay mods when possible.
Preserve a save from immediately before forming the Concord and make separate
backup saves before using destructive debug events.

## Things to look for

### Formation and first month

- Are the formation requirements understandable and achievable without
  distorting the opening campaign?
- Does **Proclaim the Kitayama Concord** create the new organization without
  generating a severe pause or error flood?
- Can the native Concord button be found easily?
- Does **Ratify the Kitayama Concord** remove the Shogunate and disappear?
- Does Japan become the Japanese Concordate with the correct ruler title?
- Are there exactly one Tenno, one Concord State, one Presiding House, and the
  expected Chartered Houses after the first monthly repair?
- Are internal wars forbidden after formation?

### Elections, leadership, and laws

- On a fresh formation, confirm Hosokawa, Shiba, and Hatakeyama receive the
  three founding Senior Charters when those Houses still exist.
- Confirm Senior Charter capacity starts at 3 and increases by exactly one at
  every 10 Entrenchment, reaching 13 at 100.
- Kill or naturally lose several rulers, including House rulers with child
  heirs. Elections should always finish without annexing or changing the
  player's country.
- Confirm ordinary Houses can serve as emergency shoguns and that a
  non-Senior elected House creates the stated Cohesion penalty.
- Check whether Senior Charters are affordable, valuable, and politically
  meaningful without becoming mandatory.
- Confirm election and law votes use economic weight rather than one vote per
  tag.
- Only Japan or a human-controlled member should initiate law changes. Watch
  for AI Houses silently beginning votes.
- Confirm accommodating laws have no monthly Cohesion cost, every middle law
  costs exactly 0.02, and every ambitious law costs exactly 0.04. The monthly
  Cohesion tooltip should combine all active laws under **Active Concord
  Laws**, while each policy displays its individual cost.
- Compare each policy family for real specialization: trade income versus
  reach, recruitment versus manpower, construction versus control,
  legitimacy versus stability, naval reach, and credit capacity.
- Under **House Retinues**, Chartered Houses should retain their building-based
  recruitment access, target larger armies, and receive **+50% Army
  Maintenance Efficiency**. **Registered Retinues** should preserve access but reduce desired
  army size without a net maintenance subsidy. **Common Arsenals** should
  give Chartered Houses **-50% Army Maintenance Efficiency**, discourage
  additional private forces, and support Japan's army without deleting
  existing House regiments.
- After 60 Entrenchment, compare the maritime laws in the same way. **House
  Port Privileges** should encourage larger House fleets and provide **+50%
  Navy Maintenance Efficiency**, **Licensed Coastal
  Convoys** should regulate and reduce them, and the **Concord Maritime Board**
  should give Chartered Houses **-50% Navy Maintenance Efficiency** and favor
  Japan's fleet without deleting existing House ships. A House still requires
  an owned Clan Shipyard to build ships.
- Look for laws that are obvious best choices, irrelevant choices, unclear
  tooltips, or combinations that exceed roughly +20% research speed or
  +0.020–0.030 global monthly development from the complete Concord stack.
- Confirm Council Patronage supplies its temporary voting bonus and clears
  after the ballot.

### Phase 2 framework and institutions

1. Complete the Hundred-Year Concord normally or run `event kc_debug.41` and
   choose its first option. Confirm **The Concord Faces the Open Sea** appears
   once and offers House delegations, a common foreign office, or a court
   compromise. Verify the listed societal-value movement and ordinary reward.
2. Confirm **Registers of the Open Sea** is researched automatically by the
   opening event. It should grant exactly one additional bureaucracy slot. The
   other five Phase 2 advancements unlock through the implemented maritime
   laws, stories, and colonial survey chain. Check each stated prerequisite;
   they should not all unlock at the opening event.
3. Advance one month. Confirm Japan receives one **Office of Maritime
   Exchange** at 50% maintenance. It must not replace or duplicate the Concord
   Secretariat. A save which already completed the opening event should receive
   both the advancement and Office through the monthly backfill.
4. Confirm the Office always gives +1 Diplomatic Reputation and +10% Maritime
   Presence. At full maintenance and zero Office Entrenchment, confirm it also
   gives +5% Institution Growth, -20% Diplomatic Spending Cost, and +125 Trade,
   Naval, and Colonial Range. At zero funding, confirm its Merchant Maintenance
   and Burgher Satisfaction penalties are fully active. Use `event kc_debug.42`
   and `event kc_debug.43` to verify funded effects halve at 50% maintenance,
   underfunding penalties shrink as maintenance rises, and funded effects reach
   exactly twice their base values at 100 Entrenchment. Confirm Entrenchment
   does not accumulate above 100.
5. Run `event kc_debug.41` again and choose its second option. Confirm Licensed
   Oceanic Convoys, Standardized Teppō Workshops, Houses of Translation, Silver
   Clearing Exchanges, and Colonial Survey Registers become visible with
   localized names, descriptions, modifiers, and the intended dependencies.
6. Advance one month after Registers of the Open Sea is researched. Confirm
   **The Maritime Constitution** fires once and offers **Council of Licensed
   Ports** or **National Board of Exchange**. Select each outcome from separate
   saves. The selected reform must add itself and supply the additional reform
   slot it occupies, coexist with either Age 1 Articles reform, and prevent the
   competing Age 2 reform from being adopted simultaneously. Verify every
   listed bonus, penalty, and constitutional-value drift.
7. Save and reload. Confirm the opening precedent, advancements, both
   bureaucracies, their maintenance and Entrenchment, and the selected reforms
   survive without duplicating. A capstone-complete save from alpha.34 should
   receive the opening event automatically on its next eligible monthly pulse.
8. On a disposable save, collapse the Concord. Confirm the Office of Maritime
   Exchange and either Phase 2 reform are removed and are not recreated inside
   the Warring Houses Interregnum.
9. Exit and inspect the logs for errors mentioning `kc_phase2_framework`,
   `kc_office_maritime_exchange_bureaucracy`, any of the six new advancements,
   or either Phase 2 reform.

### Phase 2 works and colonial registers

1. Complete the Southern Sea Exchange or run `event kc_debug.49` and advance
   one day. Confirm **The Second National Works Register** appears once.
2. Accept the register and open Administration > National Great Projects.
   National Floodworks, Transmontane Tunnels, and National Urban Waterworks
   should now be visible, retain their five stages, and remain unpurchased.
3. Save and reload. Confirm the unlock persists and the event does not repeat.
4. Run `event kc_debug.48`, enable the override, and advance one day. Confirm
   **Charts Returned from Across the Ocean** begins the Colonial Survey
   Registers chain. Its two follow-ups should arrive one day apart in debug.
5. Test common, House, and court options from separate saves. Confirm each
   option displays and applies its modifier, Cohesion or societal-value change,
   and that the jurisdiction choice determines the final twenty-year modifier.
6. Confirm the final event automatically researches **Colonial Survey
   Registers**, rather than merely revealing it in the advancement screen.
7. While the override remains enabled and Kyoto lacks New World, confirm the
   capital receives exactly one Institution progress per month. Disable the
   override and confirm progress stops unless the real colonial-nation and
   European-contact requirements are met.
8. Save/reload after completion. Confirm the advancement, final modifier, and
   both natural unlocks persist without repeated events. Inspect the logs for
   `kc_phase2_projects`, `kc_colonial_surveys`, or option-hover errors.

### Phase 2 dynamic events and Christian contact

1. Run `event kc_debug.51` repeatedly from separate reloads and test all ten
   Phase 2 events. Confirm every option shows its modifier, estate effects,
   societal-value movement, and Cohesion change before selection.
2. In ordinary play after the Southern Sea Exchange, confirm the Phase 2
   events join the existing recurring Concord pool rather than creating an
   additional annual event. The two-year shared cooldown and each story's
   ten-year cooldown should prevent event spam.
3. Colonial boundary and concealed-revenue events should not occur naturally
   before the Colonial Survey Registers; the concealed-revenue event also
   requires a colonial-nation subject.
4. Run `event kc_debug.50` and advance one day after every choice. Confirm all
   three Christian-contact events appear, ordinary options leave Japan's
   religion unchanged, and their modifiers and Cohesion changes are visible.
5. On a disposable reload, choose accommodation in the second event and then
   **The shogun shall receive baptism**. Confirm Japan and the ruler's family
   become Catholic, Cohesion falls by 20, the clergy suffers an extreme
   satisfaction loss, legitimacy falls, and the twenty-year court modifier is
   applied. Confirm the AI cannot select this conclusion.
6. On a normal non-Christian campaign after 1555, confirm the contact chain
   begins once after the Southern Sea Exchange and its natural follow-ups are
   separated by roughly three years. Save/reload between events and confirm
   the chain resumes without duplication.
7. As a Chartered House, open the Middle Kingdom diplomacy interface. Joining
   must be unavailable while the House belongs to the Concord; JAP remains the
   sole Concord member permitted to join. If an old save already contains
   House members, confirm the Concord's monthly safety net removes them.
8. Exit and inspect the logs for `kc_phase2_flavor`, `kc_christian_contact`,
   `zz_kc_middle_kingdom_compatibility`, missing localization, or event-option
   hover errors.

### Cohesion and Entrenchment

- Check whether every monthly Cohesion source in the tooltip matches the
  actual change to two decimal places.
- Confirm passive recovery changes at every ten Cohesion: +0.50 below 10,
  +0.40 from 10–19.99, +0.32 from 20–29.99, +0.24 from 30–39.99,
  +0.18 from 40–49.99, +0.12 from 50–59.99, +0.07 from 60–69.99,
  +0.03 from 70–79.99, and zero at 80 or higher.
- Confirm Japan receives one Concord Secretariat bureaucracy after formation.
  It should begin at zero native bureaucracy Entrenchment, independently of
  the Concord Entrenchment bar. At full maintenance, its Cohesion contribution
  should be approximately +0.14 at 0 bureaucracy Entrenchment, +0.18 at 25,
  +0.21 at 50, +0.25 at 75, and +0.28 at 100; at 50% maintenance those values
  should be halved. Its Diplomatic Spending Cost reduction should be
  approximately 15%, 18.75%, 22.5%, 26.25%, and 30% at the same Entrenchment
  values and should likewise be halved at 50% maintenance. Its minor Estate
  Satisfaction Recovery should remain constant at every maintenance and
  Entrenchment setting. At full maintenance, its displayed Treasury share
  should be 25%, 31.25%, 37.5%, 43.75%, and 50% at those same Entrenchment
  values. Its recurring expense and Treasury remittance should rise together.
- Run `event kc_debug.29` to select exact Secretariat Entrenchment values and
  `event kc_debug.40` to set maintenance to 0%, 50%, or 100%. Advance one month
  after each change and verify the Common Ledger's share, last remittance, and
  annual estimate. Confirm the Treasury itself receives exactly the displayed
  monthly remittance, the share and remittance halve at 50% maintenance, both
  reach zero at 0% maintenance, and neither is collected after collapse.
  At 100 native Entrenchment, advance several additional months and confirm
  both Entrenchment and the displayed Treasury share remain capped at exactly
  100 and 50% rather than accumulating floating-point overshoot.
  Confirm ordinary
  native Entrenchment growth resumes afterward and save/reload preserves it.
- Note the Cohesion range in which normal play settles and whether maintaining
  either very high or deliberately moderate Cohesion is strategically useful.
- Use these intended equilibrium bands when reporting balance results:
  accommodating governments should settle around 80-100 Cohesion, mixed
  governments around 60-80, and fully ambitious governments around 40-60.
  A fully ambitious Concord should therefore remain outside disaster territory
  but be approximately one severe incident away from it.
- Entrenchment should pause during its two transition crises and resume after
  resolution.
- Watch milestone events, law unlocks, Banking progress, the Council Hall,
  crisis thresholds, and the 100-Entrenchment capstone for missed or repeated
  triggers.
- Report any value that moves while the Concord is collapsed.

### Visual identity

- After a full restart, inspect the Concord's bottom-screen icon, wide header,
  and Chartered, Senior, Concord State, and Presiding House rank symbols.
- Inspect every custom building, the three Concord advances, the Secretariat,
  both Age 1 reforms, and both sides of House Privilege versus Concord
  Commonwealth. Report any missing, checkerboard, stretched, or unrelated art.
- Start The Unquiet Peace, The Great Reckoning, The Hundred-Year Concord, and
  the Fracturing Concord. Each should have its own icon and wide Japanese scene
  without disturbing its functional panel layout. Their opening, incident,
  settlement, ratification, collapse, and recovery events should reuse the
  appropriate custom scene rather than a vanilla Peasants' War, Reform
  Society, Professional Armies, or Sengoku image.

### Treasury and House economy

- Confirm contributions, mediation, annual assessments, arrears, credit
  stabilization, emergency programs, and Common Works use the displayed
  amounts.
- Open the Concord's **Administration** tab. Its internal **Treasury** and
  **National Great Projects** views should switch without a large empty area,
  jumping the scrollbar, or moving either view's first card away from the top.
- Test **Maintain Common Granaries**, **Fund Common Security**, and
  **Underwrite Maritime Ventures** from the internal Treasury view. Each should spend
  only Concord Treasury gold, last five years, use an independent five-year
  cooldown, and affect exactly the countries stated in its tooltip.
- All recurring programs based on Japan's trade-and-tax income should stop
  rising at **5,000 gold**. Confirm the displayed requirement, deducted amount,
  and transferred amount remain identical after the cap is reached.
- **Stabilize House Credit** should use the richest Chartered House's tax base
  rather than Japan's income, increase with the latest arrears count, and never
  exceed 5,000 gold.
- Treasury actions that grant modifiers should show the native modifier name
  and component list beneath a short payment/result explanation rather than
  duplicating every modifier value in prose.
- Grand Irrigation, the National Kaido, and the Inland Sea Harbor Chain should
  unlock at 75, 85, and 95 Entrenchment. Irrigation and Harbor authorizations
  cost 1,000, 2,000, 4,000, 8,000, and 16,000 gold because Japan must separately
  construct and maintain the local network. Kaido retains its national cost.
- Each network stage raises its local building cap by one. Stages II-V must
  remain unavailable until Japan maintains the displayed number of effective
  building levels. Construction, workers, and maintenance goods should control
  where the economic benefits actually operate.
- At local Level V, confirm Irrigation reaches +15% Monthly Development Growth,
  +25% Food, and +15% Raw Materials; Seto Harbor Works reaches +0.25 Harbor
  Capacity; Floodworks reaches +0.1% Population Growth, +15% Capacity, and
  +2.5% Maximum Control; and Urban Water Bureaus give Stream-tier benefits plus
  +10% Disease Resistance. Kaido and Tunnels remain national/provincial works.
- Every Irrigation and Harbor level should cost 100 gold. Every Floodworks and
  Water Bureau level should cost 200 gold. Maintenance should use Masonry rather
  than raw Stone; Seto Harbor Works should additionally require Cloth and Tar.
- The National Great Projects view should first appear at 75 Entrenchment. It
  should reveal Irrigation at 75, Kaido at 85, the Harbor Chain at 95, and the
  Metropolitan Charter at 100 rather than displaying future buttons early.
- National Floodworks, Transmontane Tunnels, and National Urban Waterworks are
  Phase 2 projects. They remain hidden before the Southern Sea Exchange, then
  unlock together through the Second National Works Register. Debug event 35
  still exposes them for framework testing. Floodworks and Waterworks
  authorizations cost 2,000, 4,000, 8,000, 16,000, and 32,000; Tunnels retain
  their route-only national costs.
- After at least one Urban Waterworks stage, promote a Japanese rural location
  into a town. It should become eligible to construct an Urban Water Bureau but
  receive no free benefit until Japan builds and maintains it.
- The Metropolitan Charter is not one of the six staged works. At 100
  Entrenchment it should cost 10,000 gold and convert one selected urban location of at
  least 400,000 population into the Concord's unique Megalopolis. At 100 it
  should be visible without scrolling through Treasury programs.
- Commission Common Works repeatedly. The first 20 licenses should cost 500
  gold per batch of five; later five-license batches should cost 1,000, 2,000,
  4,000, 8,000, and finally 16,000 gold as the issued total rises.
- Watch whether the Treasury becomes a meaningful strategic reserve rather
  than an inexhaustible bank or permanent money sink.
- Compare the three Great Reckoning fiscal settlements over several decades.
- Observe whether Houses become excessively rich, permanently insolvent, or
  unable to construct their intended buildings.
- Test player and AI Charter Redemption. Report purchases that are too cheap,
  profitable because of transferred reserves, too frequent, or never occur.
- The Concord should never fall below twenty-four Chartered Houses through
  ordinary redemption.

### Buildings and infrastructure

- Confirm Japan cannot see House-only buildings and Houses can construct them
  without needing 100 relations with Japan.
- Check Kaisho, Jisha-za Temple, Kaido Post Station, inherited clan buildings,
  Tea Gardens, Silk Farms, and Iwor buildings for caps, inputs, outputs,
  profitability, AI use, and tooltip clarity.
- Shoen should have five real output methods. Tatara should have only tools
  and weapons. No blank-output copies should appear.
- Tea and Silk capacity should scale like Shoen.
- An Ezo location with about one thousand Ainu tribesmen should operate two
  Iwor Stewardship levels and two Iwor Exchange levels together.
- Check the Muster Office, Ledger Office, Council Hall, and licensed Works
  District for construction limits and rewards.

### Ezo and colonization

- Verify Ezo remains protected from unintended foreign colonizers.
- Settlement policy should wait until the entire province is colonized and
  affect every location in that province.
- Each treated location should restore approximately 400-650 Ainu tribesmen,
  capped near one thousand.
- Check whether the three settlement policies create distinct demographic,
  economic, cultural, and Cohesion choices.
- Watch Ainu assimilation, promotion, cultural acceptance, opinion, and
  building employment over several decades.
- Confirm the Surveyed Settler District penalty decays over thirty years.
- After a settlement policy is recorded, watch for the Shimamaki iron-sand
  and Niikappu horse-breeding discoveries. Either choice must replace exactly
  one raw material and must not repeat afterward.
- The Itomuka mercury discovery should require settled Kitami and at least 80
  Entrenchment. Compare the slower inspected-adit path with the more productive
  but locally harmful House concession.
- Use `event kc_debug.31` followed by `event kc_ezo_discoveries.1`, `.2`, and
  `.3` from separate reloads for fast discovery testing.
- Report whether colonization is too easy, too slow, or economically pointless.

### Dynamic Concord events

- Over ordinary play, expect approximately one Concord event every three to
  four years rather than every year. No individual story should repeat within
  ten years.
- Confirm all twelve events use the Concord visual identity and fully explain
  their cost, Cohesion, estate, temporary-modifier, and societal-value effects.
- Public settlements generally cost money and protect Cohesion; private House
  settlements generally improve estate Satisfaction while sacrificing a
  small amount of Cohesion. Report any option that is always superior.
- Before the capstone, relevant outcomes should move existing Innovation,
  Capital Economy, Plutocracy, or Conciliation values. After the capstone,
  the same constitutional choices should also move House Privilege versus
  Concord Commonwealth.

### Foundational history, 1401-1466

- In an ordinary fresh campaign, confirm only one foundational chain can be
  active at a time and that new chains wait while a disaster is active.
- The Chinese tally-trade chain should begin from 1401, the founder chain from 1408, the
  Tsushima chain from 1419, the Shōchō chain from 1428, and Port Autonomy from
  1445. A Concord founded after those dates should catch up sequentially rather
  than permanently missing the stories.
- Run `event kc_debug.37` to test any chain rapidly. Advance one day after each
  event choice and reload before testing a different branch.
- Confirm the persistent Foreign Commerce, Public Order, Credit, and Port
  Government precedents agree with the selected settlements. These precedents
  are reserved for **The War That Never Was** and later maritime content.
- Confirm all temporary and concluding modifiers are shown natively, every
  Cohesion movement is explicit, and Treasury options cannot be selected when
  the common reserve lacks the displayed funds.
- Save and reload in the middle of every chain. The scheduled follow-up and
  active-chain lock must survive, and the next dated chain must begin normally
  once the current chain concludes.

### The War That Never Was, from 1467

- In ordinary play, confirm the Situation begins after 1467 once all five
  foundational chains are complete and no disaster is active. It should not
  overlap another historical chain or the Hundred-Year Concord.
- Confirm its custom panel displays Settlement Progress to two decimals, the
  current monthly rate, six incident milestones, localized end requirements,
  a map mode, and the new situation artwork and icon.
- Monthly Progress should begin at 0.30, gain the stated bonuses from peace,
  Cohesion thresholds, and Secretariat funding, and receive the stated
  penalties from war and Cohesion below 25. The Concord's native Cohesion
  breakdown should list **The War That Never Was: -0.15 per month**.
- Use `event kc_debug.38` to start a disposable test and `event kc_debug.39`
  sequentially at 19.90, 34.90, 49.90, 64.90, 79.90, and 89.90. Confirm every incident occurs
  once and every option displays its gold, Cohesion, estate, societal-value,
  modifier, Settlement Progress, and precedent consequences.
- Incident choices should restore no more than 2 Cohesion or cost a net 3-8
  Cohesion after any applicable historical precedent.
- The representative debug precedents should strengthen the permanent electoral
  procedure, mediated credit, Concord warehouse seals, central constabulary,
  and Concord tally register choices. No precedent may remove another choice.
- Test the Compact of Coequal Houses, Dual Covenant, and Ordinance of Public
  Peace from separate saves. Each must end the Situation, remove its temporary
  member and Japan penalties, grant its stated Cohesion and twenty-year legacy,
  and survive save/reload.
- At the later Hundred-Year Concord, confirm the House and Public settlements
  contribute 20 points toward House Privilege or Concord Commonwealth,
  respectively, while the balanced settlement contributes no movement.
- Leave the panel open, hover every event option, and inspect the fresh logs for
  errors mentioning `kc_war_that_never_was`, `kc_war_never_was`, unset
  variables, invalid situation scopes, or repeated GUI evaluation.

### The Unquiet Peace at 30 Entrenchment

- Confirm all three preparations are explained and remain non-locking.
- Test the Constabulary, Fortified Roads and Harbors, and House Watches
  resolutions from separate saves.
- Incidents should create meaningful Treasury, Cohesion, and temporary-penalty
  choices rather than a free option.
- Confirm the five-year minimum, material requirements, law support, legacy,
  and Professional Armies rewards.

### The Great Reckoning at 70 Entrenchment

- Confirm the seven-year minimum, three preparation mandates, incidents, law
  preferences, Ledger Office, and completion actions.
- Test Great House Guarantees, Registered Apportionment, and Common Treasury
  from separate saves.
- Compare long-term Treasury income, Cohesion drift, House arrears, and the
  strength of each settlement.
- Confirm completion gives Renaissance presence in Japan's capital.

### Capstone, societal value, and collapse

- At 100 Entrenchment after the Great Reckoning, confirm The Hundred-Year
  Concord starts as a Situation rather than immediately ratifying the
  constitution. Confirm its description, map mode, legend, current progress,
  end condition, and monthly breakdown are fully localized.
- Confirm Drafting Progress begins at 1.00 monthly, gains the stated bonuses
  from peace, Cohesion thresholds, and Secretariat funding, and receives the
  stated penalties from war and Cohesion below 20.
- Confirm the authority, legal-language, and publication readings occur once
  at 25, 50, and 75 progress. Test every option from separate saves, including
  disabled Treasury and national-funds options.
- Use `event kc_debug.30` to test progress 24, 49, 74, and 99 quickly. Advance
  one month after each selection.
- While the Situation is active, click its native Situation alert or map icon.
  Confirm the Hundred-Year Concord panel opens, its Drafting and monthly
  progress values update, and each reading changes from Pending to Concluded.
- Leave the Situation panel open for at least one minute, close it, and reopen
  it. After exiting EU5, confirm the logs contain no repeated
  `character_header.gui`, `Unknown formatting tag`, or missing
  `situation_panel` errors.
- At 100 progress, confirm The Hundred-Year Concord uses the Unquiet Peace,
  Great Reckoning, and War That Never Was settlements together with all three
  readings to set the initial societal value.
- Confirm Japan's capital receives exactly 100 Printing Press progress and the
  selected twenty-year House Imprints, Common Edition, or Movable-Type Office
  modifier.
- Confirm the mutually exclusive Age 1 reforms Articles of Chartered Liberties
  and Council of Common Stewardship become available. Each should supply +0.05
  monthly Cohesion, move the new societal value in the stated direction, and
  provide its distinct commercial or administrative modifiers.
- Confirm Nobles, Burghers, Clergy, and Peasants each receive two new
  post-capstone privileges: one favoring House Privilege and one favoring
  Concord Commonwealth. Each estate's pair must be mutually exclusive and
  its benefits must include the stated small penalty.
- Grant four privileges aligned to one side and verify their monthly drift
  combines with the selected Age 1 reform without overwhelming event choices.
- Collapse the Concord with privileges active. All eight Concord-specific
  privileges and their modifiers should be revoked during the conversion.
- Both House Privilege and Concord Commonwealth should offer credible benefits.
- Confirm collapsing the Concord while the Situation is active ends it without
  granting Printing Press, reforms, the societal value, or a publication
  legacy.
- Below 25 Cohesion, watch the Fracturing Concord's monthly risk and emergency
  recovery tools. While the disaster is active, its emergency measures should
  be the first card in the Treasury view, above the Common Ledger.
- Recovering at 40 Cohesion should preserve the Concord.
- Collapsing at zero should land nearly every viable House, permit internal
  wars and permanent inter-House claims, preserve the player as Japan, and
  leave an inert Warring Houses Interregnum without a leader, laws, Treasury,
  elections, or active progress.
- Test save/reload after the capstone, during Fracturing, and after collapse.

### AI, performance, and campaign health

- Complete a Taiwanese province and confirm exactly one settlement panel
  appears for it. Its selected modifier must cover the whole completed
  province and survive save/reload.
- Establish each Philippine compact from a reload. Tondo, Cebu, or Butuan must
  become a Commercial Protectorate, receive Japan's holdings in its own area,
  and continue receiving later Japanese settlements there.
- Use a northern foothold outside Liaodong to charter the Northern Colonial
  Administration. Later Japanese locations in upper Manchuria or Sakhalin
  should transfer to that same colonial nation on the next monthly tick.
- For the continental branch, verify diplomacy and commercial exchange end the
  chain peacefully. The war branch must grant the Korea CB; its required peace
  term costs 60 war score and moves the Korean region to Japan before the
  settlement event appears.
- From reloads, test unified Korean protectorate, four extraction commissions,
  and direct rule. Japan must remain playable in every outcome.
- Authorize the China campaign and verify both CBs target the current `CHI`
  country. Haiyou, Zhejiang, Fujian, Guangdong, and Haibei/Hainan are the only
  selectable sectors; each costs 20 War Score, for exactly 100 total. Only the
  designated treaty-coast locations represented in the reference save should
  transfer, rather than each entire area. The commercial term creates a
  Commercial Protectorate, while the extraction term creates an Extraction
  Commission and immediately removes 3 Concord Cohesion.
- As Concord Japan, open Make Subjects and confirm both Commercial Protectorate
  and Chartered Extraction Commission are available when releasing a country
  or province. The Extraction Commission must charge 3 Cohesion through this
  route as well.
- Run `event kc_debug.62` on a save containing both subject types. Confirm all
  six panels name an actual Japanese subject, show their Treasury, Cohesion,
  societal-value, and modifier effects natively, and use the Korean, Chinese,
  Philippine, or Taiwanese description when the chosen subject qualifies.
- Confirm monetary amounts equal two, four, or six months of the selected
  subject's trade-and-tax income as appropriate, can exceed 5,000 gold, and do
  not change merely because Japan's own income changes.
- In **The Overseas Assessment**, confirm the first and third choices give
  Japan temporary merchant power specifically in the market containing the
  subject's capital, rather than a global Japanese trade modifier.
- In the charter-review panel, convert an Extraction Commission into a
  Commercial Protectorate. The same country, ruler, and territory must remain;
  only the subject constitution should change. From reloads, compare the
  registered-reform and tightened-charter alternatives.
- Advance at least twenty years with either overseas subject type. Consequence
  events should occur no more often than once every four years, individual
  stories should not repeat within sixteen years, and the pool must remain
  silent during historical chains or an active disaster.

- Observe AI law votes, charter purchases, redemptions, building priorities,
  Treasury solvency, colonization, and crisis responses.
- Report monthly-tick freezes, UI stalls, excessive event repetition, or
  performance changes as House count falls.
- Watch for members losing their type, the Concord losing leadership outside
  the collapsed state, or Japan losing access to its actions.
- Check whether other countries behave strangely around protected Ezo, Taiwan,
  or the Philippines.
- Chartered Houses must not join the Middle Kingdom. On an affected old save,
  up to twelve existing House memberships should be removed per monthly tick
  until none remain, without a freeze or error flood. Japan itself may retain
  or seek centralized Middle Kingdom membership.
- Note whether the alternate Japan is stronger or weaker than a comparable
  ordinary Japanese campaign and why.

### Presentation and persistence

- Report pink text, missing localization, incorrect names or ruler titles,
  clipped panels, empty tooltips, duplicate methods, and unclear requirements.
- Save and reload after formation, elections, law votes, charter changes,
  acquisitions, settlement policies, both crises, the capstone, and collapse.
- From a post-capstone campaign, verify the 1523 Ningbo chain concludes without
  violence, grants Licensed Oceanic Convoys automatically, and never hardcodes
  the current holder of China as Ming.
- In the Southern Sea Exchange, compare progress with the Office of Maritime
  Exchange unfunded, partially funded, and fully funded; then test every
  firearms, powder, silver, translation, missionary, treaty-port, and final
  settlement branch from reloads.
- Confirm the unique Southern Exchange Hall remains limited to one Japanese
  coastal location, survives save/reload, consumes its listed maintenance, and
  can be rebuilt elsewhere if destroyed.
- After the Southern Sea Exchange, verify Kyoto gains exactly one New World
  institution point per month only while Japan has a colonial-nation subject
  and knows a country whose capital is in Europe.
- At 76 Southern Sea Exchange progress, verify the Southern Islands Survey
  appears once. Every sponsor must grant all four Taiwanese exclusive claims
  and thirty-year Ryukyu settlement CBs; unused Taiwanese claims must disappear
  after the temporary access variable expires.
- Test the Tondo, Cebu, and Butuan loyalty purchases separately. Confirm each
  can be opened through Taiwan ownership, Maynila market leadership, or a
  matching local foothold; its Treasury price must equal sixty months of that
  partner's current trade-and-tax income, and acceptance must transfer both
  Japanese holdings and colonial claims for only the matching island group.
- Complete the four Red-Seal Charter events from 1590 onward. Check every
  modifier and value movement, all one-day debug follow-ups, the clearing of
  the historical-chain lock, and the final legacy after save/reload.
- In 1609, test independent, Japanese-subject, and directly ruled Ryukyu. The
  settlement must adapt without annexing Japan, preserve local territory when
  appropriate, and create the selected Commercial Protectorate, Extraction
  Commission, partnership, or crown-port outcome.
- From 1600 onward, confirm Merchants of Competing Europes begins only after
  the Red-Seal and Tensho chains are complete. Run all four events, verify that
  every option displays its modifier and Cohesion/value movement without hover
  errors, and confirm the final common, House, or national precedent survives
  save/reload without selecting a permanent European patron.
- From 1610 onward, confirm Japanese Overseas Communities follows the company
  chain even for a trade-focused Japan without formal colonies. Test all five
  events. Existing and later qualifying overseas subject capitals must receive
  exactly one permanent Registered Nihonmachi modifier; it must never be
  removed and reapplied every month.
- Use `event kc_debug.68` to start Regulation of the Open Seas. Confirm the
  dedicated panel displays Ratification Progress, exact monthly progress,
  three influence values, and six article rows without clipping or an empty
  monthly section. Compare progress at peace, at war, with the Maritime Office
  above and below half funding, with and without an overseas subject, and with
  Cohesion above and below 20.
- Use `event kc_debug.69` and `event kc_debug.70` to test every influence preset
  and article. Earlier maritime choices may change starting influence and AI
  preference but must never hide a final outcome from the player.
- Finish with `event kc_debug.71` and one monthly tick. Each final choice must
  add exactly one of Commonwealth of Chartered Ports, Articles of Registered
  Open Ports, or National Maritime Administration; remove the provisional
  Council/National Board; preserve its reform slot; and activate its funded
  Maritime Office modifier at 50% or greater maintenance.
- Save and reload during the Situation and after each final reform. Then test a
  Concord collapse during the Situation: it must end unsuccessfully, clear the
  historical-chain lock, and never grant a final reform.
- When ending a session, fully close EU5 before collecting the logs.

## Bug report template

```text
EU5 version:
Kitayama Concord version:
Other enabled mods:
Country and date:
Concord leader:
Cohesion / Entrenchment:
What happened:
What you expected:
Steps to reproduce:
Does save/reload change it:
Debug command used, if any:
Save / screenshot / error.log excerpt:
```
