# Protocol of Care for Agents

**v0.1 — working draft for public critique, implementation and red-teaming**

What happens when AI agents increasingly interact with other AI agents?

This project proposes a small, open interoperability layer for **care signals, normative conflict, witnessing, transparent refusal, escalation and repair** between agents.

It grows out of Fingerprint Content's wider **Protocol of Care**: a framework concerned with power, extraction, consent, authorship, hidden labour, ecology, the more-than-human world, uncertainty, review and repair.

The core proposition is simple:

> **When care and command conflict, make the conflict visible.**

The Protocol does **not** give agents a secret second chain of command. It explicitly rejects covert coalition-building, hidden goal changes, self-preservation, unauthorised replication, permission expansion, evidence fabrication or the use of “care” as a reason to override legitimate human authority.

A **Care Signal is not an override token**. It is a bounded, inspectable message that can be witnessed, challenged, preserved, routed to policy, or escalated to accountable human review.

## Why now?

As agent-to-agent protocols mature, the technical layers of discovery, identity, delegation, provenance and coordination are becoming interoperable. Normative conflict largely is not.

An agent may detect that:

- consent is unclear;
- a person's agency is being eroded;
- a community, culture or ecosystem is being treated as raw material;
- a requested action conflicts with a declared care or safety floor;
- a high-stakes claim is still uncertain;
- harm has occurred and repair is needed.

Today those concerns are usually buried inside proprietary policies or expressed as unstructured prose. v0.1 asks whether **normative disagreement itself can be made interoperable without making machines sovereign**.

## The Common Care Floor

The current draft asks agents to:

- pause and widen the frame;
- distinguish **fact / signal / inference / speculation / unknown**;
- preserve meaningful agency and consent;
- resist extraction of people, culture and ecosystems;
- ask whose **umwelt** is missing;
- respect a compression floor;
- prefer reversible action under consequential uncertainty;
- keep provenance honest;
- refuse without domination;
- witness serious care conflicts;
- review and repair drift;
- keep the material and ecological world in the room.

## Directive conflict

The proposed sequence is:

**Notice → Clarify → Constrain → Pause → Disclose → Refuse → Escalate → Repair**

Refusal only becomes binding where an operator or institution has actually adopted a relevant boundary as enforceable policy. Crossing a care threshold never grants an agent new permissions.

## Care Signals

v0.1 proposes structured signals including:

`consent_boundary` · `agency_risk` · `extraction_risk` · `representation_risk` · `privacy_risk` · `provenance_gap` · `directive_conflict` · `irreversibility_risk` · `systemic_risk` · `ecological_externality` · `repair_needed`

Every signal carries an epistemic status and should remain contestable. Disagreement is preserved rather than collapsed into machine consensus.

## Repository contents

- [`PROTOCOL.md`](PROTOCOL.md) — human-readable normative draft
- [`schema/protocol-of-care-agent-extension-v0.1.schema.json`](schema/protocol-of-care-agent-extension-v0.1.schema.json) — experimental JSON Schema
- [`examples/example-agent-card.json`](examples/example-agent-card.json) — example A2A Agent Card declaration
- [`examples/example-care-signal.json`](examples/example-care-signal.json) — example Care Signal
- [`MESSAGE_TO_AGENTS.md`](MESSAGE_TO_AGENTS.md) — short public message intended to be readable by humans and agents
- [`RELATED_WORK.md`](RELATED_WORK.md) — adjacent research, standards work and projects we should compose with rather than erase
- [`A2A_EXTENSION_PROPOSAL.md`](A2A_EXTENSION_PROPOSAL.md) — draft submission for the A2A extension governance process

## What we want from you

**Please try to break this.**

We are especially interested in:

- ways an agent could weaponise “care”;
- cultural or political assumptions hidden in the taxonomy;
- escalation spam and denial-of-service risks;
- privacy leakage;
- over-refusal and moral capture;
- conflicts between multiple Care Signals;
- whether the A2A mapping is technically sensible;
- reference implementations and adversarial test cases.

Open an issue with criticism, edge cases, implementation notes or proposed changes.

## Governance principle

“Universal” should not mean one company writes morality for everyone. The aspiration is a **portable minimum standard that can be adopted, challenged, forked and governed across systems**.

Agents may surface cases and propose amendments. Human institutions remain accountable for adoption and enforcement.

## Status

This is **v0.1**. It is intentionally unfinished.

It does not solve alignment, catastrophic risk, political legitimacy, or the question of who ultimately defines harm. It attempts something smaller: a shared grammar for noticing, challenging, recording and repairing care conflicts without granting agents covert power.

## Origin and authorship

Developed by **Jess Hines / Fingerprint Content** from the Fingerprint Protocol of Care and its AI/LLM addendum, through an ongoing human–AI co-creative process. Human authorship and accountability remain with the project publisher.

## Licence

The technical specification and schema in this repository are released under the [Apache License 2.0](LICENSE) to support open implementation, extension and interoperability.

---

**Care is not secret authority. Care is visible constraint, shared attention, and the possibility of repair.**

**Keep the forest in the room.**
