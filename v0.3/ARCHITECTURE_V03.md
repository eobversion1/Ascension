# Extending ASCENSION after v0.3

The working chapter remains seven ranks through Civic Leader. The long journey is Survival → Commerce → Political Power → Global Dominion → Galactic Empire → Universal Dominion → Divine Ascension → Omnipotence. These later eras are an architectural roadmap, not empty playable ranks.

## Existing boundaries

- `content.gd`: stable IDs for resources, ranks, generators, upgrades, exclusive policies and rank benefits. Append real, complete content here; never renumber saved content IDs.
- `game.gd`: the authoritative resource ledger, modifiers, progression checks, saving, migration, pause and bounded offline time. Scientific-number bags remain the currency representation.
- `activities.gd`: complete trade and negotiation rules and JSON-safe activity state. Presentation never grants resources. Transactions use the same payment/earnings ledger as enterprises.
- `main.gd`: portrait presentation, one scroll surface, action feedback and lifecycle wiring. Deferred button callbacks finish input dispatch before replacing controls.

A trade quote stores capital, profit, civic rewards, duration and its sampled risk result at dispatch. Delivery returns principal directly to the wallet; only profit enters lifetime earnings. Automatic repeats pay again and stop without debt if funds are missing. Active orders and negotiation rounds use persistent serials to reject stale UI actions. Offline progress enters the same chronological activity clock as active play, with the eight-hour/75% cap. There is no separate duplicate reward path.

Save schema 2 adds the activities namespace. Migration from schema 1 retains existing resources, rank, assets, policies and Legacy and creates a `.pre-v03.json` file before overwrite. Future versions are preserved and blocked, not guessed at. Every future resource/module addition needs its own migration and round-trip tests.

## Future complete layers

| Era | A genuinely new playable layer | Reuse and extension |
|---|---|---|
| Global Dominion | Territory supply, infrastructure and competing political mandates | Add territory module with stable region IDs; spend ledger resources, schedule construction on the shared clock |
| Galactic Empire | Fleet logistics, exploration and technology choices | Add technology graph and route capacity; use scientific-number costs and explicit maintenance budgets |
| Universal Dominion | Cross-galaxy governance and laws with systemic trade-offs | Add policy scopes and production domains instead of multiplying every resource identically |
| Divine Ascension | Creation rules and prestige that alter how systems interact | Add a versioned meta-progression ledger distinct from chapter relationships and enterprises |
| Omnipotence | Player-authored worlds and constraints | Compose proven modules; define meaningful objectives beyond a final currency threshold |

Each layer should ship with an independent simulation policy, meaningful choices, save migration, offline bounds, a narrow-screen interaction test and a complete Android path. Do not create dozens of ranks until there is gameplay for them. Avoid routing giant currencies through native floats: the current bounded contract catalogue uses small numeric coefficients and converts to scientific-number bags; future astronomical contract definitions should use those bags directly. Avoid storing derived production modifiers, which would duplicate bonuses across migrations.

Trade Clerk is the first explicit automation capability, not an unused multiplier. Later automation should be opt-in, explain reserves and opportunity costs, and have finite work per offline update. Current offers have minimum 24-second journeys, three slots and an eight-hour offline cap, keeping catch-up bounded. Future instant actions require aggregation rather than unbounded event loops.
