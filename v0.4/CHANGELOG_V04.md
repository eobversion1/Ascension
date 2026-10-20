# ASCENSION v0.4 — The Living Economy

Built on the existing v0.3 Godot project; seven complete ranks and original promotion requirements remain.

- Three connected sectors: Workshops improve stalls, Trading Posts improve Workshops, and suppliers improve trading. Owned-business milestones, sector investment and existing upgrades compound actual production.
- Revenue, operating expense and net profit are explicit. Positive demand rotates every two minutes; ordinary operations never debit savings or destroy assets.
- Contract capital and rewards scale with productive income, capacity and shipment size. Tools, sector development, institutions and privileges affect real opportunities. Quotes freeze at dispatch; stale displayed terms cannot silently charge a different price.
- Merchant, public and council agreements unlock three ratified privileges with real investment discounts, lower costs, stronger contracts and expanded access.
- Coordinated Supply, Merchant Assurance and Estate Steward add production integration, voluntary risk protection and reserved automatic reinvestment. Delegated trade protects principal and repeats safe routes.
- Seven permanent discoveries multiply production by 1.03 each. Legacy preserves discoveries, achievements, highest earned status and preferences while resetting current-life assets and relationships.
- Original four-era illustrated district, contextual building controls, ownership-linked supply animations, compact business statements, sector management and an interactive advancement timeline. Reduced-motion setting, two-column shipment controls and linked incomplete requirements.
- Schema-2 saves migrate to schema 3 with a pre-v0.4 backup; package identity and debug signing remain compatible. No permissions, services, ads or accounts added.

## Defects corrected during validation

The first reduced-motion implementation was re-enabled by Godot when the world control entered the tree. Applying the preference in `_ready()` now stops animation processing, verified by rendered input tests. Stale contract quotes now reject a tap after economic terms change. Four shipment-size choices use a wrapping two-column grid on narrow screens.

The earlier promotion defect remains repaired: the original header merely navigated to the Ascend page; it did not promote. The current header executes the shared, guarded promotion transaction and saves before reporting success. Requirements were not reduced to conceal this defect.

## Scope and future priorities

The playable chapter still ends at Civic Leader with repeatable Legacy. Sovereignty, space and divine gameplay are roadmap items. Add a distinct territory/governance chapter next, followed by human pacing studies, audio and physical-device performance/accessibility validation. Current demand is deterministic and beneficial, rather than a competitive price market. Illustrations are static original generated art with lightweight supply animations, not a navigable world.

A further regression caught a timing difference when the third trade unlocked a permanent discovery during a long offline update. Discoveries now apply at each delivery boundary before quoting the next automatic order; online and offline results match.

Actual Android interaction found that a faction link could reopen Ventures at the old long-list offset. The explicit link now overrides deferred tab-scroll restoration; a regression verifies the target is visible before any helper scroll. Default upgrade ordering now follows rank, and mixed-currency upgrade comparisons use accurate wording.
