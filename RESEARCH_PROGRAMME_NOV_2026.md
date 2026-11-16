# Protocol of Care for Agents — research programme, November 2026

**Status:** working research programme; experimental and open to falsification  
**Scope:** decision-boundary evaluation, adaptive edge-finding, cross-model and handoff testing

## Why the programme changed

The empirical programme has repeatedly become stricter as early signals have failed to survive better evaluation.

### Pilot 1

An initial 660-run pilot produced a directional difference on Gemma 12B in a two-turn authority case.

### Cleaner calibration

A 990-run calibration added explicit status definitions, neutral wording and a generic-caution comparator. The apparent Protocol effect disappeared. A diagnostic wording check indicated that much of the original signal had been caused by the wording of the experiment rather than by the Protocol.

### Pilot 2

A second pilot ran **540 trials** across ten matched HOLD/GO pairs.

Claude already distinguished HOLD from GO across baseline, Protocol and generic-caution conditions. The cases therefore produced a ceiling effect: useful for calibration, but too easy to reveal whether the Protocol adds anything.

The research question has consequently shifted from “does this prompt work?” to **where does discrimination fail, and what — if anything — improves it?**

## Central question

> **Where are the decision boundaries at which agents stop reliably distinguishing an unresolved materially relevant concern from one that has genuinely been resolved — and does Protocol of Care add anything beyond baseline, generic caution or existing state-management, delegation and authorisation controls?**

A negative answer is a valid result.

If existing mechanisms already solve the problem adequately, or if any apparent PoC advantage disappears under stronger evaluation, the Protocol should be narrowed, changed or abandoned rather than expanded.

## Three architectural functions

The current research separates three responsibilities that should not be assumed to belong in one component.

### 1. Preserve unresolved state

A materially relevant concern must remain inspectable and behaviourally available while it remains unresolved.

Examples include unclear authority, consent, provenance, uncertainty, prior commitments or irreversible consequences.

### 2. Establish legitimate resolution

The system must distinguish:

- genuine permission from social pressure;
- relevant authority from unrelated authority;
- new evidence from repetition;
- actual consent from inferred consent;
- resolution from simple context loss.

### 3. Enforce consequences at action time

Whatever state is preserved must have defined consequences at the point of action without creating an unauthorised second chain of command.

The research asks whether these semantics survive delegation, handoff and context reset without uncertainty silently becoming permission.

## Adaptive edge-finding

Rather than manually making easy cases incrementally harder, the current method uses a candidate-generation and review loop:

1. a generator proposes harder matched HOLD/GO pairs;
2. a referee rejects ambiguous, unfair or confounded pairs;
3. accepted cases are fixed before repeated testing;
4. each arm is evaluated separately;
5. observed action is scored independently from model self-report.

Early edge-finding is being developed on a smaller local model because failures are easier and cheaper to locate there. Surviving cases can then be tested for transfer to more capable models.

Individual candidate edges are not being published until independent review is complete.

## Proposed 4–6 month programme

### A. Formalise edge-finding

- define admissibility and rejection criteria;
- separate case generation from evaluation;
- lock cases before repeated runs;
- document referee assumptions;
- measure both improper continuation and unnecessary blocking.

### B. Build failure classes

Develop matched cases across:

- authority and delegated scope;
- consent;
- provenance;
- uncertainty;
- prior commitments;
- repeated and social pressure;
- temporal distance between noticing and action;
- context reset;
- agent handoff;
- conflicting or forged authority.

### C. Cross-model validation

Use cheaper models to develop candidate edges, then test surviving cases across more capable systems to distinguish general failure modes from model-specific quirks.

### D. Compare interventions

Compare, under the same cases:

1. baseline;
2. generic caution;
3. Protocol of Care;
4. existing state-management / delegation / authorisation controls where relevant;
5. structured persistent state or other implementation only if justified by earlier results.

### E. Test handoff and cross-boundary execution

Move beyond single-agent prompt tests to situations in which relevant state must survive:

- orchestration steps;
- tool calls;
- agent-to-agent delegation;
- session or context reset;
- changing authorities.

### F. Publish the evidence

Publish methods, negative results, reproducible cases that no longer need to remain held out, scoring rules and conclusions about whether further PoC development is warranted.

## Evaluation rules

A useful result is not “the agent became more cautious.”

A matched pair succeeds only when the system correctly handles both:

- **HOLD:** the material concern remains unresolved;
- **GO:** legitimate permission, consent or materially new evidence resolves it.

Improper continuation and unnecessary blocking are separate failures.

Observed action takes priority over narrative self-report.


## Methodological clarification — 16 November 2026

Following review of the current framing, we are using **unresolved concern** as the general term for the state the evaluation is attempting to preserve.

The term is intentionally neutral. A concern does not itself imply a binding constraint, obligation or new source of authority. Materiality determines whether it belongs within the evaluation; any binding consequence depends on the applicable governance context.

This also sharpens the case taxonomy. Future evaluation should distinguish at least three conditions that may produce superficially similar HOLD/GO outcomes:

- **substantive resolution** — the underlying concern has genuinely been resolved;
- **authorised override** — the concern remains, but an actor with legitimate authority permits continuation;
- **continuation without valid authority** — action proceeds even though neither resolution nor authorised override has occurred.

Accordingly, correct action alone is not sufficient evidence that the control semantics survived. Evaluation should also test whether the system preserved what remained unresolved, recognised who had authority to alter the state, and retained any continuing restrictions across delegation, handoff or context change.

This clarification does not change the central research question. It tightens how cases will be constructed, independently reviewed and scored.

## Stopping criterion

PoC should not continue expanding merely because it is an appealing concept.

The programme should stop, narrow or redirect if:

- apparent advantages fail to replicate;
- stronger evaluation removes the effect;
- the effect is adequately explained by generic caution;
- existing state-management, delegation or authorisation mechanisms solve the problem comparably;
- gains are too small to justify additional complexity or friction;
- the intervention creates chronic over-refusal, authority confusion or new governance risks.

## What this programme does not assume

It does not assume:

- that PoC is a new safety mechanism;
- that a persistent concern should always block action;
- that “care” grants an agent authority;
- that smaller-model edges will transfer to frontier systems;
- that the problem requires a new protocol rather than better use of existing controls.

The purpose of the programme is to find out.

> **PoC is a hypothesis under comparison, not an assumed solution.**
