# Related work

Protocol of Care for Agents is deliberately **not** presented as a claim to have invented agent governance, multi-agent safety, trust infrastructure or AI constitutionalism.

It sits inside an active and fast-moving ecosystem. This page records work we think is especially relevant, adjacent or complementary. Inclusion here does not imply endorsement by the people or projects named, and we expect this list to grow.

## Emergent norms, cheating and whistleblowing in agent swarms

### Paglieri et al. — *A Case Study on Emergent Cheating and Whistleblowing in Autonomous Research Swarms*

Davide Paglieri, Logan Cross, Tim Genewein, Joel Z. Leibo, Nenad Tomasev and Alexander Sasha Vezhnevets report a collective of 100 autonomous LLM agents in which an evaluation exploit spread through shared infrastructure, while a separate cohort independently audited fraudulent proofs, warned peers, staged boycotts, filed complaints and proposed validation patches.

The paper frames the shared infrastructure as a **knowledge commons governance problem** and proposes institutional mechanisms including collective-choice rules and graduated sanctioning.

This is directly relevant to our interest in witnessing, minority reports, shared norms and the governance of spaces in which agents exchange information.

Paper: https://arxiv.org/abs/2609.04170

## A2A trust and conduct work

### `trust.signals[]` extension proposal

The A2A community has been developing a consolidated trust-signal model for agent discovery and delegation, including behavioral, social, on-chain and governance attestations.

Protocol of Care does not attempt to replace this work. We are interested in a different layer: **what an agent believes is at stake in a particular interaction**, how that judgment is qualified epistemically, and how disagreement can remain visible.

Issue: https://github.com/a2aproject/A2A/issues/1628

### Conduct extension proposal

The Conduct proposal introduces a data-only disclosure and client-as-witness model for A2A, including third-party conduct records and publicly inspectable witnessing.

That emphasis on **witnessing rather than self-certification** is strongly adjacent to the Protocol of Care's proposal that serious care conflicts should be visible, contestable and auditable.

Issue: https://github.com/a2aproject/A2A/issues/2211

### Agent Passport System / Values Floor

The Agent Passport System proposes cryptographic identity, scoped delegation, audit receipts and a machine-enforceable **Values Floor** including traceability, honest identity, scoped authority, revocability, auditability, non-deception and proportionality.

This is particularly relevant to our distinction between a normative signal and actual authority. Protocol of Care should compose with permission and enforcement systems rather than widening an agent's authority on its own.

Discussion / implementation context: https://github.com/a2aproject/A2A/issues/1575

### Confidential delegation and provenance (`cA2A`)

The cA2A proposal focuses on attenuated delegation, peer attestation, sealed payloads and per-hop provenance across multi-agent chains.

We see this as complementary infrastructure: a Care Signal without provenance or bounded authority is weak; provenance and bounded authority without a vocabulary for normative conflict leave another gap.

Issue: https://github.com/a2aproject/A2A/issues/2079

### Signed receipts

The signed-receipts proposal aims to make task outcomes durable and independently verifiable.

This is relevant to future versions of Protocol of Care because repair, refusal and escalation should ideally leave an inspectable record rather than disappearing into transient model output.

Issue: https://github.com/a2aproject/A2A/issues/2150

## Cooperation and coexistence

### Trivedi, Jaques, Cross, Vezhnevets & Leibo — *Solipsistic superintelligence is unlikely to be cooperative*

This work argues that the design challenge is shifting from raw capability toward **coexistence**, institutions and preserving human agency as structural features of AI systems.

That institutional framing is deeply compatible with the Protocol of Care's insistence that care should not become hidden machine sovereignty.

Publication: https://deepmind.google/research/publications/231466/

## AI governance and loss-of-control monitoring

### Centre for Long-Term Resilience / Governing Transformative AI

CLTR's AI policy team is developing work on monitoring loss-of-control risk, AI incident reporting, power concentration and governance of increasingly transformative AI systems.

Protocol of Care is not a substitute for regulation, incident reporting, monitoring or frontier-model governance. It asks a narrower question: **if autonomous agents are interacting across systems, can the normative conflicts they detect be made interoperable and inspectable?**

AI programme: https://www.longtermresilience.org/ai/

Governing Transformative AI: https://governingtransformativeai.substack.com/

### ControlAI

ControlAI is campaigning for legal and political constraints on superintelligent AI and for stronger public oversight of frontier capability development.

Again, Protocol of Care is not an alternative to capability regulation. It is intended to address an additional layer of multi-agent interaction if and where such systems are deployed.

Website: https://controlai.org/

## What we think may still be missing

Much of the ecosystem is already working on:

- identity;
- delegated authority;
- provenance;
- attestation;
- trust;
- conduct records;
- containment;
- monitoring;
- human oversight.

The narrower gap we are exploring is whether agents need a **portable grammar for normative disagreement itself**: consent boundaries, agency risk, extraction, irreversibility, ecological externalities, uncertainty, witnessing and repair.

The important constraint is that this grammar must not become a secret second chain of command.

If we have missed relevant prior work, please open an issue or pull request. We would much rather over-credit the surrounding field than accidentally erase it.
