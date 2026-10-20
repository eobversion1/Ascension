# ASCENSION v0.4 validation — 2026-10-19–20

## Engine and automated verification

Godot 4.6.3 stable imports and compiles the retained project. Android export, signature v2/v3 verification, 16 KiB alignment and manifest inspection succeed. Package identity remains `org.ascensiongame.chapterone`, version 0.4.0/code 4, minimum API 24, target API 36, ARMv7/ARM64/x86_64. No Android permissions.

Passing engine suites: 165 core economy/save assertions, 161 activity/migration assertions, and 93 new interconnected-economy assertions. New checks cover actual business→upgrade→contract→trust→privilege→promotion effects, no-debt automation, frozen/stale quotes, cost accounting, market tick equivalence, huge scientific balances, active-order v0.3 migration with untouched backup, and hybrid Legacy persistence. A newly discovered offline timing discrepancy was corrected: permanent trade discoveries apply at delivery boundaries before automatic requoting.

Passing rendered suites: **1,078 general UI checks**, **289 activity UI checks**, and **447 living-economy UI checks** (including actual 100-lot dispatch at 360×640). Together with engine assertions: **2,233 checks**.

Rendered Godot input suites are separate from Android testing. They use actual pointer events with explicit rank/capital/time fixtures to test controls, scrolling, held/stale actions, all promotion gates, small layouts, purchases, diplomacy, charter ratification, sector investment, automation and reduced motion. The initial reduced-motion failure was fixed in world-control initialization; no expected failures are suppressed.

Four actual-engine strategy simulations run for a full simulated day with checkpoints at 5, 20, 45, 120 and 1,440 minutes. Results and methodology are in ECONOMY_V04.md and `tests/results/v04/balance.json`. They establish reachable progression under multiple policies, not guaranteed novice play times or optimality of every possible strategy.

## Android interaction record

Android 15/API 35 x86_64 emulator, software ANGLE/SwiftShader and no KVM. Existing native save backed up before update. Migration retained Street Vendor, three stalls, Warm Clothes, earned merchant trust and zero Legacy, and wrote `.pre-v04.json`. The illustrated game window rendered successfully. A shader-cache warning caused recompilation; this is retained in the log.

Native interactions before the navigation correction purchased two Workshops, promoted the migrated earned save to Independent Trader, opened management from the district, expanded the retail sector, bought Better Location after payback sorting, scrolled to the bottom of the contract catalogue, dispatched a paid five-lot relief shipment and received its real rewards. A three-round Assembly accord earned additional reputation and trust. These used no injected resources or ranks. The corrected final APK retains this progress and is used for the remaining tests below. Native screenshots and persisted-state checkpoints are under `tests/results/android-v04`. Rendered desktop input tests are under `tests/results/v04`; they are not represented as Android touches.

Native interaction caught a genuine scroll-restoration defect: linking from Council into a faction could leave that faction above the visible region because the old Ventures scroll offset was restored two frames later. This was corrected and a visibility regression added; the rendered helper had previously auto-scrolled to the named control and therefore concealed this behavior. The corrected APK is rebuilt and the actual cross-screen link is retested on Android.

On the corrected final APK, the Merchant League link was retested after a long-scrolled Ventures screen: the intended faction and negotiation control were visible immediately. Three actual paid concession rounds raised merchant trust to two. Native ratification of Open Passage succeeded and earned the Integration discovery, connecting ownership and sector investment to diplomacy and permanent compounding.

Further corrected-build touches followed the reputation requirement to a Rumour Network purchase (positive reputation production), followed the Trading Post requirement to two real purchases, and promoted to Guildmaster. Promotion used lifetime reputation after spending on the privilege; rank requirements were unchanged. The native OCR driver required retries when a control was missed; the successful persisted-state assertions were retained rather than relaxing expected outcomes.

The final-build Campaign Office purchase produced positive influence on Android. Background/resume preserved Guildmaster, purchased institutions and Open Passage; the earned save was backed up before any late-chapter or offline fixture was injected.

The marked offline fixture has one opted-in salvage route, a Trade Clerk, no passive generators and a timestamp 24 hours old. Android settled exactly **720 deliveries**, **9,954.43775881096 profit** and **19,936.4377588108 wallet coins**, matching a separately generated actual-engine oracle. This includes the third-delivery discovery and rotating demand. It verifies the eight-hour absence cap × 75% effective time, paid reinvestment and principal accounting; the fixture is not represented as naturally earned player progress.

A second native resume did not award the offline cap again. Active repeated orders persisted and continued to pay fresh capital.

The late-chapter fixture enabled Estate Steward through touch. On a later market boundary, retail development rose from 0 to 1 while craft remained 1; reputation continued increasing. Native 360×800 and 420×1000 captures show the district and navigation fitting their viewports. Twelve upward swipes reached Institutional Reform, the final upgrade card, with no change to purchased upgrades. Reduced motion was enabled through Settings before prestige.

The actual Legacy confirmation completed on Android: rank reset to Homeless Beggar, Legacy rose from 2 to 3, six permanent discoveries and seven achievements persisted, highest earned rank remained Civic Leader, and reduced motion stayed enabled. Current privileges, sector development, relationships and the unfinished negotiation reset. This is explicitly a late-chapter QA fixture, not a claim that this chapter was naturally earned on the emulator. Active-order reset is covered by engine tests; the fixture shipment may have completed during layout testing.

The final first-promotion touch check worked from the post-Legacy fixture: fifteen WORK taps, a paid first Street Stall, then the enabled header promoted Homeless Beggar to Street Scavenger. This used Legacy 3 bonuses and is not presented as a fresh Legacy-0 timing test. Original eligibility gates were unchanged.

The earned Guildmaster save (Legacy 0, retained assets and Open Passage) was restored after all fixtures. Final APK SHA-256: `426fdc197c8c2ac57b41eb0cd2e6d9459ff8051085ba1737c5fddc2cfd953198`. The installed APK was pulled from the emulator and matched this hash.

Final bounded runtime/event-log requests returned no entries; this is a limited log capture, not proof that no Android fault could occur. The successful launch, rendered screenshots, persisted-state checkpoints and interaction results are the primary native evidence. The earlier captured startup shader-cache warning was nonfatal.

## Known boundaries

No physical phone has been tested. ARM hardware performance, battery drain, OEM lifecycle behavior, hardware cutouts, low-memory recovery and screen-reader accessibility remain unverified. The software emulator is not a physical-device performance benchmark. The chapter remains seven ranks through Civic Leader with repeatable Legacy; future eras are clearly marked roadmap items. No audio system was added. Local device time is trusted within the offline cap.
