===== BEGIN PRO: POSITIONING =====
Load when: deriving positioning end-to-end (the full Dunford 5 components), validating a statement, building an insight-led sales pitch, picking a market category, handling buyer≠user, or planning a de-risked launch. Base §GTM gives the pointers; this is the worked depth. Attributions: Dunford (*Obviously Awesome* — the 5-component method, the validation tests; *Sales Pitch* — insight-led pitch), Moore (*Crossing the Chasm* — beachhead, whole-product), Biddle (DHM hard-to-copy test), Dixon & McKenna (*The JOLT Effect* — 40–60% no-decision, indecision/FOMU), Perri (launch = risk reduction), Yien/Rachitsky (10-section PRD, for the launch-spec pointer).

## 1. Positioning is deliberate, not inherited
- **Default positioning is an accident of history** (Dunford): you named the product against the alternatives that existed the week you started, and never revisited it. The job is to *choose* the frame that makes your value obvious — not to describe the product.
- Positioning ≠ messaging ≠ narrative. **Positioning** = what it IS and for whom (PM owns). **Messaging** = how to say it (Marketing owns). **Narrative** = how to tell it in context (Sales owns). Misnaming positioning as "a tagline problem" sends you to copywriting when the frame itself is wrong.
- **Contrarian — positioning is a living hypothesis, not a monument.** Pre-PMF, a formal statement can be premature; treat it as something you test in sales calls and revise, not a fixed artifact you defend.

## 2. The Dunford 5-component derivation — in order, each feeds the next (WORKED)
Derive **in sequence**; reversing it (starting from the category you wish you were in) is how teams end up positioned against a market that doesn't want them.
1. **Competitive alternatives** — what the customer uses *if you don't exist*. **Always include "do nothing"/status quo — usually your #1 competitor.** A spreadsheet, a junior hire, an internal script all count.
2. **Unique attributes** — capabilities/features you have that the alternatives do *not*. Be ruthless: "easier to use" is not unique; a specific mechanism is.
3. **Value** — what those attributes let the customer *do that they care about*. Reach it with the **"so what?" ladder** (§3).
4. **Best-fit customers** — the segment that cares *most* about that value (best-fit, not all-addressable). The characteristics that make a buyer fall in love fast.
5. **Market category** — the frame of reference that makes the value obvious and sets the buyer's expectations.

**Worked (illustrative — a metrics/analytics product, default-positioned as "yet another BI dashboard tool"):**
- **Alternatives:** Tableau/Looker (head-to-head BI), *and* "do nothing — analysts hand-write SQL per request, metric definitions live in 40 conflicting dashboards." The status quo is the real incumbent.
- **Unique attributes:** metric definitions are **git-versioned, code-reviewed, and compiled to one semantic layer** every tool queries. No BI tool does this.
- **Value ("so what?" applied):** *consistent, governed numbers* — "revenue" means the same thing in every dashboard, board deck, and Slack message; ends the "whose number is right?" fire drill; audit-ready.
- **Best-fit customers:** mid-to-large data teams (≥5 analysts, illustrative) where **conflicting metrics already caused a visible, expensive mistake** — they care most. NOT the solo analyst at a 10-person startup (no pain yet → §5 chasm).
- **Market category:** reframe from "BI dashboard tool" (a crowded, feature-compared market where git-versioning reads as a quirky checkbox) to **"metrics / semantic governance layer"** — a frame where versioned definitions are the *whole point*, not a feature.
- Judgment: the category choice (step 5) is where the work pays off — in "BI tool" the differentiator is invisible; in "metrics layer" it's the table stakes. Same product, opposite win rate.

## 3. The "so what?" ladder + frame stress-tests
- **"So what?" ladder (attributes → value):** ask "so what?" of each unique attribute until you land on something a buyer would *pay* for. *git-versioned defs → so what? → numbers can't silently diverge → so what? → board/finance trust the same source → that's the value.* Stop laddering when the next "so what?" is a business outcome, not a feature.
- **DHM hard-to-copy test (Biddle):** a differentiator a competitor can ship next quarter is a **feature, not positioning**. Ask: does this make customers **D**elighted, is it **H**ard to copy, is it **M**argin-enhancing (does it improve unit economics)? Position on attributes that survive a rival's roadmap.
- **JTBD job-story:** frame the underlying need as *"When [situation], I want to [motivation], so I can [outcome]"* — keeps the value customer-anchored, not feature-anchored.
- **Sell what's on the truck:** position the product you **ship today**, not the roadmap. AI capability is increasingly *table stakes* — in positioning, ignore future/competitor moves and frame on shipped value; address roadmap on the roadmap, not in the pitch.

## 4. Validation battery — run all three before you lock the frame
A frame that reads well to *you* is worthless; these are the falsification tests (Dunford). Fail any → the component above it is wrong; go back, don't patch the words.
| Test | How to run it | Pass / Fail signal |
|---|---|---|
| **Customer-mirror** | Read the value statement to 5–8 best-fit customers cold. Ask them to describe, in *their* words, what the product does and who it's for. | **Pass:** they echo your value (often better than you wrote it). **Fail:** they reach for the old category ("oh, a dashboard thing") → your category (step 5) didn't land. |
| **Substitutability swap-test** | Swap your product name for the top competitor's in the statement. Re-read. | **Pass:** the statement now reads *false* (the differentiator is yours alone). **Fail:** it still reads true → you've described the category, not your position. Most generic positioning dies here. |
| **Durability** | War-game the next 2–3 competitor moves and the next model/tech shift. Does the frame survive them? | **Pass:** the differentiator is structural / hard-to-copy (DHM). **Fail:** a rival or a base-model upgrade neutralizes it next quarter → it's a feature; re-derive on a durable attribute. |
- Worked: swap-test on our example — *"Tableau compiles every metric from one code-reviewed source"* reads **false** → the attribute is genuinely ours. Good. Customer-mirror catches the failure mode where buyers still say "BI tool" → if so, the category frame needs more education or a narrower beachhead (§5).
- Cadence: re-run customer-mirror every quarter and after any major competitor launch — positioning rots silently as the market moves around you (§9 monthly sync is the early-warning system).

## 5. Pick the category — 3 market-frame strategies + the chasm
**Choose the frame with eyes open (Dunford). Decision rule: take the cheapest frame your differentiation can actually win in.**
| Strategy | What it is | Cost / when to pick it |
|---|---|---|
| **Head-to-head** | win an existing market *as defined* | **Cheapest demand** (buyers already shopping) — pick when you can out-execute incumbents on their own terms. Don't pick if your edge is invisible in their feature-compare grid. |
| **Big-fish-small-pond** | sub-segment a market you can dominate | **Best default for challengers** — own a niche convincingly, then widen. Pick when a clear sub-segment feels your value most. |
| **Create-a-new-game** | define a new category | **Highest cost** — you must *build the demand* and educate the buyer. Pick ONLY when no existing frame fits AND you can fund years of category education. Most "new category" plays should have been big-fish. |
- Our worked example sits between big-fish ("governance layer for data teams") and create-a-new-game ("metrics layer") — pick big-fish first unless you can fund category education.
- **Moore — beachhead & the chasm (early markets):** crossing from early adopters (buy vision) to the early majority (buy references) requires a **beachhead**: one narrow segment you dominate completely before expanding. Pick it on (a) a compelling reason to buy *now*, (b) a **whole product** you can actually complete for them, (c) word-of-mouth density (they talk to each other). **Do not spread thin pre-chasm** — the early majority wants a safe, proven choice for *their* exact use case, not a flexible tool for everyone.

## 6. The one-line statement (Moore template) + buyer ≠ user
The single-sentence output of the §2 work — the alignment artifact, not the pitch:
```
For [best-fit segment] who [need/JTBD],
[product] is a [market category]
that [single most important benefit/value].
Unlike [primary alternative — incl. status quo],
our product [the differentiating attribute that delivers the benefit].
```
- Filled (worked): *"For data teams who can't trust that 'revenue' means the same thing twice, [Product] is a metrics governance layer that gives every dashboard one audited, version-controlled definition. Unlike BI tools bolted onto ad-hoc SQL, our product compiles every metric from one code-reviewed source."*

**Two positioning statements when buyer ≠ user (PLG / bottom-up B2B).** When the person who *adopts* isn't the person who *pays*, one statement can't serve both — the end-user cares about the job; the economic buyer cares about ROI, risk, and control. Write **both**, keep them coherent (same product, two value frames), and route each to the right surface.
| | End-user statement (drives **adoption**) | Economic-buyer statement (drives **purchase**) |
|---|---|---|
| Cares about | getting the job done today, low friction | ROI, risk reduction, governance, total cost |
| Lands on | the product (in-app, docs, free tier) | the sales deck, security review, the order form |
| Worked value frame | *"ship a trustworthy metric in minutes — no waiting on the data team"* | *"end the 'whose number is right?' fire drill org-wide; audit-ready governance, fewer board-deck errors"* |
- Failure mode: a bottom-up product that only writes the user statement gets viral adoption and then **stalls at procurement** because no one armed the buyer's ROI case (and vice versa: an ROI-only frame that never wins the user gets shelfware). Map the §7 pitch and §9 sales motion to whichever statement the deal is currently stuck on.
- **Pressure-test each statement** before locking: does it survive a hostile read? Is the alternative real (and does it include status quo)? Is the benefit a value or a feature? Is the target *narrow enough* to fall in love? Then run the §4 battery on it.

## 7. The sales pitch build — insight-led, not product-led (Dunford, *Sales Pitch*)
A pitch has two parts: **the insight** (a POV that reframes how the buyer should *evaluate* options) and **the differentiated value**. **Lead with the insight, never the company.** Two-act arc: **setup** (insight → reframe the buying criteria) → **follow-through** (your product satisfies the criteria you just reset).
1. **Insight / setup** — the non-obvious truth about the buyer's problem. *"Every team you query trusts a different 'revenue' number, and you only find out in the board meeting."* If they nod here, you've reframed the buying criteria toward your strengths.
2. **Alternatives & their inherent tradeoffs** — name the options *including status quo*, and the structural weakness each carries. *BI-on-ad-hoc-SQL → fast but ungoverned; warehouse-only → governed but no self-serve; do-nothing → silent divergence.* Be fair; fairness earns trust.
3. **"The way we see it" — perfect-world criteria** — the 3–4 things a *perfect* solution would do, **stacked toward what only you deliver** (governed AND self-serve AND auditable). The setup pays off here.
4. **Follow-through — introduce the product** — map each capability → a criterion → a value. Not a feature tour; a criteria-satisfaction walk.
5. **Proof** — references (the early-majority currency), data, a live demo of the exact JTBD. One on-segment reference beats five generic ones.
6. **The ask + de-risk the decision** — see §8; the failure mode here is not losing to a rival, it's the deal stalling.

## 8. The real B2B enemy is indecision — JOLT (Dixon & McKenna, *not* Dunford)
> ⚠️ **"40–60% of B2B deals end in no-decision" is the JOLT Effect — Dixon & McKenna, *The JOLT Effect* — NOT Dunford.** The enemy is the customer's **FOMU (fear of messing up)**, not a competitor. Position against the **status quo**, not only rivals.
- **J — Judge the indecision:** read whether the buyer is stuck on *valuation* (is it worth it?) or *outcome uncertainty* (will it work for us?). Different stalls need different fixes — diagnose before you push.
- **O — Offer a recommendation:** don't lay out 12 options and "let them decide" — that *increases* FOMU. Tell them what you'd choose for their situation, and why.
- **L — Limit the options:** narrow the configuration/tier choices; choice overload kills more deals than price. (Ties to §6: a sharp two-statement frame already pre-narrows.)
- **T — Take risk off the table:** pilots, success guarantees, staged rollouts, opt-out clauses, proof-of-value periods — make "yes" feel safe.
- Pair with positioning: a sharp frame *reduces* FOMU because the buyer can clearly see this is built for *their* exact situation. Indecision is a positioning symptom as much as a sales one.

## 9. Launch = risk reduction, not a date (Perri)
**De-risk on three questions BEFORE committing — any one unproven and the launch is theater:**
- **Valuable** — does it solve a real problem? (evidence, not assertion)
- **Adoptable** — can users find it and succeed with it? (onboarding, discoverability)
- **Viable** — can you support and sustain it? (cost, ops, COGS envelope)

**Mechanics:** feature-flag to a small cohort first → watch real failure modes → widen (no big-bang). Ship a **cohesive bundle** — related changes as one coherent narrative, not a dribble of half-features.

**Phased plan (directional / point-in-time):**
- **Pre (~8–12 wk):** beta, sales/support **enablement**, **pricing + positioning locked**, success metrics + guardrails defined, launch tier/config narrowed (§8).
- **Launch:** coordinated product/marketing/sales/support; internal comms *before* external; the §6 statement(s) and §7 pitch are the source of truth for all messaging.
- **Post (~4–8 wk):** adoption + retained-value metrics, iterate, retro.

**Launch-readiness checklist (fill-in):**
```
Valuable: evidence the problem is real + painful = [____]
Adoptable: activation path instrumented? discoverability tested? = [Y/N]
Viable: support/ops/COGS sustainable at scale? = [Y/N]
Positioning passed §4 battery + statement(s) LOCKED (no live edits during launch)? = [Y/N]
Buyer-statement + user-statement both armed (if buyer≠user)? = [Y/N]
Enablement: sales/support trained on pitch + objections + JOLT de-risk? = [Y/N]
Flagged rollout cohort + rollback plan? = [____]
Success metric (adoption/retained value, NOT ship-count) + guardrails = [____]
```
> ⚠️ **Optics-velocity trap:** ship-count and launch velocity are vanity. A launch nobody adopts moved no outcome — measure **adoption and retained value**, not the press hit. (For the launch spec itself, the §Templates **10-section PRD — Kevin Yien (Square), popularized by Lenny Rachitsky, NOT a "ChatPRD standard"** — carries the Non-Goals + Narrative sections a launch needs.)

## 10. Keep positioning alive in the org (enterprise / sales integration)
- **Ownership split + monthly PM↔Sales sync:** PM owns positioning, Marketing owns messaging, Sales owns narrative. Monthly: Sales brings **top-5 loss reasons + top-5 customer requests**; PM shares upcoming releases + positioning guidance. This loop catches drift (and §4 customer-mirror failures) before they become a rewrite.
- **Customer-committed roadmap:** when Sales promises a feature to close a deal, gate on (1) strategy fit, (2) how many *other* customers need it, (3) true cost incl. maintenance — separate customer-funded builds from the roadmap.
- **Deal-breaker escalation:** when the CRO escalates, make opportunity cost visible — *"Here's what we'd deprioritize to do this; want that trade?"* Score one-off-vs-generalizable × deal value vs. maintenance/opp-cost × reversibility → build / yes-with-conditions / no-with-alternative.
- **Aumayr split (mature orgs):** **Strategic PM** owns market strategy, pricing, positioning; **Operational PM** owns backlog and delivery — don't let positioning become an afterthought squeezed between sprints.

Regulatory note: in fintech/healthcare, claims in positioning and launch copy are **compliance-gated** (substantiation, fair-balance, adverse-action rules) — legal review is a mandatory launch gate, and an unsubstantiated benefit claim can block the launch outright.
===== END PRO: POSITIONING =====
