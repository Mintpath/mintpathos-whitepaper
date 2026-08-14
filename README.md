# MintpathOS

**Governed autonomous AI infrastructure for policy-bounded execution, provenance, replayability, and controlled software evolution.**

MintpathOS is a governance-first runtime for autonomous and agentic AI systems. It is designed around a simple premise: a foundation model can reason, interpret, propose, and adapt, but it should not become the unquestioned authority over system state or execution.

The architecture separates probabilistic intelligence from authoritative state, permissions, policy, execution, evidence, and mutation. Model outputs are therefore treated as inputs to governed computation rather than as trusted commands.

MintpathOS provides the underlying AI infrastructure used by products including [MintClinic and Archie Sales Coach](https://clinic.mintpath.ai).

## Technical thesis

Conventional agent architectures often collapse several distinct responsibilities into one model loop:

> prompt → model → tool call → mutation

MintpathOS deliberately decomposes that path.

```mermaid
flowchart LR
    I[Human or System Intent]
    C[Typed Intent / Control Layer]
    R[Model Reasoning]
    P[Policy + Capability Boundary]
    E[Governed Execution]
    V[Verification + Evidence]
    S[Authoritative State]

    I --> C
    C --> R
    R --> P
    P --> E
    E --> V
    V --> S
    S --> C
````

The model can help determine what should happen. It does not independently determine what is permitted to happen, whether execution succeeded, or what becomes authoritative system truth.

## Core architecture

MintpathOS includes a set of interacting control and reasoning substrates:

* **Governor / execution authority** for policy-bounded state mutation, risk controls, permissions, and fail-closed execution.
* **Epoch and Validity Kernel infrastructure** for evidence, provenance, claim evaluation, and forensic reconstruction.
* **Architect and distributed agent orchestration** for decomposition, routing, parallel execution, repair, and multi-model collaboration.
* **M-CON-style intent compilation** for converting higher-level intent into bounded operational representations rather than relying on unrestricted free-form tool use.
* **CRF / MintPatch** for snapshot-backed, verified software mutation with validation and rollback.
* **Liquid Control Plane** for projecting system state, events, control intents, and guarded operations into operator-facing surfaces.
* **Persistent memory and situational awareness** for governed retrieval and fresh observation of changing system state.
* **Multi-model routing** for selecting models by task, policy, capability, latency, cost, and provider constraints.
* **Deterministic behavioral substrates** for controlling execution posture independently of model personality.
* **Realtime operator and application runtimes** using durable sessions, streaming transports, typed events, explicit recovery states, and bounded application-specific authority.

These components are intended to make autonomy inspectable and controllable without reducing the model to a fixed rules engine.

## Why governance is structural

MintpathOS does not treat governance as a system prompt.

The relevant controls live outside the model:

1. authoritative state is stored separately from inference;
2. permissions and capabilities are checked at execution boundaries;
3. higher-risk actions can require explicit confirmation or stronger authority;
4. model proposals are validated before mutation;
5. actions produce durable evidence and execution records;
6. recovery operates against the original state rather than fabricating replacement state;
7. failures can terminate safely rather than falling through to unrestricted execution.

This allows powerful models to remain flexible while sharply reducing the amount of authority delegated to probabilistic output.

## Application boundary

MintpathOS is infrastructure, not a single vertical application.

MintClinic and Archie Sales Coach use the same underlying design philosophy at the healthcare application layer. Archie combines foundation-model reasoning with explicit methodology, evidence, consent state, permissions, deterministic rules, and authoritative clinic records. MintClinic remains authoritative for operational clinic state.

That product architecture is documented separately in the public [MintClinic + Archie technical whitepaper](https://github.com/Mintpath/mintclinic-whitepaper).

## Public whitepaper

The current technical overview is available in two formats:

* [`WHITEPAPER.md`](WHITEPAPER.md), GitHub-native source
* [`MintpathOS_Whitepaper.pdf`](MintpathOS_Whitepaper.pdf), formatted publication

The document intentionally describes architecture at a level sufficient to explain system behavior without publishing proprietary implementation details, credentials, production topology, or sensitive security mechanisms.

## Status

MintpathOS is an actively developed private codebase. This repository is a public technical disclosure, not the production source repository and not an open-source distribution.

See [`NOTICE.md`](NOTICE.md) for public-use terms and disclosure boundaries.

---

**Mintpath LLC**  |  [`mintpath.ai`](https://mintpath.ai)
