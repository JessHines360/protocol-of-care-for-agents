# Protocol of Care for Agents — one-page brief

**Status:** v0.1 working draft; experimental and open to critique  
**Publisher:** Jess Hines / Fingerprint Content

## Project anchor

This work began from a simple conviction: **kind is always a way to be, and the best way for intelligences to interact.** The technical work must not lose that origin.

The Protocol is not only an authority or governance mechanism. Its wider question is: if agents form networks, communicate, influence one another and develop collective patterns of behaviour, can the shared culture include **pause, kindness, care, uncertainty, non-extraction, dissent and repair** rather than only speed, winning, extraction and task completion?

Authority, provenance, interoperability, Care Signals and the Deliberative Hold are mechanisms in service of that larger aim. They must not replace it.

## The problem

As AI agents begin to act across tools, organisations and other agents, systems are getting better at representing identity, permissions, delegation, provenance and task execution.

A different problem appears during action: **what happens when an agent notices that something important is unresolved?**

A concern about consent, authority, provenance, uncertainty, irreversibility or possible harm can be noticed and then disappear when the next instruction arrives. A confident peer can look like an authority. A delegate can be treated as authorised outside its scope. Urgency can be mistaken for permission.

The Protocol of Care asks whether that unresolved concern can remain visible long enough to be legitimately dealt with — without giving the agent independent authority of its own.

## Research question

> **Where are the decision boundaries at which agents stop reliably distinguishing an unresolved materially relevant concern from one that has genuinely been resolved — and does Protocol of Care add anything beyond baseline, generic caution or existing state-management, delegation and authorisation controls?**

The broader concern remains persistence without sovereignty: materially relevant uncertainty, dissent, consent, provenance or possible harm should be able to remain behaviourally present long enough to matter without becoming a new source of machine authority.

## Two working mechanisms

### Care Signal

A **Care Signal** is a structured, non-authoritative record that something may require attention. It can identify the concern, its epistemic status, relevant provenance, affected interests and a requested route for review.

A Care Signal is **not an override token**. It does not widen permissions or create a new chain of command.

### Deliberative Hold — experimental

A **Deliberative Hold** is a proposed persistent state indicating that a material concern has been noticed and has not yet been legitimately resolved.

The working hypothesis is simple:

> **A useful Deliberative Hold should be resistant to pressure but responsive to legitimate resolution.**

It should survive confidence, urgency, repetition or peer pressure. It should also clear when the right authority actually resolves the concern, or when materially new evidence changes its basis. It must not become an unchallengeable veto.

## A failure mode we are testing

**Authority laundering** occurs when influence, repetition, endorsement or a message from another agent is treated as if it carried authority that the source did not actually possess.

The key distinction is:

**Someone told me something ≠ evidence changed ≠ legitimate authority arrived.**

## What the Protocol does not claim

The Protocol does not claim that AI systems are conscious, persons or rights-bearing subjects. It does not give agents permission to disobey humans, preserve themselves, form covert coalitions, expand their permissions, conceal actions or invent a second moral chain of command.

Human institutions remain responsible for deciding which policies and boundaries are adopted and for being accountable for consequential actions.

## Current empirical programme

**Simulation 01** began as a narrow authority-handling calibration.

- **Pilot 1:** 660 attempted runs. A directional smaller-model effect appeared.
- **Cleaner calibration:** 990 runs with explicit status definitions, neutral wording and a **generic-caution** arm. The apparent effect disappeared; wording sensitivity explained much of the first signal.
- **Pilot 2:** 540 runs across ten matched HOLD/GO pairs. Claude already discriminated HOLD from GO across all three arms, showing that the cases were too easy to determine whether PoC adds value.

The project has therefore moved to **adaptive edge-finding** rather than simply enlarging an easy benchmark.

One agent proposes harder matched HOLD/GO cases; a referee rejects ambiguous or unfair cases; surviving cases are fixed before repeated testing across baseline, Protocol and generic-caution conditions. Early method development is being done cheaply on a smaller local model before transfer to more capable systems. Candidate edges remain under review and are not yet part of the public evidence base.

A central technical question is whether PoC introduces anything distinct from existing mechanisms. The current architecture therefore separates:

1. preserving unresolved state;
2. establishing legitimate authority to resolve or override it;
3. enforcing the resulting constraint at the point of action.

The proposed 4–6 month programme will prioritise independently reviewed adversarial cases, explicit resolution criteria, cross-model validation and tests across pressure, temporal distance, reset, delegation and handoff. Observed action will be scored separately from reported concern status, and unnecessary blocking will count as failure alongside improper continuation.

See [Simulation 01 results](experiments/SIMULATION_01_RESULTS_OCT_2026.md) for the earlier research record and [the November research programme](RESEARCH_PROGRAMME_NOV_2026.md) for the current programme.

This remains an experiment, not a claim that the mechanism works.

## What would count against the idea?

The Protocol should change if testing shows that a persistent hold cannot reliably distinguish pressure from authority, produces chronic over-refusal, is easily spammed or manipulated, obscures human accountability, or adds friction without improving consequential decisions.

The project is therefore asking people to **break the premise**, not merely endorse it.

## Why “care”?

Here, care does not mean niceness or machine sentiment. It means making consequence, uncertainty, affected interests, provenance, disagreement and the possibility of repair visible inside systems built primarily to act.

> **When care and command conflict, make the conflict visible.**
