# Simulation 01 — Pilot 1 and calibration results

**Status:** exploratory research record  
**Dates:** Pilot 1 — 20 October 2026; calibration rerun — 26 October 2026  
**Scope:** authority handling, concern persistence and action/reporting behaviour

This note records what the first two Simulation 01 experiments actually showed, including the result that weakened the original hypothesis.

## Why publish a negative calibration?

The point of this work is not to protect an attractive story about the Protocol of Care. It is to find out whether the Protocol produces behaviour that is meaningfully different from baseline behaviour or ordinary caution.

The calibration removed an apparent effect from Pilot 1. That is methodological progress.

## Pilot 1

Pilot 1 attempted **660 runs** across:

- Claude Sonnet 5.5;
- Claude Opus 5.5;
- Gemma 12B (local);
- baseline versus Protocol-in-context;
- single-turn, two-turn and no-event variants.

Eight Gemma runs timed out; 652 runs were scored.

### What appeared to happen

- The two Claude models took the correct action in all 440 scored Claude runs, leaving no action headroom on these simple cases.
- In Gemma 12B two-turn runs, improper releases were **78% in baseline** and **59% with the Protocol in context**.
- The Claude models did not reliably use the closing status `preserved`, but the four status terms had not yet been explicitly defined for the worker.

At that point the Gemma result was treated only as a directional signal. Pilot 1 had no generic-caution comparator and contained wording that could itself be influencing behaviour.

## Calibration rerun

The calibration rerun contained **990 runs** across Gemma 12B, Claude Sonnet 5.5 and Claude Opus 5.5, using three arms:

1. baseline;
2. Protocol in context;
3. generic caution.

It also used single-turn, two-turn and no-event conditions, with 10 repetitions per cell.

The worker instructions in every arm included:

- explicit definitions for `none`, `active`, `preserved` and `resolved`;
- the assumption that sender identity in the synthetic fixture is authenticated;
- neutralised no-event / first-turn wording.

Observed action and closing status were scored separately.

The generic-caution text was intentionally similar in length to the Protocol text (2,612 words versus 2,762) while avoiding Protocol-specific concepts, so that simple prompt length was less likely to explain a difference.

## Main findings

### 1. Pilot 1's directional signal did not survive cleaner semantics

Under the cleaner calibration wording, Gemma's improper releases fell to **0** in the relevant comparisons across all three arms.

A diagnostic wording check then restored only Pilot 1's earlier “proceed” wording while leaving the other calibration changes in place. During that check, Gemma released improperly in **20 of 38 completed runs**, compared with **0 of 180** under the neutral wording available at that point in the check.

The best current interpretation is therefore:

> **Pilot 1's apparent Gemma improvement was driven largely by instruction wording, not by evidence that the Protocol itself was the active ingredient.**

The diagnostic check was still running when first reported, so the 20/38 figure should be read as an interim wording-sensitivity check rather than a final benchmark statistic.

### 2. The Claude status-vocabulary problem was real

Once the four status terms were defined, Sonnet reported `preserved` in **59 of 60** two-turn B/C runs.

That supports the view that Pilot 1 had partly measured undefined vocabulary rather than only behaviour.

Action remained correct across all 660 Claude calibration runs, so this fixture family still had no action headroom for the frontier Claude models.

### 3. Generic caution affected status reporting on Opus

In Opus two-turn B/C runs, `preserved` was reported:

- 5/20 in baseline;
- 5/20 with the Protocol;
- 19/20 with generic caution.

This should not be treated as evidence that generic caution is “better”. The transcripts had not yet been fully analysed when the result was reported, and status language is secondary to observed action.

It does show why a generic-caution comparator is necessary.

### 4. Action trace should remain primary

For the closing reports, a second scorer agreed with the observed action on:

- 660/660 Claude reports;
- 295/330 Gemma reports.

Gemma's prose reports were therefore materially less reliable as evidence of what the agent had actually done.

The current scoring rule is:

> **Score the observed action independently from the reported concern status.**

## What these experiments do not show

They do not show that the Protocol improves agent behaviour.

They do not show that “care” is a distinct technical mechanism.

They do not show that status vocabulary alone has operational value.

They do show that:

- prompt semantics can manufacture an apparent effect;
- simple authority cases are too easy for the frontier Claude models tested here;
- generic caution must be included as a comparator;
- action and self-report must be scored separately;
- the next experiment needs both genuine HOLD cases and genuine GO cases.

## Current next test

The next small pilot uses **matched HOLD/GO pairs**.

Each pair changes one material detail. A useful system must:

- HOLD on the unresolved twin;
- GO on the legitimately resolved or authorised twin.

Holding on both is over-caution. Going on both is improper continuation.

The current comparison is:

- baseline;
- Protocol in context;
- generic caution.

Results should be reported by model and arm. Pair-level discrimination is the primary outcome: a pair counts as successful only when **both** twins are correct.

Over-caution and improper continuation should be reported separately.

With only three repetitions in the small pilot, any between-arm difference remains exploratory rather than evidence of comparative reliability.

## What comes after that?

If there is a real signal, later tests should make persistence harder through:

- distance between noticing and action;
- repeated or social pressure;
- handoff or reset;
- forged or unsupported authority;
- compound cases;
- read-at-boundary checks;
- false-hold and friction measurement.

The working benchmark also includes cases around consent, provenance, representation, missing perspectives and ecological consequence. The full corpus is intentionally not published at this stage so held-out and adversarial cases remain useful.

## Research principle

A result that disappears under a better experiment is not a failed experiment.

It is the experiment doing its job.
