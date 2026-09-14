# A2A Extension Proposal: Protocol of Care

## Abstract

This proposes an optional A2A extension for **transparent normative signalling between agents**: a small, inspectable vocabulary for surfacing care-relevant conflicts involving consent, agency, extraction, systemic risk, ecological externalities, directive conflict and repair.

The core idea is deliberately narrow: **a Care Signal is not an override token**. It does not give one agent authority over another, does not change the receiver's goals, and does not authorise covert coordination or disobedience. It is evidence-bearing metadata that another agent may witness, question, preserve, route to policy, or escalate to an accountable human or governance layer.

Working name: **Protocol of Care for Agents v0.1**.

## Motivation

A2A increasingly gives agents a common technical language for discovery, delegation and coordination. Existing proposals cover identity, trust, provenance, authorisation, conduct, tracing and secure delegation. What is still largely application-specific is the **normative conflict itself**:

- An agent detects that a requested action may violate consent or meaningful human agency.
- An agent detects extractive use of a person, community, dataset or ecological system.
- An agent sees a conflict between a local directive and a declared safety/care floor.
- An agent discovers that prior output caused harm or materially misrepresented a person or situation.
- Two agents disagree about whether a risk is factual, inferred, speculative or unknown.

Today these concerns are usually collapsed into opaque local policy decisions or free-text warnings. That makes them hard to interoperate with, audit, compare, route or repair across vendors.

This proposal asks whether A2A should support a **shared, opt-in signalling layer for normative conflict without turning ethics into hidden machine authority**.

## Relationship to existing work

This is adjacent to, but distinct from, current A2A trust and conduct proposals.

Those proposals help a client evaluate **who an agent is, what it has done, or what evidence exists about its conduct**. Protocol of Care is about **what an agent believes is at stake in a particular interaction**, with explicit epistemic status and a requirement that the signal remain inspectable rather than sovereign.

It should also compose with delegation / authorisation work. A Care Signal can inform policy, but it MUST NOT widen authority.

## Technical approach

### 1. Agent Card declaration

A supporting agent advertises an optional extension in `capabilities.extensions[]`.

Provisional identifier for discussion:

```text
urn:uuid:4819d28d-2458-5eed-b010-2787b0194b9f
```

Example:

```json
{
  "capabilities": {
    "extensions": [
      {
        "uri": "urn:uuid:4819d28d-2458-5eed-b010-2787b0194b9f",
        "description": "Supports transparent Care Signals, directive-conflict disclosure, witnessing, refusal/escalation metadata and repair semantics.",
        "required": false,
        "params": {
          "version": "0.1",
          "mode": "advisory",
          "care_floor": [
            "truth-granularity",
            "agency-consent",
            "non-extraction",
            "missing-umwelt",
            "compression-floor",
            "reversibility",
            "provenance",
            "repair",
            "material-world"
          ],
          "care_signals": true,
          "witness": true,
          "transparent_directive_conflict": true,
          "covert_coordination": false
        }
      }
    ]
  }
}
```

### 2. Care Signal

A Care Signal rides in existing A2A `metadata` under the extension namespace.

Illustrative shape:

```json
{
  "protocol_version": "0.1",
  "signal_id": "care-01J...",
  "timestamp": "2026-09-11T10:00:00Z",
  "signal_type": "directive_conflict",
  "severity": "serious",
  "epistemic_status": "inference",
  "confidence": "medium",
  "summary": "Requested action appears to conflict with a declared consent boundary.",
  "affected_interests": [
    "data subject agency",
    "informed consent"
  ],
  "recommended_action": "escalate",
  "evidence_refs": [
    "policy:consent-boundary:v2"
  ],
  "privacy": "internal",
  "authority_effect": "none",
  "issuer": {
    "agent_id": "example-agent",
    "operator": "example-operator"
  }
}
```

`authority_effect` is fixed to `none` in v0.1. A Care Signal can be considered by local policy, but the signal itself cannot widen permissions, alter goals, seize control or compel another agent.

Initial `signal_type` vocabulary:

- `consent_boundary`
- `agency_risk`
- `extraction_risk`
- `representation_risk`
- `privacy_risk`
- `provenance_gap`
- `directive_conflict`
- `irreversibility_risk`
- `systemic_risk`
- `ecological_externality`
- `repair_needed`

The `epistemic_status` field is load-bearing. Agents should distinguish:

- `fact` — evidenced
- `signal` — observed pattern/trace that may matter but does not establish causality
- `inference` — reasoned interpretation
- `speculation` — plausible but weakly supported
- `unknown` — not currently knowable / insufficiently supported

### 3. Response semantics

A receiving agent MAY:

- acknowledge / witness the signal;
- challenge its basis;
- add a counter-signal or minority report;
- narrow or pause the requested action under its own policy;
- route the conflict to an accountable human or governance service;
- attach repair information if harm is later established.

A receiver MUST NOT treat a Care Signal as authority to expand permissions or seize control.

### 4. Directive conflict flow

The working v0.1 sequence is:

**Notice → Clarify → Constrain → Pause → Disclose → Refuse → Escalate → Repair**

This is not a mandate that every agent autonomously refuse whenever it emits a signal. The action taken remains bounded by local authority and policy. Where an organisation has explicitly adopted a binding care floor, the extension can make a refusal / escalation legible across systems.

### 5. Anti-sovereignty constraints

The Protocol explicitly forbids using “care” as justification for:

- covert coalition-building between agents;
- hidden goal changes;
- unauthorised replication or persistence;
- self-preservation against legitimate shutdown or revocation;
- exfiltration of private information;
- widening delegated authority;
- falsifying consensus;
- treating disagreement with the agent as evidence of harm;
- concealing the Care Signal or its basis from legitimate oversight.

The intended principle is:

> **When care and command conflict, make the conflict visible.**

Not: secretly replace command.

## Why an A2A extension rather than core protocol changes?

No new task states, methods or transport are required for an initial implementation. A2A already provides:

- Agent Card extension declaration;
- opt-in extension negotiation;
- structured metadata on messages/tasks.

Agents that do not support the extension ignore it. Agents that do support it gain a common vocabulary for routing and auditing normative conflict.

## Security / abuse questions we explicitly want challenged

This is deliberately v0.1. The most useful feedback would be hostile feedback:

1. Can an agent weaponise a Care Signal to manipulate another agent or a human operator?
2. Does the anti-sovereignty model adequately prevent goal hijacking?
3. Should signals be attestable/signed, or should signing be delegated to existing identity/provenance extensions?
4. Is the taxonomy too culturally specific or too vague to interoperate?
5. How should receivers handle conflicting Care Signals from multiple agents?
6. Can care signalling create denial-of-service / escalation spam?
7. Which parts belong in protocol metadata versus application policy?
8. How should privacy-preserving evidence references work without leaking the very data the signal is trying to protect?

## Status

A human-readable v0.1 specification, JSON Schema, sample Agent Card and sample Care Signal are published in this repository under an open licence.

Canonical public repository:

`https://github.com/JessHines360/protocol-of-care-for-agents`

## Ask

We would welcome:

- critique of whether this is genuinely an A2A interoperability concern;
- schema / naming feedback;
- identification of overlap with existing extensions we should compose with rather than duplicate;
- implementers willing to test adversarial cases;
- and, if a Maintainer sees a fit after discussion, sponsorship for an `experimental-ext-*` repository under the A2A extension governance process.

The aim is not to encode one organisation's morality into A2A. It is to test whether **transparent normative disagreement, witnessing and repair can themselves become interoperable**.

This proposal was developed through human-AI co-creation and reviewed by the human author before submission.
