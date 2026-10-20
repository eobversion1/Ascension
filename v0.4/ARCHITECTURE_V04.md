# Extending ASCENSION after v0.4

`game.gd` owns the authoritative ledger, migration, promotion, permanent progress and bounded offline accrual. `activities.gd` schedules paid contracts and negotiation state. `economy.gd` derives sectors, capacity, costs, demand, privileges, discoveries and reserved reinvestment. `content.gd` keeps stable content IDs; `main.gd` and `world_view.gd` present rules without duplicating ledger authority.

Schema 3 adds `economy` and `settings`. Schema-2 migration preserves active quoted orders, outcomes, negotiation rounds, all resources, assets, policies and Legacy, and copies the original file to `.pre-v04.json`. Do not renumber saved IDs. Derived multipliers are calculated, not accumulated in saves. Legacy retains discoveries, achievements and highest rank separately from the current life.

The shared chronological clock splits production at deliveries and two-minute market boundaries. Offline uses the same clock (eight-hour absence cap, 75% effective time). Operations are bounded by three trade slots, finite sector levels and a minimum journey duration. Scientific-number currency bags avoid native-float overflow; native floats remain limited to bounded coefficients/time. Future instant actions need batched accounting rather than unbounded event loops.

## Approved era roadmap — not implemented content

1. Destitution and Survival — working survival and first income.
2. Commerce and Prosperity — working ownership, supply, trade and diplomacy.
3. Wealth and Industry — extend sector investment into technology and logistics.
4. Civic and Political Influence — current institutions and privileges; extend into governance.
5. Sovereignty and Empire — **Sovereign Ruler → Regional Overlord → Continental Unifier → Imperial Founder → Emperor → World Emperor**. Add territory infrastructure, supply and political mandates as a distinct tested layer.
6. Planetary and Stellar Dominion — fleets, routes and research domains.
7. Universal Dominion — intergalactic governance and scoped economic laws.
8. Divine and Metaphysical Power — creation rules, permanent discoveries and ultimately omnipotent creator.

Future modules should use stable IDs, explicit spending/earning transactions, scoped multipliers, shared clock events, versioned migration, a deterministic strategy simulator and actual narrow-screen Android interactions. Implement complete capabilities before adding ranks that promise them.
