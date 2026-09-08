# Kitayama Concord Debug Events

Run commands from the EU5 console in debug mode. Unless a command says
otherwise, select Japan in a formed-Concord save, pause the game, run
`event kc_debug.N`, and then advance one monthly tick if the expected result
does not occur immediately.

These events deliberately mutate campaign state. Use backup or disposable
saves. Events 5-9, 20-25, and 27 are especially unsuitable for a continuing
campaign.

For the two normal-progress observer runs, use [OBSERVER_TESTS.md](OBSERVER_TESTS.md); do not use milestone-completion cheats in those runs.

| Command | Purpose |
| --- | --- |
| `event kc_debug.1` | Add 10 Concord Cohesion. |
| `event kc_debug.2` | Remove 10 Concord Cohesion. |
| `event kc_debug.3` | Add 10 Concord Entrenchment. |
| `event kc_debug.4` | Remove 10 Concord Entrenchment. |
| `event kc_debug.5` | Temporarily reduce the Concord to exactly 25 Chartered Houses, set both bars to 100, clear the selected country's redemption cooldown, and add abundant gold for testing the permanent 24-House redemption floor. Normal monthly membership repair may re-add removed Houses. |
| `event kc_debug.6` | Reset Banking notification and all 10/20/40/60/80 Entrenchment milestone flags and policies, then set Entrenchment to zero for a clean unlock sequence. |
| `event kc_debug.7` | Destructively create an Oshima settlement test: give every eligible unowned location in the province to the selected country and add one thousand sponsor-culture peasants to each. |
| `event kc_debug.8` | Add one thousand people to a random protected Ainu tribesmen pop so the approximately 1,000-person growth cap can be checked quickly. |
| `event kc_debug.9` | Replace every owned thirty-year Surveyed Settler District subsistence penalty with a one-year copy to test continuous decay. |
| `event kc_debug.10` | Prepare The Unquiet Peace: clear its completion markers and set Entrenchment to exactly 30. Advance one month as Japan. |
| `event kc_debug.11` | During The Unquiet Peace, fund the Treasury and bypass time and material requirements so the prepared route resolves on the next monthly tick. |
| `event kc_debug.12` | During The Unquiet Peace, expire only the five-year minimum and supply twelve months of Treasury income. The visible completion actions and normal route requirements remain. |
| `event kc_debug.13` | Instantly build a free Kaisho in Japan's capital for up to 26 Houses lacking a Kaisho or completed Kaido Post Station, allowing the House Watches ownership requirement to be tested. |
| `event kc_debug.14` | Prepare The Great Reckoning: mark The Unquiet Peace complete, clear Reckoning markers, and set Entrenchment to 70. Advance one month as Japan. |
| `event kc_debug.15` | Prepare all material Reckoning requirements: expire seven years, authorize and build three Ledger Office levels, set Cohesion to 100, fund fifteen months of Treasury income, and grant at least eight Senior Charters. The relevant law remains to be passed. |
| `event kc_debug.16` | During The Great Reckoning, fund the Treasury and force completion on the next monthly tick. If no visible settlement was selected, the opening mandate determines the fallback. |
| `event kc_debug.17` | Remove the annual assessment timer and give every House twelve months of income so the next collection tests normal solvent payments. |
| `event kc_debug.18` | Create exactly eight Houses in assessment arrears and fund the Treasury. Stabilize House Credit should cost six months of Japan's trade-and-tax income. |
| `event kc_debug.19` | Add five cumulative Common Works District licenses without paying Treasury funds or starting the program cooldown. |
| `event kc_debug.20` | Open a two-stage capstone setup. First select an Unquiet Peace legacy, then select a Great Reckoning settlement in event 22. Both crises are marked complete and Entrenchment becomes 100 so the Hundred-Year Concord Situation starts next month. |
| `event kc_debug.21` | Set Cohesion to 20 and force The Fracturing Concord to begin on the next monthly spawn check. Works before or after the capstone. |
| `event kc_debug.22` | Second stage normally opened by event 20. Select Great House Guarantees, Registered Apportionment, or Common Treasury; mark both crises complete and set Entrenchment to 100. Running it directly skips selection of an Unquiet Peace legacy. |
| `event kc_debug.23` | During The Fracturing Concord, set Cohesion to zero so the normal collapse event appears on the next monthly tick. |
| `event kc_debug.24` | During The Fracturing Concord, set Cohesion to 40 so the normal recovery event appears on the next monthly tick. |
| `event kc_debug.25` | Destructive isolation test: execute the bounded warring-House landing effect while preserving the Concord object. Reload before repeating. |
| `event kc_debug.26` | Legacy no-op retained so older testing instructions do not call a missing event. |
| `event kc_debug.27` | Full-scale destructive landing test after event 25 or a completed collapse. Attempts to turn every remaining Chartered House into a landed state; Houses without a viable location may disappear. |
| `event kc_debug.28` | Safe post-collapse shell repair. If the Concord is already collapsed, reset both bars to zero, clear the active crisis marker, and restore Japan's collapsed-state flag without creating, destroying, replacing, or changing IO membership. |
| `event kc_debug.29` | Open a five-option Secretariat test event that sets its native bureaucracy Entrenchment to 0, 25, 50, 75, or 100. At full maintenance the expected Cohesion contributions are approximately 0.14, 0.18, 0.21, 0.25, and 0.28, while Diplomatic Spending Cost reductions are approximately 15%, 18.75%, 22.5%, 26.25%, and 30%; at 50% maintenance both are halved. The passive Estate Satisfaction Recovery should remain constant. |
| `event kc_debug.30` | While the Hundred-Year Concord Situation is active, set Drafting Progress to 24, 49, 74, or 99. Advance one month to test the corresponding reading or final ratification. |
| `event kc_debug.31` | Destructively assign Shiribeshi, Hidaka, and Kitami to the selected Concord member, mark them as settled, restore the three discovery inputs, set Entrenchment to 80, and add testing gold. Use only on a disposable save. |
| `event kc_debug.32` | Select House Retinues, Registered Retinues, or Common Arsenals immediately. Use one save to compare House army targets, recruitment, and maintenance behavior under all three arms settlements. |
| `event kc_debug.33` | Set Entrenchment to 80 and select House Port Privileges, Licensed Coastal Convoys, or the Concord Maritime Board immediately. Use one save to compare House naval behavior under all three maritime settlements. |
| `event kc_debug.34` | Prepare recurring Treasury testing: set Entrenchment to 80, mark both crises complete, clear the three new program cooldowns and modifiers, and add 100,000 gold to the Concord Treasury. |
| `event kc_debug.35` | Destructively reset all six five-stage great works and their Japan-region modifiers; expose the three future Phase 2 projects; set Entrenchment to 100; add 750,000 Treasury gold; and add 400,000 people to Japan's capital so the separate 10,000-gold Metropolitan Charter can be tested. |
| `event kc_debug.36` | Authorize Level V of all four physical infrastructure networks without constructing buildings, allowing direct tests of local eligibility, five levels, staffing, maintenance, and modifiers. |
| `event kc_debug.37` | Open the five foundational historical-chain launchers and run the selected chain in one-day rapid mode. |
| `event kc_debug.38` | Prepare representative earlier precedents, set Cohesion to 70, fund Japan and the Treasury, and directly activate The War That Never Was from a formed-Concord save. The Situation must not already be active. |
| `event kc_debug.39` | While The War That Never Was is active, set Settlement Progress to 19.90, 34.90, 49.90, 64.90, 79.90, or 89.90. Advance one month to test the selected incident. |
| `event kc_debug.40` | Set Concord Secretariat maintenance to 0%, 50%, or 100%. Combine with event 29, advance one month, and verify its Cohesion, Diplomatic Spending, Treasury share, monthly remittance, and annual estimate. |
| `event kc_debug.41` | Either replay the normal Phase 2 opening after marking the Hundred-Year Articles complete, or expose all five later story-gated Phase 2 advancements and grant Research Progress. |
| `event kc_debug.42` | Set Office of Maritime Exchange maintenance to 0%, 50%, or 100%. The Office must already exist. |
| `event kc_debug.43` | Set Office of Maritime Exchange bureaucracy Entrenchment to 0, 50, or 100 for exact scaling tests. |
| `event kc_debug.44` | Start the four-event Tallies of Ningbo chain in one-day rapid mode with ample Japanese and Treasury funds. |
| `event kc_debug.45` | Prepare the maritime prerequisites and open the Southern Sea Exchange at zero progress. |
| `event kc_debug.46` | Move an active Southern Sea Exchange immediately before any of its seven ratification thresholds. |
| `event kc_debug.47` | Move an active Southern Sea Exchange to 99.90 progress for completion on the next monthly tick. |
| `event kc_debug.48` | Toggle the colonial-nation and European-contact test override. Enabling it resets and opens the Colonial Survey Registers chain one day later, makes its follow-ups arrive one day apart, and enables monthly New World Institution progress. |
| `event kc_debug.49` | Remove the later Great Projects unlock while preserving a completed Southern Sea Exchange, then open the Second National Works Register one day later. |
| `event kc_debug.50` | Reset and open the three-event Christian-contact chain one day later. Follow-ups arrive one day apart, and the player-only baptism conclusion is exposed for testing. |
| `event kc_debug.51` | Open a selector for all ten recurring Phase 2 maritime, colonial, firearms, religious-contact, and commercial events. Its governor-ledger option temporarily bypasses the natural colonial-nation requirement. |
| `event kc_debug.57` | Open and fund the Tondo, Cebu, or Butuan five-year-income loyalty compact. |
| `event kc_debug.63` | Open the Southern Islands Survey or immediately expire its unused settlement rights. |
| `event kc_debug.64` | Run the four Red-Seal Charter events one day apart. |
| `event kc_debug.65` | Run the two-event adaptive 1609 Ryukyu Settlement one day apart. |
| `event kc_debug.72` | Prepare the two late Harbor authorization buttons, seed a thirty-level Outer Port network for the Southern Ocean requirement, or reset both extensions. |

## Useful sequences

### Entrenchment unlocks

1. `event kc_debug.6`
2. Use `event kc_debug.3` repeatedly.
3. Advance a monthly tick at 10, 20, 40, 60, and 80.

### The Unquiet Peace

1. `event kc_debug.10`
2. Advance one month and choose a preparation.
3. Use `event kc_debug.12` to test real completion requirements, or
   `event kc_debug.11` for a fast resolution.

### The Great Reckoning

1. `event kc_debug.14`
2. Advance one month and choose a preparation.
3. Use `event kc_debug.15` to prepare normal completion, or
   `event kc_debug.16` for a fast resolution.

### Capstone and collapse

1. `event kc_debug.20`
2. Select both prior crisis outcomes.
3. Advance one month to start The Hundred-Year Concord.
4. Use `event kc_debug.30` and advance one month to test each reading and
   ratification. Reload before retesting a milestone that already fired.
5. `event kc_debug.21`
6. Advance until The Fracturing Concord starts.
7. Use `event kc_debug.24` to test recovery or `event kc_debug.23` to test
   collapse from separate saves.

### Dynamic Concord events

Run `event kc_concord_flavor.1` through `event kc_concord_flavor.12` in a
formed-Concord save. Confirm every option explains its Cohesion, estate,
temporary-modifier, and societal-value consequences. In ordinary play the
pool checks yearly, has a two-year shared cooldown, and prevents an individual
story from repeating for ten years.

### Foundational historical chains

Run `event kc_debug.37` as JAP in a formed-Concord save. The event offers five
test launches and destructively clears all earlier outcomes from this content
package. After selecting a chain, advance one day after every choice; rapid
mode schedules each follow-up one day apart.

- **Chinese Tally Trade:** four events covering the embassy, the title of King of
  Japan, the tally allotment, and the returning ships.
- **The Concord After Its Founder:** three events covering constitutional
  continuity, custody of the seals and registers, and the future of Chinese trade.
- **Tsushima, Joseon, and the Wakō:** four events covering Joseon's complaints,
  the 1419 expedition, the maritime settlement, and its enforcement.
- **The Shōchō Debt Crisis:** three events covering the burning ledgers,
  tokusei, mediated repayment, strict enforcement, and the resulting doctrine.
- **Port Autonomy:** four events covering port petitions, municipal versus
  national versus House government, warehouse jurisdiction, and the final
  port constitution.

Confirm every choice lists its estate, societal-value, Cohesion, gold, and
modifier effects; unaffordable national or Treasury choices should be disabled.
Each chain must end by removing rapid mode and its active-chain lock.

### The War That Never Was

1. Run `event kc_debug.38` in a formed-Concord save and choose the first option.
2. Confirm the Situation panel opens with Settlement Progress, monthly progress,
   six incident rows, its map mode, and fully localized end requirements.
3. Run `event kc_debug.39` sequentially and advance one month after selecting
   19, 34, 49, 64, 79, and 89. Test all incident branches from reloads.
4. Confirm the native Cohesion breakdown lists **The War That Never Was** at
   -0.15 per month. Incident gains must not exceed 2 Cohesion and incident
   losses must fall between 3 and 8 after applicable precedent reductions.
5. Confirm the representative Concord precedents strengthen the Secretariat,
   mediated-credit, Concord-port, central-patrol, and Concord-tally choices
   without hiding or disabling the alternatives.
6. The Final Convention adds the last ten Progress and resolves the Situation.
   Test all three final settlements from separate saves.

### Ezo economic discoveries

1. Run `event kc_debug.31` on a disposable formed-Concord save.
2. Run `event kc_ezo_discoveries.1`; Shimamaki should change from Sand to
   Iron under either option.
3. Reload or rerun event 31, then run `event kc_ezo_discoveries.2`; Niikappu
   should change from Millet to Horses under either option.
4. Reload or rerun event 31, then run `event kc_ezo_discoveries.3`; Tokoro
   should change from Fish to Mercury under either option.
5. In an ordinary campaign, the Itomuka event must remain unavailable before
   80 Entrenchment and before Kitami receives an Ezo settlement policy.

### Concord estate privileges

Use a post-capstone save. Each of the Nobles, Burghers, Clergy, and Peasants
should show one House Privilege settlement and one Concord Commonwealth
settlement. The two privileges belonging to the same estate must be mutually
exclusive. Confirm their monthly societal-value drift and modifiers disappear
if the Concord collapses.

### Military, naval, and Treasury laws

1. Run `event kc_debug.32` and compare all three arms settlements from the
   same save. House Retinues should give Chartered Houses +50% Army Maintenance
   Efficiency; Registered Retinues should be neutral; Common Arsenals should
   give Houses -50%, shift desired force size toward Japan, and not delete
   existing House units.
2. Run `event kc_debug.33` and compare all three maritime settlements. House
   Port Privileges should give Chartered Houses +50% Navy Maintenance
   Efficiency; Licensed Coastal Convoys should be neutral; the Maritime Board
   should give Houses -50%, shift desired force size toward Japan, and not
   delete existing House ships.
3. Run `event kc_debug.34`, open **Administration > Treasury**, and test
   Maintain Common Granaries, Fund Common Security, and Underwrite Maritime
   Ventures.
4. Confirm each action deducts the displayed Treasury cost, applies its
   five-year modifiers to the stated recipients, starts its own five-year
   cooldown, survives save/reload, and never spends Japan's national treasury.
5. Run `event kc_debug.35` on a disposable save. Irrigation and Harbor network
   authorizations should cost 1,000, 2,000, 4,000, 8,000, and 16,000 gold;
   Floodworks and Waterworks should cost 2,000, 4,000, 8,000, 16,000, and
   32,000. Kaido and Tunnels retain their former 2,500/5,000 starting costs.
   Stage I should unlock one local building level. Later buttons require the
   displayed number of effective network levels before raising the cap again.
   All six buttons and the Metropolitan Charter should be collected under
   **Administration > National Great Projects**, with no blank space above the
   National Works Register after the command runs.
6. Confirm Concord Irrigation Works are visible in agricultural locations and
   explicitly supported Japanese lowland provinces even where EU5 shows no
   river, lake, or wetland. Floodworks should be visible on the coast and in
   those lowlands. Both must be JAP-owned domestic buildings.
7. Confirm Seto Harbor Works are initially limited to eligible Japanese coastal
   locations adjoining the Seto Inland Sea. Urban Water Bureaus should appear
   in towns, cities, and megalopolises but never in rural settlements.
8. Run `event kc_debug.36`. Build five levels of each network in an eligible
   test location. Every level should add its listed workers, maintenance demand,
   and one increment of the local modifier. At Level V, verify the full project
   values. Irrigation and Harbor levels should cost 100 gold; Floodworks and
   Water Bureau levels should cost 200. New towns become eligible for Water
   Bureaus but receive no free bonus.
9. Reload and verify building levels, stages, level caps, and the Harbor Chain's
   national Port Proximity modifier survive. Retired province, Harbor-location,
   and automatic Waterworks modifiers must not return.
10. Confirm Irrigation, Kaido, and the Harbor Chain normally unlock at 75, 85,
   and 95 Entrenchment. Floodworks, Tunnels, and Urban Waterworks should remain
   hidden until the Second National Works Register unlocks them after the
   Southern Sea Exchange; debug event 35 supplies that unlock for testing.
11. Confirm the Metropolitan Charter is a separate 10,000-gold action at 100
   Entrenchment, asks for an eligible 400,000-population urban location, and promotes
   only the selected location to a Megalopolis.

### Phase 2 maritime content

- `event kc_debug.44` starts the four-event Tallies of Ningbo chain in rapid
  mode. Every follow-up arrives after one day. It also supplies both Japan and
  the Concord Treasury with test funds.
- `event kc_debug.45` prepares the maritime prerequisites and opens the
  Southern Sea Exchange at zero progress with its normal monthly rate.
- `event kc_debug.46` moves an active Southern Sea Exchange immediately before
  one of its seven thresholds: 20 Firearms, 40 Powder, 55 Silver, 70
  Translation, 76 Southern Islands Survey, 82 Missionaries, or 92 Treaty Port.
  Advance one monthly tick afterward.
- `event kc_debug.47` moves the active Southern Sea Exchange to 99.90 progress.
  Advance one monthly tick to see the final settlement.
- `event kc_debug.48` enables or removes a testing override for the colonial
  nation plus European-contact requirements. Enabling it resets and opens the
  Colonial Survey Registers chain after one day and gives its two follow-ups
  one-day delays. While enabled, Kyoto gains one New World Institution point
  per monthly tick.
- `event kc_debug.49` removes the Phase 2 Great Projects unlock while retaining
  the completed Southern Sea Exchange, then opens the **Second National Works
  Register** after one day.
- `event kc_debug.50` resets the Christian-contact chain and opens it after one
  day. Both follow-ups arrive one day apart, and the player-only conversion
  conclusion is available regardless of earlier Southern Sea precedents.
- `event kc_debug.51` opens a selector for the ten Phase 2 recurring events.
  Use separate reloads when comparing their options and modifiers. The
  governor-ledger choice supplies a temporary debug substitute for its natural
  colonial-nation requirement; ordinary gameplay still requires that subject.
- `event kc_debug.52` resets and rapidly plays the four-event 1582 Great
  Embassy chain, with every follow-up arriving after one day.
- `event kc_debug.53` converts Japan's most populous existing subject into
  either a Concord Commercial Protectorate or a Chartered Extraction
  Commission. It does not create a new country, so use a disposable save with
  at least one Japanese subject. The Extraction Commission option also tests
  its automatic 3 Cohesion creation cost and notification.
- `event kc_debug.54` initializes every Chartered House's concession account
  and grants six additional unused licenses to each House.
- `event kc_debug.55` directly selects Exempt House Charters, Discretionary
  House Service, or Universal House Mobilization without holding a law vote.
- `event kc_debug.56` opens the Taiwanese settlement policy for a fixed western
  province so all three local modifiers can be compared from reloads.
- `event kc_debug.57` opens a selector for the Tondo, Cebu, and Butuan
  commercial compacts and supplies test Treasury funds. The selected local
  country must still exist. Ratification must cost exactly sixty months of
  that partner's current trade-and-tax income, create a Commercial
  Protectorate, transfer matching Japanese holdings, and give Japan the
  remaining exclusive settlement claims for that island group. In natural
  play each compact may open from Japanese Taiwan, Maynila market leadership,
  or a Japanese foothold in its own island group; postponement lasts five
  years rather than permanently refusing the compact.
- `event kc_debug.58` gives Japan a test foothold at Nayoro and opens the
  Northern Colonial Administration charter.
- `event kc_debug.59` opens the Continental War That Never Was council without
  waiting for 1585. Choose the war path to test mobilization and the Korea CB.
- `event kc_debug.60` transfers KOR-owned Korean locations to Japan and opens
  the Korean constitutional settlement. Test each of the three outcomes from
  a reload; the four-commission option intentionally creates four subjects.
- `event kc_debug.61` authorizes and grants both 25-year treaty-coast CBs
  against `CHI`. In separate wars, confirm the special peace term exposes five
  limited sectors at 20 War Score each and creates the matching subject type.
- `event kc_debug.62` opens the six-event overseas-subject consequence
  selector. The first two entries require a Commercial Protectorate, the next
  two require an Extraction Commission, and the final two accept either type.
  Use the charter-review entry to test conversion into a Commercial
  Protectorate without annexation or territorial transfer.
- `event kc_debug.63` tests the Southern Islands Survey. The first option opens
  its three-way ratification and funds the common survey; confirm that Japan
  receives exclusive claims on all four Taiwanese provinces and a thirty-year
  Southern Island Settlement CB against each surviving Ryukyuan tag. The
  second option expires the access immediately and should remove unused
  Taiwanese claims. The third option grants access directly and schedules the
  new authoritative cleanup for the following day, allowing the delayed-event
  path to be verified without advancing thirty years.
- `event kc_debug.64` plays the four Red-Seal Charter events one day apart.
  Test the common, House, and court choices from reloads; every option should
  display its actual modifier, value movement, Treasury cost where applicable,
  and the final twenty-five-year constitutional legacy.
- `event kc_debug.65` opens the adaptive 1609 Ryukyu Settlement for the current
  owner of Urasoe. Use separate saves with Ryukyu independent, subject to JAP,
  and directly owned by JAP. Each state should expose its own three options;
  protectorate outcomes must preserve or recreate local government, while the
  House outcome creates an Extraction Commission and costs 4 Cohesion.

Alpha.48 completes the first overseas governance and continental-expansion
framework. The two custom subjects now reuse stable vanilla assessment prices,
which removes the missing generated price-modifier warnings from earlier
alphas.

Alpha.49 restores the overseas and continental localization file with EU5's
required UTF-8 BOM and guards Philippine, Korean, and treaty-coast area scans
against unowned locations.

Alpha.50 exposes both overseas subject types in Concord Japan's Make Subjects
menu, makes every independently created Extraction Commission cost 3 Cohesion,
and replaces the oversized China settlements with five save-derived coastal
sectors totaling 100 War Score. It also removes the principal peace-tooltip,
Taiwan-scope, and northern-colony script-error sources found in alpha.49.
The peace summary now explicitly says that each demand transfers the designated
treaty ports of its named area, rather than implying that the complete vanilla
area changes hands. Commercial Protectorates and Extraction Commissions also
have distinct generated subject-type icons matching EU5's 128-pixel icon set.

Alpha.51 gives those overseas constitutions recurring political consequences:
harbor investment, legal jurisdiction, quota arrears, charter review, rival
House concessions, and overseas assessments. Regional descriptions recognize
Korean, Chinese treaty-coast, Philippine, and Taiwanese subjects, and an
Extraction Commission can now be reformed into a Commercial Protectorate.

Alpha.52 corrects the custom subject-type checks used by the alpha.51 event
pool and debug selector. EU5 expects bare subject keys in `is_subject_type`,
while subject-changing effects continue to use database-qualified keys.

Alpha.53 removes the 5,000-gold ceiling from the overseas-subject incidents
and evaluates each amount from the selected subject's trade-and-tax income.
It also replaces Japan's global remittance bonuses with temporary Japanese
merchant power in the market containing that subject's capital, and hides the
nested debug-event calls so hovering the selector cannot evaluate an undefined
subject scope.

Alpha.54 adds the Southern Islands Survey and its thirty-year Taiwan/Ryukyu
access, economy-scaled Philippine loyalty compacts with claim transfers, the
four-event Red-Seal Charters, and the adaptive two-event Ryukyu Settlement of
1609. Taiwan's fallback safeguard now lasts until 1610 if the survey never
opens a Japanese route.

Alpha.55 moves the temporary access warrant ahead of CB creation, replaces
variable-dependent claim expiry with a hidden cleanup scheduled exactly 10,950
days later, adds a one-day cleanup debug test, and makes each Philippine price
read directly from Tondo, Cebu, or Butuan so option tooltips never require an
unset saved scope.

Alpha.56 hides internal monthly IO maintenance behind one concise tooltip and
guards Great Project restoration against unset stage variables. This removes
the false monthly list of revoked Irrigation, Floodworks, and Waterworks
modifiers and the associated error flood when hovering a newly created Concord.

Alpha.57 completes the late maritime century. Debug events 66-67 rapidly run
Merchants of Competing Europes and Japanese Overseas Communities. Debug events
68-71 start, shape, advance, complete, and reset Regulation of the Open Seas.

Alpha.60 corrects all parts of the Overseas Communities hover failure. The
fourth event now saves its economy-scaled Treasury subject under the expected
scope, while events one through three schedule their follow-ups only after the
player chooses an option. The shared Treasury values also safely return their
minimum cost when EU5 previews the fourth event before its subject scope exists;
the actual event continues to use the selected subject's trade-and-tax income.

### Late-maritime debug events

- `event kc_debug.66` rapidly runs all four Merchants of Competing Europes
  events. It clears the prior outcome, adds ample Treasury funds, and schedules
  each follow-up after one day.
- `event kc_debug.67` rapidly runs all five Japanese Overseas Communities
  events. Qualifying colonial nations, Commercial Protectorates, and Extraction
  Commissions receive Registered Nihonmachi in their capitals when it ends.
- `event kc_debug.68` starts Regulation of the Open Seas immediately and adds
  ample Treasury funds. It is unavailable while that Situation is already
  active.
- `event kc_debug.69` sets a clear Chartered Ports, Registered Ports, or
  National Administration influence preset while the Situation is active.
- `event kc_debug.70` moves progress to 14.90, 29.90, 44.90, 59.90, 74.90, or
  89.90. Select one article and advance a month to test its event.
- `event kc_debug.71` moves an active Situation to 99.90 for its final monthly
  tick. When no Open-Seas Situation is active, its second option removes a
  completed debug outcome and restores the provisional Council of Licensed
  Ports for another test.
- `event kc_debug.72` prepares the post-maritime Great Project extensions. Its
  first option completes the prerequisites, sets Harbor Stage V, clears both
  authorizations, and funds the Treasury. Its second option authorizes the
  Great Outer Ports and creates thirty test levels across Hakata, Nishisonogi,
  Kagoshima, Tsuruga, Nutari, and Toshima so the Southern Ocean button can be
  tested immediately. Its third option resets both geographic authorizations.
- `event kc_debug.73` performs a one-time exploration backfill for established
  saves. Every Concord member discovers all areas already known to Japan. Keep
  the game paused while this large batch resolves; future successful
  explorations are shared automatically.
- `event kc_debug.74` force-refreshes the hidden Concord concession rights
  granted by Japan and every current Japanese subject to all Chartered Houses.
  It also caches concessions for an already-open vanilla completion event. Use
  it on an older save before transferring a completed colonial province.
- `event kc_debug.75` snapshots every existing House colonial concession and
  immediately retries restoration inside Japan's colonial nations. Run it
  before a vanilla Transfer Province choice and again after the transfer when
  testing an older save.
- `event kc_debug.76` clears every Chartered House's two-year scripted ship
  order cooldown. Advance to the next yearly country pulse to retest paid naval procurement; normal
  money, sailors, shipyard, Senior status, and active maritime-law limits still
  apply.
- `event kc_debug.77` prepares the overseas-investment AI test. It refreshes
  subject construction rights, clears the organization and House construction
  cooldowns, ensures one concession license per AI House, and supplies a modest
  testing reserve. Advance at least one month, then continue for a year: the
  Concord should begin one paid, non-instant House project every three months
  across colonial nations and the two custom overseas subject types.

For the Harbor extensions, confirm that the first authorization admits Hakata,
Nishisonogi, Kagoshima, Tsuruga, Nutari, Toshima, and Kameda. The second must
admit only coastal Japanese locations from Nishimuro through Kashima. Neither
authorization should create buildings during normal play, and both should
survive save/reload. Each button must disappear permanently after use; the
entire late-maritime card should disappear after both are authorized.

Alpha.45 replaces GUI-facing numeric license and embassy checks with safe
state markers, records completed Kaisho ownership directly on each House, and
reserves the shared AI-redemption cooldown before a transfer event is queued.

Alpha.46 sends every charter-redemption notice to the human-controlled country
rather than JAP alone. It also preserves Stage 0 Great Project variables with
a non-visible epsilon because EU5 discards numeric variables set to exact zero.

When testing Ningbo, confirm all four events use the custom Ningbo harbor art,
all references use the current `CHI` country name rather than assuming Ming,
each option lists its real cost and modifier, and every final settlement
automatically researches Licensed Oceanic Convoys.

When testing the Southern Sea Exchange, verify the custom Situation panel,
monthly progress breakdown, milestone rows, and event art. Firearms, Silver,
and Translation must automatically research their matching advancements on
ratification. The missionary article must not change or require Japan's
religion. The treaty-port article must construct exactly one Southern Exchange
Hall at the selected or administratively chosen Japanese coastal location.

After completing the Southern Sea Exchange, confirm the Second National Works
Register appears once and unlocks National Floodworks, Transmontane Tunnels,
and National Urban Waterworks without directly buying a stage. With debug event
48 enabled, confirm the three Colonial Survey Registers events appear, every
option displays its real modifier and value movement, the final event
automatically researches Colonial Survey Registers, and the selected twenty-year
settlement survives save/reload. Disable the override afterward.
