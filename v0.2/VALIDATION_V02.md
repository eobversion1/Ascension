# ASCENSION v0.2 validation — 2026-10-18

## Promotion defect and repair

Reproduced the reported state in the existing game: rank 0, 2,350 lifetime coins, 20 Street Stalls. Eligibility returned true and progress was 100%, but pressing the prominent ASCEND control left rank 0 and selected tab 3. Its original callback was `_select_tab.bind(3)`: it navigated to Ascension instead of invoking promotion. The actual promotion button was buried lower in that page. The engine gate itself was correct.

The header now invokes promotion directly when eligible, otherwise opens the shared requirements view. Expected-rank checks and a busy celebration guard reject stale/repeated events. Promotion is saved before success is shown; a failed save rolls the state back. The same conditions drive eligibility, visible requirements and progress. Incomplete progress is capped at 99%. Rank requirements and original prices have not been reduced.

## Automated evidence

Godot 4.6.3 stable, matching Android templates.

- Engine: **147 assertions passed**, including exact reported state, successful/unsuccessful gates, stale double attempts, unlocks, save/reload, migration backup, offline caps and Legacy persistence failure rollback.
- Rendered UI: **644 checks passed**, real pointer input and touch-emulated drag at 420×820, 360×800, 360×640 and 420×1000; purchases, rank transitions, duplicate guard, save failures, decisions, modal layout, scroll/tab restoration, lifecycle and confirmation touch sizes. Advanced ranks use explicit fixture states.
- Actual GDScript balance simulation from zero, 15 initial WORK taps, investment visits every 15 seconds: economy policy finishes at **20m15s**, influence policy at **38m**. Both reach all seven ranks, remain finite through 1,440 minutes and encounter no mandatory deadlock. This is deterministic simulation, not a human completion-time claim.

## Android evidence

Android 15/API 35 x86_64 emulator, software ANGLE rendering, no KVM. The v0.2 APK installs over v0.1 using the same package and signing certificate. Native screenshots and saved-state evidence are in `tests/results/android-v02`.

Native input has verified launch to the complete game interface, WORK, Street Stall purchase and passive earnings, first promotion from ordinary fresh play, ineligible promotion, the reported rich save, duplicate taps, a subsequent Street Vendor promotion, an upgrade purchase, tab navigation and later-rank promotions through Civic Advocate. Later-rank checks use explicitly injected test saves on an emulator only. No fixture tool targets a physical phone.

Further native checks passed: two paid strategic decisions, promotion to Civic Leader, skippable reward overlays, confirmed Legacy reset (rank 0, one Legacy point, no enterprises/decisions), and an eight-hour-capped offline award of approximately 6,927 coins from a one-stall/day-old fixture. Native screenshots at **360×800** and **420×1000** show accessible navigation and resource/action controls. Long decision-menu touch scrolling reached lower cards and left fixed navigation usable.

A native log inspection found two nonfatal Godot `can_process` errors while page controls were removed during input dispatch. Button callbacks now run deferred, after input dispatch. The complete rendered regression suite passed again after this correction: 644 checks, zero failures. The exact final APK was then reinstalled and cold-launched: earned Street Scavenger rank and the purchased stall persisted, the complete screen rendered, a Warm Clothes upgrade saved, and dragging from the upgrade area scrolled without purchasing Route Scouting. The captured final app log has setup/interface-ready messages and no Godot errors, script errors or AndroidRuntime fatal. Native earlier-rank/Legacy/offline scenarios were run before this final input-dispatch-only correction; the complete engine/UI suites cover the final logic. The crash buffer contains earlier Android Bluetooth-stack crashes, not an ASCENSION fatal; emulator performance and system reliability remain limitations.

## Build and compatibility

`org.ascensiongame.chapterone`, **0.2.0 / code 2**, minimum API 24, target API 36; ARM64, ARMv7 and x86_64. No permissions. Signature v2/v3 and ZIP alignment for 16 KiB pages pass. SHA-256:

`a62c87155134d4dd2575be717c832e59fee2907438773cdbb67b7f6ec5404037`

Save schema remains 1. Existing resources, assets, decisions, rank and Legacy are retained; a one-time `.pre-v02.json` backup is made before migrating older application saves. Existing source and native saves were backed up before development and fixture testing.

## Screenshots

Native captures include `03-stall-purchased.png`, `08-vendor-ascension.png`, `20-decisions-scrolled.png`, `21-civic-leader-ascension.png`, `22-legacy-confirmation.png`, `23-legacy-new-life.png`, `24-offline-rewards.png`, `25-narrow-360x800.png`, `26-tall-420x1000.png`, `27-final-apk-restart.png` and `29-final-upgrades-scroll.png`. All are Android screencaps, not mockups.

## Not established

No physical Android phone has been tested. Frame rate, battery, memory pressure, OEM process eviction, notched-device safe areas and all Android versions remain unverified. The software emulator has slow cold starts and previously had OS/launcher failures; this is not representative phone-performance evidence. Future imperial/cosmic eras and sound are not implemented.
