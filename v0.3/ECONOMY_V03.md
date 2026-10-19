# v0.3 economy audit and measured pacing

## The zero-production problem

Independent Trader unlocks the **Rumour Network**, purchased for 1,800 coins with no reputation prerequisite. At that rank its 0.26 base reputation/s becomes 0.286/s from the earned rank benefit: roughly 227 seconds to produce the Guildmaster gate of 65 reputation from zero with one network. Guildmaster requires no influence. Once promoted, a Campaign Office costs 14,000 coins and 75 reputation and produces influence plus reputation. Spending reputation on policies can delay that purchase but cannot remove the network's ongoing income. A single office produces 0.0572 influence/s before other modifiers, about 280 seconds for 16 influence.

The v0.2 issue was discoverability and inert percentage bonuses before a source existed. The UI now identifies the missing source, exposes its purchase near the top of Empire, explains alternatives, and labels locked influence. Market contracts and Assembly negotiations also supply reputation from Vendor onward. There are sustainable, coin-funded paths for every mandatory currency; the activities are optional.

## Investment consequences

First-unit coin payback before bonuses: Street Stall ~47s, Workshop ~92s, Trading Post 150s. Prices grow per owned unit, so the cheapest current button is not a permanent optimum. The UI compares real marginal output under current rank, upgrades and relationship modifiers. Pure reputation/influence purchases have no invented coin exchange rate. Warm Clothes and Route Scouting show additional WORK taps needed to recover cost, distinguishing active play from passive investment.

Contract principal is returned to the wallet, never counted again as lifetime earnings. Capital competes with permanent assets while a route is travelling. Quotes freeze on dispatch; buying a multiplier afterward improves future orders. Larger shipments commit proportionally more capital, while civic rewards scale with the square root of lots. This avoids large coin reserves instantly trivialising political resources.

Safe routes guarantee quoted profit and full civic credit. Shortcuts take 80% of the time, offer double coin profit, but award half civic credit even on success. Failure returns only 85% of capital and no rewards. Failure probability starts at 25% and falls toward 10% with merchant trust. Thus shortcuts maximise expected coin return while safe routes favour dependable reputation/influence progress. A fixed-seed 500-caravan sample observed 139 failures (27.8%) and a mean net 573.12 coins versus the analytic expectation of 600; samples are not a guarantee. The safe alternative yields 420 coins over 120 seconds. Evidence: `risk-audit.json`.

Negotiations have three rounds and visible motives. Free listening can achieve a cordial 25% reward but cannot build trust by itself. A well-timed funded concession and bargain can secure an accord; repeated pressure can fail outright. Merchant trust improves coins and trade profits, Assembly trust improves reputation, and Council trust improves influence. Trust caps at five per faction per life. Delegate cooldowns and paid concessions prevent unlimited free reward tapping. Exclusive v0.2 policies continue to trade commercial against civic output.

The Trade Clerk is a capability unlock rather than a cosmetic multiplier. Reinvestment is per-route, opt-in and paid. It uses chronological settlement, operates within the offline cap, and stops when capital is insufficient; it cannot borrow.

## Actual-engine simulation

Each policy starts from zero, uses 15 initial WORK taps and visits every 15 seconds. Permanent investment choices compare marginal production against weighted resource costs. Economy and civic policies take opposing exclusive choices. Engaged variants also negotiate, reserve half their wallet when launching safe trades, and buy a clerk when affordable. No currency or ranks are injected into these simulations. Later Android fixtures are separately labelled.

| Policy | First promotion | Guildmaster | Civic Leader | Deliveries by 20m | Negotiations by 20m |
|---|---:|---:|---:|---:|---:|
| economy | 60s | 12m15s | 20m15s | 0 | 0 |
| economy_engaged | 60s | 10m45s | 19m00s | 8 | 9 |
| influence | 60s | 12m45s | 38m00s | 0 | 0 |
| influence_engaged | 60s | 12m45s | 34m15s | 3 | 9 |

All four policies reach all seven ranks and retain valid finite balances at 5, 20, 45, 120 and 1,440 minutes. Existing rank requirements were retained. The engaged commercial policy takes 19m versus 20m15s without activities; civic play takes 34m15s versus 38m. These heuristic policies establish viable alternatives, not optimality or human completion-time predictions. Actual first-time players also spend time reading, comparing and exploring. Activities improve the opening without becoming mandatory gates.

Evidence lives in `tests/results/v03/balance.json`. Use `./tools/godot.sh --headless --path . --script res://tests/balance_v03.gd` to reproduce.
