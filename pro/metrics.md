===== BEGIN PRO: METRICS =====
Load when: designing a North Star + input tree, building a growth-accounting/retention model, defining guardrails, picking a B2B or agent/AI outcome metric, building a value-driver tree (impact × controllability), or auditing a metric that "looks up" while value isn't. Base §Metrics routes here for the worked depth. All `~`/band numbers are directional / point-in-time — verify against your own data.

## 1. North Star + 3-5 input tree — the WORKED decomposition
**Rule (Amplitude North Star Playbook):** ONE metric that captures delivered customer value + revenue, broken into **3-5 *movable* input metrics** that ladder to it multiplicatively or additively. Inputs must be (a) leading, (b) ownable by a team, (c) collectively ~explain the NSM. If an input can't be moved by a squad next quarter, it's a context metric, not an input.

**Method (do this on a whiteboard):**
1. State the value moment in one sentence ("a user listens to music they like").
2. Write the NSM as a *quantity of that value delivered over time* — not a count of events.
3. Algebraically factor it into breadth x frequency x depth (x quality). Each factor = one input.
4. Assign each input an owner + a guardrail it must not break.
5. Sanity-check: if every input moves +10%, does the NSM move ~+33%? If not, the tree leaks — you're missing a factor or double-counting.

**Worked — Spotify (illustrative numbers):**
`Time Spent Listening (NSM) = WAU x sessions/WAU/week x minutes/session`
| Input | Illustrative | Owner | Guardrail |
|---|---|---|---|
| WAU (breadth) | 220M | Growth | new-user D7 retention not down |
| sessions/user/wk (frequency) | 11 | Core/Home | skip-rate per session not up |
| minutes/session (depth) | 24 | Discovery/ML | "thumbs-down"/session not up |
NSM ≈ 220M x 11 x 24 = ~58.1B listener-minutes/wk (illustrative). A recommender that boosts minutes/session by autoplaying filler raises depth while *quality* (thumbs-down) degrades — Goodhart. That's why depth needs the satisfaction guardrail in the same row.

**Templates (fill in your own):**
- B2C habit: `Value = Active users x core-action frequency x success-rate-per-action`
- Content/marketplace consumption: `= consumers x sessions x items-consumed/session x completion-rate`
- Two-sided marketplace → **TWO trees** (supply liquidity + demand liquidity); the binding side (min(supply,demand)) is the real NSM.

**Re-validation:** every quarter, regress NSM against 90-day retention + revenue. If correlation has decayed, the NSM became a target and got gamed — re-derive. NSM is a proxy, never the goal.

## 2. Guardrail taxonomy — pair at least one, ideally one per input
Pick the guardrails that could move *against* the user while the NSM rises:
| Class | Example guardrail | Catches |
|---|---|---|
| Quality / health | error rate, p95 latency, crash-free % | "engagement" that's actually rage-clicking |
| Customer sentiment | CSAT, thumbs-down rate, support-ticket rate | depth bought by annoyance |
| Trust & safety | report rate, policy-violation exposure | growth via toxic/unsafe content |
| Unit economics | gross margin, cost per active user, COGS/session | usage that loses money |
| Retention / churn | logo + revenue churn, dormancy rate | a spike that doesn't stick |
Counting-method drift (base §Metrics) applies here too: hold N-day vs rolling vs bracketed definitions fixed across the guardrail and the NSM.

## 3. AARRR growth accounting (Jonathan Hsu / Social Capital) — the WORKED math
**MAU decomposition** — every active user this month is one of five states vs last month. The point is the *flows*, not the level:
- **New** — first-ever active this month
- **Retained** — active last month AND this month
- **Resurrected** — active before, dormant last month, active again now
- **Churned** — active last month, NOT this month (a negative flow)
- **Dormant** — churned and still gone (the silent reservoir resurrection draws from)

`MAU(t) = Retained + New + Resurrected` and `ΔMAU = (New + Resurrected) − Churned`.

**Worked (illustrative):** last month MAU 100k. This month: New +18k, Resurrected +6k, Churned −20k → MAU = 80k retained + 18k + 6k = 104k.
- **Quick Ratio = (New + Resurrected) ÷ Churned = (18+6)/20 = 1.2.** Below 1 = leaking faster than filling, regardless of how strong acquisition looks; ~1.0 treading water; growth SaaS often targets ~1.5-2+ (directional). A QR of 1.2 off heavy acquisition is fragile — you're one acquisition dip from shrinking.
- Diagnose *which flow* is the lever: shrinking churn usually beats buying new users, because churn compounds against every future cohort.

**L-day engagement histogram (Ln metric, Amplitude):** of the last 28 (or 30) days, on how many was each user active? Plot the distribution.
- Bimodal "smile" (mass at L1-3 AND L25-28) = a power-user core + a tourist tail → segment them; the average L-value hides both.
- Watch the **L28/L7 split** — daily-habit products want mass piling at the high end.

**Retention curve — read the FLOOR, not the slope:**
1. Plot % of a signup cohort still active by day (D1, D7, D14, D30, D60, D90).
2. The curve must **flatten to a non-zero asymptote** — that floor is your retained core; if it decays toward 0, you have no PMF, only churn-and-replace.
3. Compare cohorts over time: a *rising floor* (curve flattening higher) is the single best leading sign of product-market fit — better than any acquisition number.
4. Trace a retention problem **upstream** (base §AARRR): a low D1-D7 floor is almost always an **Activation / time-to-value** miss, not Acquisition. Fix the aha, not the ad spend.

**Vanity vs value gate:** Acquisition (signups, downloads, MAU level) is vanity; Activation/Retention/Revenue *flows* are value. Always pair a retention fix with a North-Star input + guardrail so you don't fix retention while degrading activation or monetization.

## 4. HEART (Google — Rodden, Hutchinson, Fu) — Goals→Signals→Metrics, worked for ONE feature
Feature/UX level, NOT company level. Pick the 1-2 rows the feature actually moves; don't fill all five for show. Each row: **Goal** (what good means) → **Signal** (observable behavior that indicates it) → **Metric** (the ratio you ship on a dashboard).

**Worked — "Saved Replies" in a support inbox (illustrative):**
| Dim | Goal | Signal | Metric (target, illustrative) |
|---|---|---|---|
| Happiness | agents trust the suggestion | post-use thumbs-up | ≥70% positive |
| Engagement | becomes part of the flow | replies sent via feature | ≥3 / agent / day |
| Adoption | new agents pick it up | % of active agents who used it in first week | ≥40% |
| Retention | sticks past novelty | % of week-1 users still using it week-4 | ≥60% |
| Task success | speeds resolution w/o errors | median handle-time + edited-before-send rate | −20% time, edit-rate <30% |
Task-success here carries the guardrail (edit-rate up = the suggestions are wrong; speed bought by sending bad replies). Alt lens when the question is *habit loss* rather than UX regression → trigger/hook-decay analysis, not HEART.

## 5. B2B North Star — NRR vs OMTM-by-stage
- **Default B2B NSM = Net Revenue Retention** (expansion − contraction − churn on the existing base): >100% healthy, ~120%+ best-in-class (directional). NRR is the one metric that proves land-and-expand works and survives a CFO. PLG variant: score Product-Qualified **Accounts**, not lone-user PQLs (base §Growth).
- But NRR is a **lagging** outcome — pair it with a stage-specific **OMTM (One Metric That Matters — Croll & Yoskovitz, *Lean Analytics*):** the single metric for your *current* constraint, which changes by stage:

| Stage / constraint | OMTM to obsess this quarter |
|---|---|
| Pre-PMF | % of accounts hitting the activation/aha event |
| Early expansion | seats/account growth or feature-attach rate |
| Scaling | NRR + gross logo retention |
| Efficiency | CAC payback months, magic number |
Run NRR as the durable scoreboard AND one OMTM as the focusing function — reporting only NRR lets a team coast on last year's expansions while the leading flow rots.

## 6. Agent / AI outcome metrics — count JOBS, not events
The moment the product acts on the user's behalf, event volume ("messages sent," "API calls") is vanity — a looping agent inflates it. Measure the **outcome**:
- **Resolved-without-handoff rate** (autonomous success) — the agent NSM.
- **Task success / goal-completion rate** vs a labeled set.
- **Time-to-resolution** and **turns-to-resolution** (fewer is better — the inverse of a chat product).
- **Cost per *successful* task** = (tokens + infra) ÷ resolved jobs — not cost per call; a 90%-success agent at 3x the cost-per-success of an 80% one may be worse.
- **Escalation-to-human rate** + **silent-failure rate** (acted wrong, no flag) — the dangerous one; instrument an observable signal or it's invisible.
Tie to base §Metrics AI three-tier stack: Quality (eval pass-rate) → Experience (task success, no-retry) → Unit economics (cost per successful task). A quality win that doesn't move experience is vanity; an experience win that blows the cost envelope isn't a win.

## 7. Failure mode — business-capture disguised as customer value
The most common metrics fraud: a metric that rises because the **business extracted more**, dressed up as the user **receiving more value**. The two move together in healthy products and *diverge* exactly when you're harvesting.
Tells, and the paired value metric that exposes each:
| "Value" metric going up | What it may actually be | Pair it with |
|---|---|---|
| Ad impressions / screen | more interruption, not more value | sessions/user, D30 retention |
| Time-in-app | confusion / dark-pattern friction | task-success, time-to-complete |
| Revenue per user | price-gouging a captive base | NRR, voluntary churn, CSAT |
| "Engagement" notifications | re-engagement spam | unsubscribe + uninstall rate |
| GMV (marketplace) | subsidy-driven, unprofitable | take-rate, contribution margin, repeat rate |
**Test:** for any NSM, write one sentence describing how it could rise *while the customer is worse off* (Goodhart). If you can't refuse that sentence with a paired guardrail already on the dashboard, the metric isn't safe to optimize. Count value the customer *received and would pay again for*, never value the business *captured this quarter*.

## 8. Benchmark bands (directional / point-in-time — verify current)
| Metric | Weak | Decent | Strong |
|---|---|---|---|
| Retention D1 | <25% | ~30-40% | 40%+ |
| Retention D7 | <10% | ~10-20% | 20%+ |
| Retention D30 | <5% | ~5-10% | 10%+ |
| DAU/MAU stickiness | <10% | ~20% | 50%+ (daily habit) |
| Quick Ratio (growth co.) | <1 (shrinking) | ~1-1.5 | 2+ |
| NRR (B2B SaaS) | <90% | 100-110% | 120%+ |
| Freemium free→paid | <2% | ~2-5% | 5%+ |
**PMF probe (Sean Ellis test):** ≥40% of activated users would be "very disappointed" without the product → signal of product-market fit. Survey *activated* users only; an unactivated cohort answers about a product they never experienced.

## 9. Value-driver tree — the business-value twin of the North Star tree (L.E.K.)
The §1 North Star tree factors *customer* value into movable product inputs. The **value-driver tree** factors *enterprise/shareholder* value (NPV / operating profit) into the operating drivers a team can move — **price · volume · mix · cost · capital · retention** — then ranks them by **leverage, not by how aggressively you can manage them.** Use it to connect a product metric to dollars (business case, exec memo) and to catch the trap L.E.K. names directly: *companies "unintentionally reward managers for attaining performance measures which have little impact on value."* (L.E.K. Consulting, *Identifying & Managing Key Value Drivers*, Exec Insights XIX-36, © 2017.)

**3 steps (L.E.K.'s exact sequence):**
1. **Map** — disaggregate the top number into progressively smaller components "until you reach the level where daily operating management decisions reside" (operating margin → distribution cost → trucking → truck utilization). Document the linkages.
2. **Sensitivity test** — perturb each driver (±10%, or one unit) and measure ΔNPV; rank by the size of the swing (a **tornado**). The ranking routinely upends priorities: L.E.K.'s petroleum business obsessed over *industrial volume* (+10% ≈ $14M) and *trucking cost* (≈ $26–33M) — both near-zero — while *consumer/retail margin* ($485–681M), *retail investment* ($385M), *retail volume* ($321M) and *rail cost* ($281M) dwarfed them. *(All figures illustrative, from the L.E.K. case.)*
3. **Controllability filter** — keep only drivers management can actually move. The sharpest lesson of the case: the **single highest-impact driver, margin, was *uncontrollable*** (regulated pricing) — so it is **NOT a KPI**; it's a hedge / strategy problem. After filtering, the actual KPIs became the controllable high-impact drivers: **discounting, retail volume, investment, rail cost.**

**Value-driver matrix (value impact × controllability):**

| | Low value impact | High value impact |
|---|---|---|
| **High control** | Monitor (cheap to watch) | **Manage actively → these become your KPIs + tie to incentives** |
| **Low control** | Low priority — ignore | Hedge the downside / reconfigure strategy |

Two tests, **both required: significant value impact AND controllable.** Most ops lists fail because "every operating factor is treated as equally important" (L.E.K.).

**Tie-off:** assign each surviving driver an owner by type — *growth* → marketing/sales, *efficiency* → ops, *financial* (capital/WACC) → finance — and substitute value drivers into the performance/incentive system, **tailored by function**. Re-run sensitivity when the cost/revenue structure shifts — the ranking is point-in-time.
===== END PRO: METRICS =====
