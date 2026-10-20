# v0.4 economy and pacing evidence

Godot 4.6.3 runs the actual game rules. Four deterministic policies start at zero, tap exactly fifteen times to buy a stall, then visit every fifteen seconds with up to three asset purchases. Activities are optional. These are efficient scripted strategies, not a prediction of novice human play. Original rank requirements are unchanged.

| Strategy | Scavenger | Vendor | Trader | Guildmaster | Advocate | Leader |
|---|---:|---:|---:|---:|---:|---:|
| economy | 1:00 | 4:15 | 6:45 | 11:45 | 20:00 | 20:30 |
| economy_engaged | 1:00 | 4:00 | 6:15 | 10:15 | 17:15 | 23:15 |
| influence | 1:00 | 4:15 | 6:45 | 10:15 | 16:00 | 20:30 |
| influence_engaged | 1:00 | 4:00 | 6:30 | 10:15 | 15:00 | 19:15 |

All four policies complete the chapter and retain valid balances at 5, 20, 45, 120 and 1,440 minutes. No compulsory activity/resource deadlock appeared in these policies. This does not prove every possible spending strategy is optimal.

At 20 minutes, commercial activity earns about 18.43M lifetime coins versus 3.24M for passive commercial investment, but ends the chapter later (23:15 versus 20:30) because capital and civic resources were committed elsewhere. Civic activity reaches Leader at 19:15 versus 20:30 for passive civic investment. Early Guildmaster arrives between 10:15 and 11:45. Stronger commercial compounding therefore does not automatically dominate civic advancement. Later wealth substantially exceeds chapter gates; a new territory layer is needed before adding higher numerical milestones.

## Actual causal links

- Ownership adds production and capacity; Workshops support stalls, Trading Posts support Workshops, and combined suppliers support commerce. Ten, twenty-five and fifty owned businesses each add a 1.25 sector milestone. Four sector levels each multiply production by 1.30 and contract profit by 1.15.
- Each sector has revenue and a bounded operating-cost fraction. Baseline costs are 25%; supplier/staff upgrades reduce them by four percentage points each, Public Supply by three, with a 10% floor. Costs are withheld from revenue, never withdrawn from savings. A featured sector receives 20% extra demand for two minutes in each six-minute cycle.
- Tools and staffing expand capacity. Existing business upgrades improve their linked contract margins; scaled capital is derived from passive coin income × base journey duration × shipment share. The share is 0.12/0.35/0.70/1.40 for 1/5/20/100 lots. Base contract floors preserve early relevance. Civic rewards also scale against existing civic income.
- Merchant trust improves contract profit. Ratifying Open Passage reduces business/contract capital by 10% and increases profit by 15%; Public Supply improves margins and contract reputation by 25%; City Trading Charter improves sector sales by 15%, contract profit by 20% and shipment access. These require actual trust, rank and payment.
- Production and contracts generate coin and civic resources; negotiations grant trust; ratified rights improve production/investment; integrated investment earns a permanent 1.03 discovery multiplier. Rumour Networks and Campaign Offices remain sustainable reputation/influence sources.
- Manual risky routes trade possible loss for faster, greater coin profit and smaller civic rewards. Assurance protects principal. Delegated routes protect principal and repeat safely; they stop when new quoted capital cannot be paid. Estate Steward reinvests at market boundaries only when it can retain half the wallet, never spending reputation or influence.
- Legacy adds 25% output per point. Each permanent discovery multiplies by 1.03. Achievements, discoveries and highest earned status persist; current businesses, sector levels, privileges and relationships reset.

## Verification and limits

`economy_tests.gd` demonstrates the full owned-business → productive upgrade → capacity → paid contract → negotiation → political privilege → Guildmaster chain. It also tests market tick partition equivalence, huge scientific-number wallets (1e1000), frozen quotes, insurance, safe delegation, reserved stewardship, migration of active orders and permanent Legacy state. Separate rendered UI tests exercise the same controls. Native Android evidence is recorded in VALIDATION_V04.md.

No wallets are converted to native floats for contract scaling. Cost exponents and very large completion balances are tested; the simulation is a lightweight three-sector system, not a population/commodity exchange model. Prices grow exponentially, so payback and cross-holding marginal income are shown for comparisons. Long unattended operations never subtract assets, status or permanent benefits.
