# ASCENSION 0.2.0

- Fixed the prominent ASCEND action: it now promotes directly when eligible. Previously it only navigated to the Ascension tab; the actual promotion button was farther down that page.
- Unified displayed conditions, eligibility and progress. Incomplete gates cannot round to 100%. Original rank thresholds are unchanged.
- Added stale-rank and modal guards against duplicate promotions, immediate persistence, and rollback if saving fails.
- Added cumulative rank benefits, narrative celebrations, unlock summaries and the next milestone. Celebrations can be dismissed immediately.
- Rebuilt the existing portrait interface with original atmospheric vector artwork, bundled licensed serif/body fonts, compact collapsible resources, bottom navigation, layered cards and clear acquired/locked states.
- One main scrolling area per page; touch events pass through child controls, drags cancel clicks, and tab scroll positions are restored after layout.
- Added manual-work and generator payback comparisons. Existing exclusive strategic choices remain consequential.
- Settings now contains Pause, checkpoint save and confirmed destructive Reset. Autosave status is visible without permanent gameplay utility buttons.
- Preserved save schema 1, existing progress and Legacy. Old saves receive a one-time pre-v0.2 backup before migration. The APK uses the existing package and debug signing certificate.
- Deferred button callbacks until input dispatch completes, avoiding removal of the active control during Android touch processing.
- Sized native confirmation actions to at least 48 logical pixels; corrected responsive celebration layout.

## Scope and limitations

Seven ranks through Civic Leader and repeatable Legacy are playable. Later imperial/cosmic/divine eras, audio and physical-device performance validation remain outstanding. Android emulator tests use software graphics and do not establish phone frame rate, battery use or OEM process-eviction behavior. See VALIDATION_V02.md for evidence and test-fixture boundaries.
