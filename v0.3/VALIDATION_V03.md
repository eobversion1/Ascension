# ASCENSION v0.3 validation — 2026-10-19

## Earlier promotion repair retained

The original prominent ASCEND control only selected the Ascension page; it never called promotion. Eligibility was already satisfied in the reported 2,350-coin/20-stall save. The v0.2 repair made the header promote directly, unified the displayed gate with eligibility, guarded stale/repeated taps and persisted promotion before showing success. Version 0.3 retains that repair and the original rank requirements. Dismissing the new ascension scene additionally returns to the top of Empire, revealing newly unlocked income guides.

## Automated checks

- Godot **4.6.3 stable** imports/compiles the existing project and exports Android successfully.
- **153 core economy/save assertions** pass, including original promotion guards, all generators/upgrades/policies, numerical limits, save recovery and Legacy.
- **161 activity/migration assertions** pass: paid dispatch, gates/capacity, frozen outcomes, principal accounting, losses, real deliveries, optional repeated paid orders, no debt, pause, negotiation rounds/failure/cordial/accord outcomes, trust caps, faction rewards, schema-1 migration, active-state JSON round trips, offline settlement and duplicate-award prevention.
- **942 existing rendered UI checks** and **297 activity UI checks** pass. These inject actual Godot pointer/touch-emulated input and use explicit capital/rank/time fixtures. Activity checks purchase through the resource guide, generate reputation, fund influence, complete negotiations, operate the clerk, filter/sort upgrades, collapse the header and verify narrow/short/tall layouts and ascension cards.
- Four actual-engine progression policies complete all ranks and keep valid balances through a simulated day. See ECONOMY_V03.md and `tests/results/v03/balance.json`.
- A fixed-seed 500-trip risk sample exercises the actual contract engine; detailed counts and expected value are in `risk-audit.json`.

The rendered UI checks also cover failed promotion attempts, stale promotion callbacks, narrow celebration bounds and the post-ascension return to the new district.

The first activity save/reload regression caught JSON numeric-type handling in shipment-size validation. The implementation was corrected and the complete activity suite then passed. There are no suppressed/expected failures in the listed passing suites.

## Android interaction evidence

Android 15/API 35 x86_64 emulator; software ANGLE/SwiftShader rendering, no KVM. APK version 0.3.0/code 3 installs over the existing v0.2 app using the same package and certificate. The original native save was backed up before installation. Native schema-1 migration preserved earned Street Scavenger rank and Legacy, and created a pre-v0.3 backup.

The application reaches the full rendered game screen with the new world art and compact interface. A cached-shader warning triggered recompilation during the slow software-emulator cold start; startup completed. Native screenshots and per-step persisted-state evidence live in `tests/results/android-v03`.

The initial migration, salvage, stall and Vendor checks used the preceding v0.3 candidate. The final APK adds the post-ascension return to Empire, was installed during the negotiation, and ran the remaining negotiation, restart, Guildmaster/resource path, clerk, offline, Legacy and layout checks.

Completed native interactions (the evidence JSON and screenshots are in `tests/results/android-v03`):

- From the migrated earned save: dispatch and actual timed salvage delivery, permanent stall purchases, promotion to Street Vendor, and a mixed three-round Merchant League negotiation. The paid first round survives an in-place final-APK update and a process restart; the completed accord grants reputation and merchant trust.
- From a clearly marked Independent Trader fixture: purchase a Rumour Network with coins, observe positive ongoing reputation, dispatch a five-lot relief contract, receive its real rewards, and promote to Guildmaster. No reputation or influence is injected during this path. The initial rank, capital and enterprises are fixture data, so this is not claimed as a fresh native full-chapter run.
- After that promotion: Continue returns to the top of the new citadel district and exposes the Campaign Office guide. Purchasing the office starts real influence production.
- Native upgrade purchase, Available/All filtering, all the way to the final upgrade cards, and navigation among all five bottom destinations. Dragging through trade and upgrade lists does not make unintended purchases.

- Trade Clerk purchased through the native upgrade card; auto-repeat enabled by touch; two real subsequent salvage deliveries and paid reinvestment confirmed in saved state.
- Marked offline fixture: one opted-in salvage route, a clerk, no passive generators and a 24-hour-old timestamp. Native catch-up settles exactly **720 deliveries**, **8,640 profit** and **18,622 wallet coins** after the committed principal. A second resume does not grant the cap again. This verifies the eight-hour × 75% effective-time limit and shared paid-repeat clock on Android.

- Marked Civic Leader fixture with two Legacy points, an active delegation and an unfinished negotiation: the native confirmation button begins a new life at rank zero with **three Legacy points**, zero wallet and cleared shipments, negotiation and faction trust. The original earned save was then restored and verified at Street Vendor with its earned merchant trust and unchanged Legacy. Destructive fixture progress was not left in the normal test save.

Native captures at 360×800 and 420×1000 show readable resource rows, accessible repeat controls and unobscured bottom navigation. These are emulator viewport tests, not hardware-cutout certification.

One cold-start run produced an Android input-timeout dialog: “Application does not have a focused window.” The fully software-emulated device took over a minute to initialise, and the test had sent input during startup. A clean restart reached the rendered interface and subsequent interaction checks continued. This timeout is retained in the evidence; the build is not represented as having a flawless emulator launch history. No GDScript exception or application crash was found in the captured Godot/AndroidRuntime logs. Real-phone startup and performance still need validation.

## APK

Package `org.ascensiongame.chapterone`; Android 7/API 24+, target API 36; ARM64, ARMv7, x86_64. No Android permissions. Debug signing v2/v3 and 16 KiB ZIP alignment verified. The installed emulator APK was hashed and matches this exported file byte-for-byte. SHA-256:

`8f9ae9165fe16ed82e1a1069e12198232ba22a96aeb1ced08290107d314934e0`

## Boundaries

No physical phone has been tested. Frame rate, battery use, low-memory eviction, OEM-specific lifecycle behavior, screen-reader accessibility and hardware cutouts remain unverified. Software-emulator delays are not a phone-performance benchmark. Gameplay uses local device time within the offline cap. Later global/galactic/universal/divine eras and sound remain future work; the current complete chapter ends at Civic Leader with repeatable Legacy.
