===== BEGIN PRO: GROWTH =====
Load when: designing an OEC, modeling a growth loop, sequencing a PLG/hybrid motion, scoring PQAs, or building an experiment whose validity is at risk (many comparisons, networked/marketplace interference, novelty effects). Base §Growth + §Metrics route here for the worked math. All numbers below are illustrative / point-in-time — re-derive on your own data.

## 1. Funnel vs loop — model the right thing
- **Funnel** = one-shot, top-to-bottom (AARRR, McClure). Useful for diagnosing a *stage* leak. Fatal flaw: it has no engine — every cohort starts from paid input.
- **Loop** = the output of one turn re-feeds the input of the next (Reforge). Compounding, defensible, harder to copy. A funnel asks "where do users drop?"; a loop asks "what does a converted user *produce* that pulls in / re-activates the next user?"
- Rule: instrument the **loop**, report the funnel as its cross-section. If you can't name what the output re-feeds, you have a funnel pretending to be a loop — growth will stall the day you stop buying input.

## 2. Growth-loop modeling — the input→output re-feed math
Generic loop: `new_input(t+1) = output(t) × conversion`. The loop's *gain* K decides whether it amplifies or just leaks.

**Acquisition / viral loop.** K = invites_per_user × invite→signup conversion.
- Steady-state amplification of any base acquisition = `1 / (1 − K)` for K<1; K≥1 = runaway (rare, audit for fraud).
- *Worked (illustrative):* base = 1,000 organic signups/wk; each new user sends 2 invites; 8% convert → K = 0.16. Amplifier = 1/(1−0.16) = **1.19** → effective ~1,190 signups/wk. Doubling invite-conversion to 16% → K=0.32 → amplifier **1.47**. The leverage is on conversion, not invite *volume* — invites are cheap noise; the accept step is the constraint.

**Engagement loop.** output = content/data/habit a user creates that pulls them (or others) back. Model as a **weekly return rate** r per active user (the share who come back the next period). Keep the two regimes separate — they have opposite signs:
- *With constant acquisition A:* the active base trends to a steady state `N → A / (1 − r)`. *Worked (illustrative):* A = 2k new actives/wk, r = 0.3 → N ≈ 2,000 / 0.7 ≈ **2,857** sustained actives.
- *Without new acquisition:* the base decays geometrically by the return rate each week, toward zero — 10k → ~3k → ~900 → … (each week retains only the r-fraction). There is no positive floor; only acquisition holds the base up.

The lever is r itself, measured by **killing the loop output** (e.g. notifications off) in a holdout and watching the return rate drop.

**Monetization loop.** revenue re-feeds **paid acquisition**. Self-funding iff `LTV > CAC` AND payback < cash runway. Reinvestable surplus per customer = LTV − CAC; recycle into CAC at the same unit economics → compounding spend. *Worked:* LTV $300, CAC $100, payback 4 mo → each customer funds ~2 more at the same CAC after payback; the loop is gated by **payback period**, not LTV:CAC ratio — a 3× ratio with 18-mo payback starves the loop.

Decision: pick the **one** loop that is your primary engine this stage (acquisition early, engagement mid, monetization at scale — they trade off). Don't run three half-instrumented loops.

## 3. PLG motion sequencing + hybrid-PLG (Verna)
Pure PLG is rare at scale — winners **layer** motions and sequence them (Elena Verna). Default sequence:
1. **PLG self-serve** — low TTV, freemium/trial, in-product upgrade triggers. Owns acquisition + activation + low-end expansion.
2. **Product-led sales (PLS)** layered on top — reps engage *only* accounts that cross a usage threshold.
3. **Marketing-led** demand-gen + **sales-led** outbound for segments PLG can't reach (high-ACV, compliance-gated, low-frequency).

**PQA > PQL.** B2B buys at the **account** level — score Product-Qualified *Accounts* (usage aggregated per logo), not lone-user PQLs, or sales chases noise.
- PQA score = **fit** (firmographic: ICP match, employee count, industry) × **engagement** (breadth: # active seats; depth: core-action frequency; velocity: week-over-week growth).
- *Worked routing table (illustrative):*

| Account | Fit (0-5) | Active seats | Core-actions/wk | WoW velocity | PQA | Route |
|---|---|---|---|---|---|---|
| Acme | 5 | 14 | 90 | +22% | high | PLS rep now |
|Bolt | 2 | 30 | 200 | +5% | mid (low fit) | nurture, don't staff |
| Cog | 5 | 3 | 12 | +40% | rising | watch; trigger at seat-threshold |

**Ring-fence PLS (critical).** Reps touch an account **only** past the usage threshold AND where self-conversion is unlikely (e.g. multi-team, security review pending). Do **not** let reps work accounts that would self-convert — that cannibalizes margin and inflates "sales-sourced" revenue. Measure PLS by *incremental* conversion over a self-serve holdout, not gross.
- Metrics: PQL/PQA, TTV, activation rate, free→paid (~2-5% directional), **NRR** (the PLG North Star; >100% healthy, ~120%+ best-in-class — directional/point-in-time).
- **Not** for high-touch, low-frequency, or compliance-gated buying — there, lead sales-led; PLG becomes a lead-gen feeder, not the engine.

## 4. Painted-door / fake-door test (demand before build)
Ship the **entry point** (button, menu item, pricing tier) → count intent (clicks / signups for "notify me") → show "coming soon." Cheap pre-build signal.
- Report **intent rate** = clicks ÷ exposed users, against a pre-set bar (e.g. "build only if >5% of exposed click — illustrative"). Segment the clickers (are they your ICP?).
- **Never leave it live** — repeated dead doors cost trust. One exposure window, then kill or build. Pair with a follow-up survey/concierge to confirm the click meant the job, not curiosity (novelty inflates first-touch).

## 5. OEC design — WORKED (short-term proxy that predicts long-term value)
**OEC** (Overall Evaluation Criterion, Kohavi/Tang/Xu) = the **one** metric an experiment optimizes — a short-term, in-window proxy chosen *because it predicts* the long-term goal you can't measure in two weeks. Set it (and guardrails) **before** launch; never pick metrics after peeking.

Steps:
1. **Name the long-term goal** you actually care about (6-mo retained revenue, LTV).
2. **List candidate short-term proxies** measurable inside the experiment window.
3. **Validate** each proxy against history: does the cohort that moves the proxy retain/monetize better? Check **sensitivity** (does it move on real changes?) and **directional alignment** (no proxy that rises while value falls — Goodhart).
4. **Compose** into a single OEC (a primary metric, or a normalized weighted combo).
5. **Attach guardrails** — must-not-regress metrics that catch the proxy being gamed.

*Worked (illustrative — food-delivery app):*
- Long-term goal: 26-week retained gross profit per signup. Window: 14 days.
- Candidates: sessions/user, items browsed, **completed orders/user (14d)**, push opt-in.
- Validation on prior cohorts: users with **≥3 completed orders in 14d** retained at 58% to week 26 vs 19% for <3 → strong, sensitive, aligned. "Sessions" rose with a confusing UI (users lost, clicking around) → *rejected* (rises while value falls).
- **OEC = completed orders per user in first 14 days.**
- **Guardrails (ship-blocking if they regress):** median delivery-time SLA, refund/cancellation rate, support-contacts per order, app-crash rate, **unsubscribe rate**, and (regulated contexts) any consent/disclosure metric. A treatment that lifts the OEC but blows a guardrail does **not** ship.
- Rule: a stat-sig *tiny* OEC lift may still not be worth shipping once you price the opportunity cost (eng, complexity, surface risk) — judge effect size vs the next-best use of the slot, not just p<0.05.

## 6. Experiment-design template (fill-in, pre-commit before launch)
```
Hypothesis (causal WHY, not just WHAT): We believe [change] will [mechanism] →
  moving [OEC] because [reason]. (Raviv: state the why — that's the learning.)
OEC: ____   Guardrails (must-not-regress): ____, ____, ____
Unit of randomization: user / session / account / cluster / time-slice  (see §8)
MDE (min effect worth shipping): __%   Power: 80%   α: 0.05
Required N / expected duration: ____ (don't peek; fix the horizon)
Validity gates: SRM check (split = design?) · pre-period/A-A balance ·
  no overlapping confound in window (outage/holiday/price/PR/campaign) ·
  invariant-metric check (a metric the change should NOT move)
Pre-committed decision rule: win→__ / flat→__ / loss→__   (write before unblinding)
Segments to read: STATIC pre-treatment only (country, device, signup cohort)
Multiplicity plan: # comparisons = __ ; correction = Bonferroni / BH (see §7)
Interference risk: none / networked / marketplace → design = __ (see §8)
Analysis: novelty/primacy date-segmentation plan (see §9)
```

## 7. Multiple-comparison correction (Bonferroni / Benjamini-Hochberg)
Testing many metrics, variants, or segments inflates false positives: at α=0.05, **20 independent comparisons → ~64%** chance of ≥1 false "win" (1−0.95²⁰). Correct it.
- **Bonferroni** — control family-wise error: use threshold **α/m** (m = # comparisons). m=10, α=0.05 → require p<0.005 each. Simple, conservative; right when any single false positive is costly (e.g. shipping a harmful change).
- **Benjamini-Hochberg (BH)** — control the **false-discovery rate** (expected share of false wins among declared wins); more powerful for screening many metrics. Procedure: sort p-values ascending p₍₁₎…p₍ₘ₎; find the largest i with **p₍ᵢ₎ ≤ (i/m)·α**; declare 1…i significant.
- *Worked BH (illustrative, m=5, α=0.05):* p = 0.001, 0.008, 0.02, 0.04, 0.21. Thresholds (i/m)·α = 0.01, 0.02, 0.03, 0.04, 0.05. Largest i with p₍ᵢ₎≤threshold: i=4 (0.04≤0.04). → declare the first **4** significant (Bonferroni at 0.01 would pass only the first 2). Choose BH for exploration, Bonferroni for a go/no-go safety call.

## 8. Interference / SUTVA — networked & marketplace deep designs
Standard A/B assumes **SUTVA**: one unit's treatment doesn't affect another's outcome. False in **two-sided marketplaces, social graphs, shared-supply, shared-budget** systems — treated users spill onto control (a treated rider depletes the same driver pool a control rider draws from), biasing the measured effect. Two fixes:
- **Cluster / geo randomization** — randomize whole self-contained units (city, market, region, company/team) instead of individuals, so spillover stays *within* an arm. Cost: far fewer effective units → less power; needs many balanced clusters and often CUPED/variance reduction. Use when interference is spatial/organizational (delivery markets, ride-hail cities, B2B per-account features).
- **Switchback randomization** — randomize **time windows** (e.g. 30-min slices) ON/OFF across the *entire* market, comparing on vs off periods. Each market is its own control over time; handles strong supply/demand coupling. Watch carry-over between adjacent slices (add washout buffers) and time-of-day confounds (balance the schedule). Use when the market is too coupled to split geographically (pricing, matching, surge).
- Always state the interference risk in the design doc; "we randomized by user" in a marketplace is a silent validity bug, not a detail.

## 9. Novelty / primacy — date-segment, trust the steady state
Week-1 lift is contaminated: **novelty** (curiosity spike that fades) or **primacy** (users re-learn a changed flow, effect *grows*). Don't read the launch spike as the durable effect.
- Plot the **daily/weekly treatment effect** over the window. Fades to baseline → novelty (don't ship on the spike). Rises then plateaus → primacy (the steady state is the real, larger effect).
- Segment **new vs existing** users: novelty hits existing users hardest; a new-user-only readout often shows the true long-run effect sooner.
- Extend the window past the decay/learning curve before committing; if you must decide early, decide on the **trend's asymptote**, not the integral.

## Pitfalls (fast scan)
- SRM/Twyman first — a surprising or 51/49-when-designed-50/50 result is probably an instrumentation bug; debug before interpreting.
- Segment only on **static pre-treatment** attributes — slicing on post-treatment behavior invents fake wins.
- Don't A/B everything (Raviv) — low-traffic, strategic/irreversible, or un-instrumentable bets → use judgment + qualitative; state the hypothesis (why), not just the prediction (what).
- Regulated (fintech/health): consent, adverse-action, clinical-safety guardrails **gate** the test — not optional metrics.
===== END PRO: GROWTH =====
