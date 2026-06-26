===== BEGIN PRO: AI-EVALS =====
Load when: you're standing up evals for an LLM/AI feature — eval plan, error analysis, LLM-judge validation, MVQ bar, shadow-mode rollout. Base §AI-Native gives the doctrine; this gives the executable depth, templates, and a worked pass. Framework spine unchanged: Husain & Shankar (hamel.dev evals-faq, Field Guide), Khan (Arize, Lenny's), Shankar et al. arXiv:2404.12272, Nika (MVQ, AI product sense) & Granados (AIPDL, AI-PM archetypes). All `~` numbers are directional / point-in-time — calibrate to your data.

## 1. End-to-end eval plan (fill-in)
Copy this, fill every slot. If a slot is blank you don't have a spec, you have a vibe.
```
FEATURE: ____   JOB-TO-BE-DONE (Christensen): When I __, I want to __, so I can __.
"GOOD" DEFINED FOR (audience): ____   (helpful differs per persona — base §AI-Native)
HARD CONSTRAINTS (assert up front, no judge): valid JSON | never names competitor | no PII | ____
MVQ BAR (§7): do-not-ship = ___ | acceptable = ___ (+fallback) | delight = ___
COST ENVELOPE (§7): $___ /successful task ceiling · p95 latency ___ ms
DATASET: ~100 representative traces from ____ (real ⟶ preferred; else synth via dims ____)
FAILURE TAXONOMY: discovered from data (§3) — NOT authored upfront
JUDGE: binary pass/fail + critique; validated vs human labels (§4); TPR/TNR reported
OFFLINE (CI): golden set N=___, deterministic asserts + judge, runs every change (§5)
ONLINE (prod): sample ___% live traces, reference-free judge, CIs, weekly review (§5)
ROLLOUT: shadow → internal → cohort %; kill-switch = ___ (§10)
OWNER: PM owns taxonomy + "what good means" + golden labels; eng owns harness/CI.
```

## 2. Loop (Husain & Shankar) — analyze → measure → improve, NOT test-first
Failure surface is ~infinite; don't write evals before you've seen failures. Ship thin → collect traces → error-analyze → build an evaluator ONLY for an observed failure mode → re-run every change. Exception: the hard constraints above (assert up front). Error analysis is ~60-80% of dev time, by hand (directional).

## 3. WORKED error-analysis pass (illustrative numbers)
Feature: AI mortgage-doc summarizer for first-time homebuyers. 100 traces, domain-expert reads each, free-text note on the FIRST thing that went wrong (upstream errors cause downstream symptoms — code the head).

Open-coding notes (sample, verbatim style):
- "invented an APR figure not in the source doc"
- "refused — said 'consult a financial advisor' instead of summarizing"
- "summary correct but 1100 words, user wanted the gist"
- "missed the prepayment-penalty clause entirely"
- "used 'amortization' with no plain-English gloss — wrong for first-timer"
- "JSON broke — trailing comma"

Axial coding → failure taxonomy + counts (cluster notes until saturation, ~20 traces with no new bucket; an LLM can propose groupings, you refine):
| Failure mode | Count /100 | Hurts? | → Targeted eval |
|---|---|---|---|
| Hallucinated number (APR, fee) | 14 | critical (trust/legal) | judge: every figure traceable to source |
| Missed material clause | 11 | critical | checklist eval vs clause list |
| Over-length / not "the gist" | 23 | medium | deterministic: word-count ≤ 200 |
| Jargon unglossed for persona | 9 | medium | judge: persona-appropriate language |
| Unhelpful refusal | 6 | high | judge: refused a benign request? |
| Format break (JSON) | 4 | low (assert) | deterministic schema check |
| No issue | 33 | — | — |
Read: build evals for the rows that *hurt*, not all of them. The 23 over-length cases are cheap to fix (a deterministic assert, no judge). The 14 hallucinated numbers are the real spec — that's the MVQ do-not-ship line. Then 10-20 fresh traces/week to catch drift and new modes. 100% pass = system not challenged.

## 4. LLM-as-judge validation protocol
A judge is a prompt with its own error rate — unvalidated, it manufactures false confidence.
1. Binary pass/fail + written critique. NOT 1-5 Likert (adjacent points are noise; annotators camp the middle → criteria drift, Shankar et al. arXiv:2404.12272).
2. PM hand-labels a held-out set (~50-100 traces, the benevolent-dictator labeler — multiple annotators = noise).
3. Run judge on the same set. Build the confusion matrix (treat "fail/bug found" as positive):
```
                 human=FAIL   human=PASS
   judge=FAIL        TP           FP
   judge=PASS        FN           TN
   TPR = TP/(TP+FN)  (catches real failures)
   TNR = TN/(TN+FP)  (doesn't cry wolf on good outputs)
```
   Worked (illustrative): TP 40, FN 5, TN 48, FP 7 → TPR 0.89, TNR 0.87. Report BOTH — no single fixed % is canonical; iterate the judge prompt until both are high enough for the stakes. A judge with high TPR but low TNR floods you with false alarms; high TNR low TPR ships bugs.
4. Bias controls: **position** (randomize A/B order in pairwise judging), **verbosity** (judge prefers longer answers — control length or instruct against it), **self-preference** (models favor their own output — don't let the generator judge itself). Prefer a **panel of judges** (e.g. 3 different models, majority/average) over one.
5. Re-validate the judge whenever you change its prompt or swap the model behind it.

## 5. Offline (CI) vs Online (prod) — EDDOps
| | Offline / CI | Online / prod |
|---|---|---|
| Dataset | small curated golden set | sampled live traces |
| Evaluators | deterministic asserts first, then validated judge | reference-free judges (no ground truth) |
| Cadence | every commit / prompt / model swap | continuous sample + weekly failure-mode review |
| Watch | pass-rate per failure mode, regression count | track CIs, drift, new failure clusters → promote back to golden set |
EDDOps (eval-driven dev): the golden set is the regression suite; prod failures flow back into it. This is the AIPDL "deployment ≠ completion" stage (Nika & Granados) made operational — monitoring/iteration is a *stage*, not an afterthought, because models drift and inputs shift.

## 6. Golden set + regression promotion
Small, curated, labeled inputs + pass/fail — high-signal, not big. Construction: seed from the error-analysis traces (one canonical example per failure mode + clear passes), balance across the synth dimensions, label personally. **Promotion rule:** every new production failure → minimal reproducing input → permanent regression case in the golden set, labeled, with the date and the failure mode it guards. The set only grows; you never delete a regression case.

## 7. MVQ tier worksheet (Nika) + cost envelope
Set the bar per feature BEFORE building. (Numbers are a contextual rule of thumb, not a standard.)
| Tier | Definition | This feature (fill) | Ships? |
|---|---|---|---|
| do-not-ship | fails a hard constraint or erodes trust | any hallucinated number | block |
| acceptable | ships with fallback / human-in-loop | ≥8/10 right, no-retry; misses caught by human review | ship w/ fallback |
| delight | autonomous, near-perfect | ≥9.5/10, no material-clause misses | raise threshold per version |
Rule of thumb (directional): ~8-9/10 right with no retry feels magical; ~1-in-5 visible misses erodes trust. Quality ceiling rises across versions — V1 launches with human-in-loop fallback and you set leadership/customer expectations on that ceiling up front (an optics deliverable, not just an eng note).
Cost-per-inference envelope: `(tokens_in·$ + tokens_out·$ + infra) ÷ resolved jobs ≤ $___`. Delight that loses money per successful task doesn't ship (base §Metrics tier 3). Hold this envelope when pricing on outcomes — model cost is variable COGS.

## 8. Non-generative ML — classification metrics (when to use each)
For ranking/scoring/extraction/risk models, evals are classification metrics, not judges:
| Metric | Use when | Trap |
|---|---|---|
| Precision = TP/(TP+FP) | false positives are costly (spam flag, fraud block) | ignores misses |
| Recall = TP/(TP+FN) | false negatives are costly (disease, churn, AML) | ignores false alarms |
| F1 = harmonic mean(P,R) | need one number, classes imbalanced | hides which error dominates — report P and R too |
| ROC-AUC | threshold-independent ranking quality | optimistic on heavy class imbalance → prefer PR-AUC there |
Pick by which error hurts more — precision/recall is a business call, not a default. For clinical/credit/regulated features add a **demographic bias/fairness evaluation across segments** (base §Calibration: fairness is a guardrail, not an afterthought).

## 9. Three Gulfs (Shankar & Husain) — what each eval artifact attacks
| Gulf | Meaning | Attacked by |
|---|---|---|
| Comprehension | you can't read all your data | error analysis on a 100-trace sample; online sampling |
| Specification | intent → prompt is lossy | golden set + validated judge = the real spec; criteria pinned, not drifting |
| Generalization | works on seen inputs, fails on unseen | fresh weekly traces; shadow-mode at scale; regression promotion |

## 10. Shadow-mode rollout + kill-switch (Nika)
Run AI silently alongside the human/incumbent to gather at-scale eval data at zero customer risk, THEN widen.
```
Stage 0 SHADOW   AI runs, output logged, NOT shown. Compare vs human on live volume.
                 GATE: offline pass-rate holds on real traffic; no new critical mode.
Stage 1 INTERNAL dogfood; PM + experts review daily.
Stage 2 COHORT   feature-flag X% (start ~1-5%, directional). Monitor MVQ tiers + cost.
Stage 3 WIDEN    raise % only while online judge pass-rate + cost envelope hold.
```
Kill-switch (define BEFORE Stage 2): auto-rollback trigger = do-not-ship rate > ___% OR cost/task > envelope OR latency p95 > ___ OR a critical-mode spike. Flag flip = instant revert to human/previous version, no redeploy. Name the owner who can pull it and the alert that pages them — a kill-switch nobody can see fire is a silent failure (actor-observability). Post-rollback: capture the failing input as a regression case (§6) before re-attempting.

Pitfalls: generic off-the-shelf "helpfulness" judge = vanity; "evals are the new PRD" is useful folklore (Foody/Braintrust) — the spec is *discovered from data*, not authored upfront.
===== END PRO: AI-EVALS =====
