===== BEGIN PRO: PRICING =====
Load when: you must set or defend an actual *number* — run a Van Westendorp or Gabor-Granger study, read a revenue-maximizing price off a curve, compose Good/Better/Best tiers, design price fences, price an outcome/AI feature against a cost envelope, or model whether a new tier expands or just relocates revenue. The base §Pricing names these tools; this module runs them. All numbers below are **illustrative**; all rules of thumb are **directional / point-in-time — re-test on your own data.**

Spine (don't skip the order): **EVC sets the ceiling → Van Westendorp finds the acceptable band → Gabor-Granger finds the revenue-max point inside that band → tier architecture + fences capture it → cohort model confirms it's incremental.** Value-based, never cost-plus (Ramanujam, *Monetizing Innovation* 2016; Campbell, ProfitWell/Paddle). Price is discovered from the customer, not derived from your costs.

## 1. EVC — the value ceiling (Nagle & Holden, *Strategy & Tactics of Pricing*)
`EVC = price of next-best alternative + monetized value of your differentiation − switching cost.` This is the ceiling WTP *can* reach; it is not the price. Capture ~10–25% of the *quantified differentiation value* (directional) — leave the rest as the customer's surplus or you kill adoption.
- **Fill-in:** alternative $____ + differentiation $____ (quantify in the customer's unit: hours saved × loaded rate, error cost avoided, revenue unlocked) − switching $____ = **EVC $____/period.**
- Judgment: a large EVC–WTP gap means *communication* is your lever (the value isn't believed), not the number. Sell the differentiation before you raise the price.

## 2. Van Westendorp PSM — the acceptable band (Peter van Westendorp, 1976)
Survey the *target segment only* (≥~?100 responses, directional). Four questions, asked about your specific product:
1. **Too cheap** — at what price so low you'd doubt the quality?
2. **Cheap / a bargain** — at what price is it a good deal?
3. **Expensive** — at what price does it start to feel expensive but you'd still consider it?
4. **Too expensive** — at what price is it so high you'd never consider it?
Plot cumulative curves (too-cheap and cheap descending; expensive and too-expensive ascending). Read the **four intersections**:
| Point | Intersection of | Reads as |
|---|---|---|
| **PMC** Point of Marginal Cheapness | too-cheap × expensive | floor — below this, quality doubt costs you sales |
| **OPP** Optimal Price Point | too-cheap × too-expensive | price where resistance is balanced/minimized |
| **IPP** Indifference Price Point | cheap × expensive | the "normal/expected" price; median WTP; where a market leader often sits |
| **PME** Point of Marginal Expensiveness | cheap × too-expensive | ceiling — above this, too-expensive dominates |
**Range of Acceptable Pricing = PMC → PME.** OPP and IPP sit inside it.
- Read the *distribution*, not the average — a bimodal too-expensive curve = two segments hiding in one survey; split and tier to each.
- Limitation (say it out loud): PSM measures *stated* price perception, not purchase intent or volume — it bounds the band, it does **not** pick the price. That's Gabor-Granger's job. Never ship a price on PSM alone.

## 3. Gabor-Granger — demand & the revenue-max price (André Gabor & Clive Granger)
Inside the PSM band, test **discrete price points**: "at $X, how likely are you to buy?" (binary, or top-2-box of a Likert) across 4–6 prices. Build the demand curve = % accepting at each price, then:
`Revenue index(P) = P × acceptance(P).` The price that **maximizes the revenue index is your revenue-max price** (assuming ~zero marginal cost; for high-COGS or AI features, maximize `P × accept × margin%` instead — see §7).
- Gabor-Granger gives revenue-max and the demand elasticity; it does **not** test packaging or feature trade-offs.
- Bias watch: respondents over-accept hypothetical prices — discount stated acceptance, and validate the top candidate with a real fake-door/checkout test before locking.

## 4. Conjoint / MaxDiff — *what goes in which tier* (Green & Rao conjoint; Louviere MaxDiff)
PSM/G-G price the *whole product*; conjoint prices the *parts* so you can compose tiers.
- **Choice-based conjoint (CBC):** show bundles (features × price), force trade-off choices, estimate **part-worth utility** per feature and the **WTP for each attribute** (utility ÷ price-coefficient). Use it to decide which features are tier-movers vs. table stakes, and to simulate share/revenue under a proposed Good/Better/Best lineup.
- **MaxDiff** (best–worst scaling): cheaper, no price; ranks features by relative importance when you only need "what do they value most?" to slot Leaders vs Fillers (base §Pricing). Use MaxDiff to *triage the feature list*, conjoint to *price the bundle*.
- Map outputs to Ramanujam's **Leaders / Fillers / Killers:** high WTP + tier-mover = Leader (lead the tier, charge for it); low WTP = Filler; *negative* part-worth or "expected free" = Killer — never bundle a Killer with a Leader.

## 5. WORKED EXAMPLE — EVC → PSM → Gabor-Granger → defended price (all numbers illustrative)
B2B analytics product, new "**Pro**" tier, target = mid-market data teams.
- **EVC:** next-best tool $200/mo + differentiation (saves an analyst ~5 hrs/mo × $60/hr loaded = $300/mo) − switching cost ~$50/mo = **EVC ceiling ≈ $450/mo.** Capturing 25% of the $300 differentiation ≈ $75 premium over the alternative → value-based floor of intent ~$275; ceiling $450. Headroom exists; WTP, not value, will bind.
- **PSM (n≈?150):** PMC $120 · OPP $180 · IPP $210 · PME $320. **Acceptable band $120–$320**, optimal ~$180.
- **Gabor-Granger** across $150/$200/$250/$300: accept 70% / 55% / 38% / 22%. Revenue index = 105 / **110** / 95 / 66 → **revenue-max ≈ $200/mo.**
- **Reconcile:** EVC ceiling $450 (lots of room — we are *not* over-charging on value), PSM optimal $180 / ceiling $320, G-G revenue-max $200. The three agree on a ~$180–$220 zone. **Defended list price: $199/mo** — sits at the G-G revenue peak, just above PSM OPP (resistance-minimized), far under the EVC ceiling (so there's expansion headroom and a credible value story for sales). **Defense in one line:** "Revenue-max on the demand curve, inside the acceptable band, with 2× EVC headroom for upsell." Annual: **$2,000/yr** (round, ~16% off — see signals below).

## 6. Tier architecture — Good / Better / Best
- **Inter-tier ratio ~1 : 2.5–3 : 5** (directional). With Better = $199 → Good ≈ $79 (the "1"), Best ≈ $399–$499 — the 5× top tracks the ratio ($79 × 5 ≈ $395, rounded up to a charm/anchor point). Want a higher Best ($499–$599)? Fine — but that's *stretching above 5×* as a deliberate price anchor, so call it that (read the guidance as ~1 : 2.5–3 : 5–6); don't present $499–$599 as a clean derivation from a 5× ratio, because it isn't.
- **Anchoring:** the high Best tier makes Better look reasonable — list Best first/leftmost or most-prominent so it sets the reference. **Center-stage:** make **Better** the visually highlighted "most popular" — most buyers pick the middle when one is framed as default. **Decoy (asymmetric dominance):** a tier that is clearly dominated by Better (slightly worse, nearly same price) pushes choice toward Better; use sparingly and never deceptively.
- **Round vs charm signals (directional):** charm ($199, $49) signals *value/deal* — fits self-serve, monthly, prosumer, B2C. Round ($200, $2,000, $50k) signals *quality/trust/premium* — fits B2B annual, enterprise, sales-led. Match the signal to the buyer: $199/mo self-serve list, $2,000/yr round for the committed annual buyer.
- Each tier needs a **value metric** (Campbell) — the unit that scales with delivered value (seats, events, GB, resolved tasks). The bill should grow as the customer succeeds.

## 7. Price fences — let segments self-sort without arbitrage (taxonomy)
A fence is a rule that keeps a low-WTP buyer from taking the high-WTP price. Three families:
| Fence type | Mechanism | Examples | Watch-out |
|---|---|---|---|
| **Feature / product** | capability gating | advanced analytics, SSO/SAML, API limits, SLA, audit logs | gate SSO behind premium **only when moving up-market** — "SSO is table stakes" is survivorship bias (base §Pricing) |
| **Usage / metric** | quantity of the value metric | seats, events, rows, storage, calls, environments | the metric must be one the buyer already equates with "more value," and hard to game/under-report |
| **Segment / identity** | who or how they buy | student/nonprofit/region/PPP, channel, commitment term (annual vs monthly), volume/contract | identity fences need verification + must be defensible/fair; geographic fences invite grey-market arbitrage |
Rule: a fence is legitimate only if the lower-WTP segment *can't easily jump it* and the gating tracks real value, not artificial crippling (which becomes a Killer).

## 8. Outcome & AI pricing — cost-per-call envelope + margin-inversion caveat
As agents replace seats, per-seat logic breaks → price on **outcomes** (per resolved ticket, per successful match) or **consumption** (per run/token). But inference is **variable COGS**, so model `P × accept × margin%`, not `P × accept`.
**Cost-per-call envelope (fill-in):**
`cost per successful outcome = (tokens/attempt × $/token + infra/attempt) × attempts per success.`
- Illustrative: $0.04/attempt × 1.8 attempts per resolution = **$0.072 COGS per resolved ticket.** Price per resolved ticket $0.50 → gross margin ~86%. Set a **margin floor** (e.g. ≥70%) as a guardrail metric.
- **Margin-inversion caveat (the trap):** pure outcome pricing inverts margin the moment model cost > price captured — a hard task that needs 6 retries, or a model-price/usage spike, can make a "win" lose money per call. Mitigations: a per-outcome **cost ceiling / circuit-breaker**, a retry cap, hybrid floor (small platform fee + usage), and re-pricing rights on model-cost change. Hold the envelope as a *live guardrail*, not a launch-day assumption.
- Map to the base **AI three-tier metric stack:** quality (eval pass-rate) → experience (resolved-without-handoff) → **unit economics (cost per *successful* task, margin envelope).** Delight that loses money per call doesn't ship.

## 9. Cannibalization / cohort-migration model — is the tier *incremental*?
A new tier that just relocates revenue you already had is a loss dressed as a win. Decompose monthly:
`Net-new revenue = (net-new customers × tier price) + (upsell from lower tiers × Δprice) − (downgrades into the new tier × Δprice) − (cannibalized from higher tiers × Δprice) − churn delta.`
- **Cohort split:** tag every buyer of the new tier as **net-new / upsell / lateral / downgrade.** Only net-new + upsell are expansion; lateral and downgrade are migration. Track for ≥2–3 cohorts before declaring success.
- **Decision rule:** ship/keep the tier if `expansion > migration` *and* it doesn't degrade the guardrails below — and re-test if it doesn't.
- **Post-launch instrumentation (base §Pricing):** NRR, tier mix / attach rate, win rate by tier, and a **sales-cycle-length guardrail** (a new tier that adds a decision and slows deals can be net-negative even if mix looks good). Re-test pricing ≥ quarterly and on every packaging or model-cost change.

**Pre-lock blind-spot check (pricing is Type-1 / high-stakes → run the FULL check):** (1) which method am I trusting and what does the *other* say (PSM band vs G-G point vs EVC ceiling — name the disagreement)? (2) is my survey segment the real buyer, or a convenience sample? (3) are my benchmark ratios outlier-winner survivorship? (4) is "outcome pricing is inevitable" a recency artifact of cheap capital / current model prices? (5) contrarian: would a single simple price out-convert this whole architecture by removing choice friction? Name a concrete failure mode to watch.
===== END PRO: PRICING =====
