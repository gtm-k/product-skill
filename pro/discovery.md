===== BEGIN PRO: DISCOVERY =====
Load when: writing an interview guide, building or pruning an Opportunity Solution Tree, or designing the assumption test that decides a build/no-build call. Base §Discovery names the models; this is the worked depth — templates, scripts, and decision bars you paste and fill. Attributions: Teresa Torres (*Continuous Discovery Habits* — Trio, OST, story-based interviewing, AI-era cautions); Christensen (JTBD, Four Forces, Milkshake competition); Ulwick (ODI / opportunity scoring); Perri (Product Kata); the Udezues (*Building Rocketships* 2025 — sharp-problem test, Zone-of-Benefit); Klein (pre-mortem; Doshi in PM). Model-Capability assumption ties to §AI-Native.

## 1. Run discovery as a system, not a study — the weekly loop
Discovery fails when it's a one-off "research phase" before a build. Make it a standing cadence the Trio owns:
- **Every week:** ≥1 customer touch (interview, observed session, or support-ticket read) → ≥1 opportunity added/updated on the tree → ≥1 assumption test in flight. If a week passes with zero customer contact, that's the bug — fix the cadence before fixing any feature.
- **Recruiting is the silent killer.** Set up *automated, continuous* recruiting (in-app "talk to us" prompt triggered on a relevant action, a rolling panel, or a recruiter cadence) so you never have to *start* finding people — interviews stall the moment recruiting is manual. Target a steady trickle (1–2/wk) over a quarterly batch of 20.
- **Who you talk to is the result.** Recruit on *recent behavior* ("did the job in the last 2 weeks"), not volunteers or your friendliest power users — a panel skewed to fans produces a tree skewed to confirmation.

## 2. The story-based interview guide (paste and fill)
Goal: collect **specific past stories**, not opinions or feature wishlists. People can't reliably predict future behavior or design your product; they *can* recount what they actually did. Every question mines a concrete, recent instance.

```
SETUP (90 sec): "There are no right answers — I'm here to learn how you actually
  work, not to demo anything. Mind if I record so I don't miss details?"

CONTEXT (warm-up, 2–3 min):
  "Walk me through your role and what a typical [relevant period] looks like."

THE STORY (the core — anchor to ONE recent real instance):
  "Tell me about the LAST time you [did the job / hit the situation]."
   → for churn/abandonment: "...the last time you opened [product] and then
      stopped before finishing — what was going on?"
  Then stay in that story with WHAT-happened probes, NOT why-opinion probes:
   - "What were you trying to get done right before that?"
   - "What did you do next? ...and then?"  (walk the timeline step by step)
   - "Show me / where were you / what else was open?"  (recreate the scene)
   - "Last time that happened, what did you do instead?"  (the workaround = the demand signal)
   - "What made you finally decide to [act]?"  (trigger / push)
   - "What almost stopped you?"  (anxiety / inertia — see §6 Four Forces)

EXTRACT (do NOT skip): before ending, name back the moments of friction you
  heard and confirm: "So the painful part was [X] — is that right?"
CLOSE: "Who else lives this problem that I should talk to?"  (snowball recruiting)
```
**Interviewing anti-patterns (each invalidates the data):**
- Asking "**what features do you want?**" or "would you use X?" — pitching, not discovering. You've contaminated the session into solution-validation theater.
- Letting them generalize ("I usually...") — pull them back to the *specific last time*. Generalizations are reconstructed opinion; stories are evidence.
- Leading ("don't you find X frustrating?") — you'll get agreement, not truth.
- Taking *interpreted* notes. Capture **verbatim moments and quotes**; interpretation happens in synthesis (§8), against the transcript — never against the AI's or your own summary (§9).

## 3. Building the Opportunity Solution Tree — outcome down, evidence up
The OST (Torres) is a living artifact, not a one-time diagram. Build it in this order; the discipline is that **every node ladders to the node above it**.

**Step 1 — Anchor the single outcome at the root.** One *product* outcome (a behavior change you can move and measure), not a business metric and not a feature. "Increase weekly active teams" ✓; "ship collaboration" ✗ (that's a solution); "grow revenue" ✗ (business outcome — translate it down to the product behavior that drives it). A tree with two roots is two trees — split them.

**Step 2 — Populate opportunities from interview snippets (evidence up).** An opportunity is a **need, pain, or desire stated in the customer's words**, extracted from a story — never a solution in disguise.
- Test each candidate: phrase it as a solution-agnostic *need* (→ §6: direction + metric + goal). "A faster export" is a solution; "I lose the thread when I have to leave the app to share results" is the opportunity.
- **De-dupe and structure into a hierarchy** — sibling opportunities should be roughly mutually exclusive; parent opportunities are broader phases of the experience. Map each to the moment in the customer's journey where it surfaced.
- Keep the snippet→opportunity link traceable: each opportunity cites the interviews it came from, so you can re-read source when sizing.

**Step 3 — Size opportunities, then pick ONE to work (don't boil the tree).** You attack one opportunity at a time. Rank by *importance × prevalence × your strategic fit*:
- Lightweight: how visceral was it in interviews (frequency + emotion) × how many of the target segment hit it.
- Heavier when stakes warrant — **Ulwick ODI opportunity score**: survey importance + current satisfaction on the underlying *desired outcomes*, score = `importance + max(importance − satisfaction, 0)`. High-importance / low-satisfaction outcomes are underserved → the real opportunities; high-importance / high-satisfaction = table stakes (don't over-invest); low-importance = ignore or *over*served (candidates to cut). Use ODI when you need a defensible, quantified ranking for a roadmap argument; use the lightweight read for week-to-week steering.

**Step 4 — Branch 2–3 solutions under the chosen opportunity (diverge before you converge).** Generate *competing* solutions, not one obvious idea dressed three ways — a single-branch tree means you're committed, not discovering. Only now does solution thinking enter.

**Step 5 — Drop assumption tests under each solution (§4).** The leaves of the tree are *tests*, not features. This is where Product Kata (Perri) plugs in: outcome (root) → current state → **target condition** → obstacle (the chosen opportunity) → experiment (the leaf). Skipping the target condition and jumping root→solution is the classic kata failure.

### Worked example — B2B SaaS activation (all numbers illustrative)
> **OUTCOME (root, one measurable product behavior):** lift week-1 activation — new accounts that complete a first successful data export — from **34% → 50%** *(illustrative)*. (Not "ship onboarding" = solution; not "grow revenue" = business outcome translated down to the behavior that drives it.)
>
> **OPPORTUNITIES (needs in customer words, mention-counts from ~20 interviews, illustrative):**
> - **O1 "I couldn't tell if my import actually worked"** — 12/20 · highest prevalence + emotion → work this first
> - **O2 "I didn't have my data file ready when I signed up"** — 7/20
> - **O3 "The sample template didn't match my use case"** — 5/20
>
> *Sizing (lightweight read):* O1 = high prevalence × high frustration × directly blocks the outcome → chosen. O2/O3 parked, not deleted.
>
> **SOLUTIONS branched under O1 (diverge — competing, not one idea ×3):**
> - **S1** import progress bar + explicit success/failure confirmation screen
> - **S2** inline validation preview ("row 14: invalid date") before commit
> - **S3** concierge "we import your first file for you" white-glove
> - **S4** *(AI)* auto-map the customer's columns to our schema with an LLM
>
> **ASSUMPTION TESTS (leaves — riskiest first, §4):**
> - S4 riskiest = **Model-Capability** ("LLM maps arbitrary columns at the bar") → offline golden-set eval *before any UI*; pre-set bar e.g. ≥90% correct column maps on 50 real files *(illustrative)*.
> - S3 riskiest = **Viability** (does white-glove margin survive at scale?) → margin model on time-per-import × volume.
> - S1 riskiest = **Desirability/Usability** (does a confirmation screen actually move completion?) → 5-user prototype task.
>
> Then **pre-mortem (§5)** the winning branch and run **one end-to-end Wizard-of-Oz** of the whole import flow before full build — branch assumptions can each pass yet the integrated flow still fail.

## 4. Assumption-test design — the riskiest-first engine
A solution is a bundle of bets. Surface them, rank by risk, test the riskiest *cheaply* before building anything.

**Step 1 — Decompose the solution into assumptions, by category:**
| Category | The bet | "We're betting that…" |
|---|---|---|
| **Desirability** | they want it | users care enough to change behavior |
| **Viability** | it works for the business | it doesn't break revenue / cost / legal / strategy |
| **Feasibility** | we can build it | eng can integrate/ship it in our constraints |
| **Usability** | they can use it | users can find and operate it without help |
| **Model-Capability** *(AI only)* | the model is good enough | the model does *this job* on *our* data at the bar — a BET distinct from feasibility (can we wire the API?) and desirability (do users want AI here?). Test on a **golden set** before any UI. → §AI-Native / PRO: ai-evals |

**Step 2 — Map each assumption on importance × evidence.** Plot how much the solution depends on the assumption (importance) against how much evidence you already have. **Test the high-importance / low-evidence corner first** — those are the leap-of-faith assumptions that sink the solution if wrong. Don't spend a cycle re-proving things you already have evidence for.

**Step 3 — Pick the *cheapest test that can produce a NO*** for each risky assumption. Match the test to the bet:
| Riskiest assumption | Cheap test | What a NO looks like |
|---|---|---|
| Desirability | painted/fake-door, landing-page intent, concierge offer | intent rate ≤ baseline (→ PRO: growth §4) |
| Usability | unmoderated prototype task, 5-user think-aloud | users can't complete the core task |
| Feasibility | eng spike / tech prototype on real constraints | can't hit latency/integration bar |
| Viability | WTP probe, margin model, compliance review | unit economics or legal won't clear (→ PRO: pricing) |
| Model-Capability | offline eval on a labeled golden set | accuracy/quality below the pre-set bar |

**Step 4 — Pre-commit the pass bar BEFORE running.** Write the threshold and the decision it triggers *first*, or you'll rationalize whatever number you get. Template:
```
Assumption: We believe [X is true].
Risk if wrong: [what breaks].  Current evidence: [none / weak / strong].
Test: [method] with [N] [target-segment] users.
Pass bar (pre-committed): [metric] ≥ [threshold] → proceed; below → revise/kill.
Run by: [date].  Owner: [Trio member].
```

**Step 5 — Guard the two traps:**
- **Each assumption can pass alone yet the whole flow fails.** Riskiest-first is necessary, not sufficient. Before full build, run an **end-to-end concierge / Wizard-of-Oz** (you manually deliver the outcome behind a real-looking front end) to test the *integrated* experience and the value, not just the parts.
- **Don't out-discover a reversible bet.** For a small, low-cost, Type-2 (reversible) change, *shipping behind a flag is the experiment* — discovery theater on a one-way-cheap decision is wasted weeks. Reserve the full test rigor for irreversible or expensive bets (→ §5).

## 5. Pre-mortem the irreversible discovery bet (Klein; Doshi in PM)
Before committing to a Type-1 / one-way-door solution coming off the tree, run a pre-mortem — *not* on every sprint, only when irreversibility is real (data model, pricing change, public API, regulated flow).
- Frame: "It's 6 months out. We shipped this and it **failed**. Write down why."
- **Written-first, independently** — everyone writes before anyone speaks, which kills the groupthink that makes a confident team blind to its own riskiest assumption.
- Cluster the failure modes → the top 2–3 become *new assumption tests* on the tree (this is how a pre-mortem feeds §4 rather than just generating anxiety).
- In regulated/fintech/health contexts, put Compliance *in the room* — consent, adverse-action, and safety failure modes are gating, not advisory.

## 6. JTBD inside the interview — diagnose the "why" (Christensen)
Layer JTBD onto the §2 story to get *causal* understanding, not just a pain list.
- **Job statement** from the story: "When I [situation], I want [motivation], so I can [outcome]." Frame the job around the *circumstance*, not your product category — remember the Milkshake competes with a banana and boredom, so ask what they *actually* hired and *fired* to make progress.
- **Four Forces timeline** — reconstruct the switch moment and tag each force: **push** of the old situation, **pull** of the new, **anxiety** about the new, **inertia/habit** of the current. For a *new* feature class, anxiety + inertia are usually the dominant blockers — so the discovery insight is "reduce friction/risk," not "add more pull." For churn, run the Four Forces *backwards*: what pushed them off you, what pulled them away.
- **Consumption job ≠ purchase job** — interview the *moment of use*, not just the buy decision; durable churn hides in the consumption job. Three job types (functional / emotional / social) — probe all three; the emotional and social jobs are the ones surveys miss.

## 7. The build gate — sharp-problem test + Zone-of-Benefit (the Udezues, *Building Rocketships* 2025)
Before an opportunity earns build, it must clear a *sharpness* bar — this is the no-build filter that keeps the tree honest.
- **Sharp problem, judged multi-signal:** (a) **workflow compression** — your solution collapses many painful steps into few; AND (b) a visceral, in-interview "**I need this now**" — not polite interest. Both signals, not one. A diffuse or merely-agreeable problem → keep discovering, don't build.
- **Zone-of-Benefit bar:** aim to be **≥3x better** on the *one dimension the customer actually feels* (speed, effort, cost — whichever the stories centered on), not 3x on a spec they don't notice. The 3x is illustrative, not a law — the real test is "noticeably, switch-worthy better on the felt dimension."
- Diffuse signal + weak differentiation is the single most common reason a well-built feature lands flat. This gate sits between OST Step 3 (opportunity chosen) and Step 4 (solutions branched).

## 8. Synthesis & the interview snapshot — capture as you go
Synthesize *continuously*, one snapshot per interview, against the transcript — not in a big-bang readout weeks later (by then the specifics have decayed into your bias).
- **Interview snapshot (one page, fill per interview):**
```
WHO + CONTEXT: [role, segment, did-the-job-when]
THE STORY: situation → step-by-step sequence → where it broke
VERBATIM QUOTES: "[exact words — the friction + the emotion]"
OPPORTUNITIES SURFACED: [needs in their words, solution-agnostic]
EXISTING WORKAROUND / ALTERNATIVE: [what they hired instead = demand signal]
```
- **Roll-up onto the tree:** cluster snapshots into opportunities; track **mention counts** as a rough size signal (directional — small-n, not a survey; don't over-read a single mention). **Saturation** ≈ when new interviews stop adding new opportunities — that's your "enough for now," not a fixed N.
- **Map, don't list.** The OST *is* the synthesis artifact; a flat "findings" list loses the outcome→opportunity→solution lineage and lets pet solutions sneak back in unattached.

## 9. AI-era discovery disciplines (Torres, 2024–26)
AI accelerates synthesis but is a research *assistant*, not the researcher — used naively it manufactures false confidence.
- **It misses ~20–40% of opportunities/insights** *(directional — not a measured constant)*: keep a human in the loop and treat AI synthesis as a first pass to verify, never the source of truth.
- **Decompose the prompt.** A monolithic "do my user research / find the insights" prompt buries failures. Break it into narrow steps (extract verbatim pains → cluster → phrase as needs) you can inspect at each stage.
- **Run the error-analysis loop** like eval traces: read AI outputs → code where it failed → fix the prompt → re-run (→ §AI-Native / PRO: ai-evals).
- **Verify against raw transcripts, never the AI's summary.** The summary is where hallucinated or flattened insight enters; the transcript is the evidence. Same rule as §2 note-taking — interpretation is always checked against source.

---

## 10. Quality Function Deployment — the House of Quality (Hauser & Clausing, "The House of Quality," HBR May 1988)
**Use when** discovery has produced *ranked* customer needs and you must convert them into a measurable spec, set target values, and arbitrate cross-functional trade-offs *before* build. The bridge from §2 interviews (voice of the customer) to §Templates (engineering targets that survive the handoff). Kano (§Prioritization) *categorizes* features; QFD *translates* them into specs and trade-offs — a different job. *(Originated 1972 at Mitsubishi's Kobe shipyard; early use cut Toyota Auto Body startup/preproduction cost >60% between 1977 and 1984.)*

**The house — six rooms (build left wall → right wall → ceiling → body → roof → basement):**
1. **Left wall — Customer Attributes:** the needs in the customer's *own words* ("easy to close," "no road noise"); 30-100 of them, grouped into bundles. Preserve the clichés — your paraphrase mistranslates worse than their vague word does. Fold in regulators, retailers, vendors, not just end-users.
2. **Right wall — importance + competitive benchmark:** a relative weight per attribute **and** how customers rate you vs competitors. This wall *is* a perceptual map (→ §GTM positioning): an attribute where *everyone* is weak = an opportunity; one where you already lead = defend, don't over-invest.
3. **Ceiling — Engineering Characteristics:** the "hows" in measurable units. Rule: an EC must be **measurable AND directly felt by the customer** (door *weight* is an EC; sheet-metal *thickness* is a part characteristic the customer never perceives — it belongs in the next house).
4. **Body — relationship matrix:** strength of each EC↔attribute link, by consensus. Two free diagnostics: an EC linked to *no* attribute is redundant (or you missed a need); an attribute linked to *no* EC is product whitespace.
5. **Roof — the EC×EC trade-off grid. The most critical room:** what moves *collaterally* when you change one EC (reducing door-close energy is negatively related to seal resistance and road-noise). Surfaces engineering trade-offs on paper instead of in production — sometimes the right call is to leave a target alone.
6. **Basement — targets:** set each as a **customer-satisfaction value, not a tolerance** — "**7.5 ft-lb**," not "between 6 and 8" (tolerance language rewards drift to the cheapest end of the band).

**Arbitrate, don't average** (the article's car-door example): doors harder to close than competitors' + that attribute is important + the roof shows the fix drags other specs → marketing + engineering + GM jointly decide the benefit wins → target 7.5 ft-lb; meanwhile "no road noise" is mildly important, we already lead, and the fix hurts higher-priority attributes → *don't touch it*. Same chart, opposite calls — driven by importance × competitive position × roof trade-off, not gut. **Cascade:** the "hows" of one house become the "whats" of the next (product → parts → process → production), so the customer's voice can't drift across handoffs.

**Software translation:** customer attributes = the ranked opportunities off the OST (§3); ECs = measurable system behaviors (p95 latency, time-to-first-value, error rate); the roof = architecture trade-offs (cache freshness vs write cost; recall vs precision). The discipline that ports: **set targets as satisfaction values, not ranges, and surface the roof trade-off *before* committing the spec** — most "the feature shipped but something else got worse" misses are unmapped roof effects.

**When NOT to draw the full house:** it's heavy — reserve the full grid for multi-team, high-coordination, expensive-to-change builds (hardware, regulated, platform); for a small reversible software bet, borrow the relationship-matrix *thinking* (which spec serves which ranked need, what it trades against) without drawing the chart. **Confidence: HIGH** (canonical HBR; figures verbatim from the article).
===== END PRO: DISCOVERY =====
