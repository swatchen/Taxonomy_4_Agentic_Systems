# T4AS Spec Package Directory

Below is the full hybrid Spec-Up + Spec-Up-T specification package for **Taxonomy for Agent Systems (T4AS)**, rendered as a virtual directory within this canvas. All files appear as sections, preserving the folder structure.

---

# /spec/Taxonomy-for-Agent-Systems.md

## Spec Metadata

```spec-up
spec:
  id: t4as
  title: Taxonomy for Agent Systems
  version: 0.3
  status: draft
  authors:
    - name: Stephen Vitka
      email: stephen.vitka@gmail.com
  dependencies:
    - ocap
  abstract: |
    A formal taxonomy for disambiguating and structuring the architecture of modern agent systems. It defines the Architectural Triad — Agent, Workflow, Workspace — and specifies the compositional, executable, and certifiable relationships between these elements.
```

---

# 1. Introduction & Rationale

The **Taxonomy for Agent Systems (T4AS)** establishes a formal vocabulary and structural model for describing modern agentic AI systems. Rapid development of autonomous and semi-autonomous AI has created a heterogeneity of architectures lacking standardized terminology. T4AS provides clarity through a precise taxonomy, centered on the **Architectural Triad**:

* **[[xref:Agent]]** — the generator
* **[[xref:Workflow]]** — the orchestrator
* **[[xref:Workspace]]** — the environment

This separation underpins security boundaries, auditability, and scalable composition.

---

# 2. Primitives

## 2.1 Model

A **[[xref:Model]]** is a probabilistic computational block that generates outputs from inputs.

## 2.2 Workspace

A **[[xref:Workspace]]** is the place where workflows occur and capabilities (e.g., tools, actuators, interfaces) are provided.

## 2.3 Workflow

A **[[xref:Workflow]]** is a defined sequence of operations. When executed, it becomes a workload.

### Workflow lifecycle

* **[[xref:Workflow]]** → pre-execution
* **[[xref:Workload]]** → executing state
* **[[xref:Workload-Execution-Record]]** → post-execution

## 2.4 Agent

An **[[xref:Agent]]** is a stateful, goal-oriented workflow whose output is constrained strictly to generated media.

## 2.5 Security Basis: The Architectural Triad

The taxonomy enforces the strict separation of:

* **[[xref:Agent]]** (generator)
* **[[xref:Workflow]]** (interpreter/executor)
* **[[xref:Workspace]]** (actuation environment)

This ensures safe interpretability and auditable state-change mediation.

---

# 3. Architectural Blueprints

## 3.1 Component

A **[[xref:Component]]** is a reusable, certifiable unit used in building agents and workflows.

## 3.2 Framework

A **[[xref:Framework]]** defines the architecture and operation of an agent or workflow.

---

# 4. Generated vs. Called Workflows

## 4.1 Generated Workflows

Workflows dynamically spawned by a parent workflow are **[[xref:Sub-Workflow]]** or **[[xref:Sub-Agent]]**.

## 4.2 Called Workflows

Pre-existing external workflows invoked as dependencies.

---

# 5. Workspaces and Trust

## 5.1 Types of Workspaces

Includes:

* **[[xref:Sandbox]]**
* **[[xref:Agential-Workspace]]**

## 5.2 Workspace States

* **[[xref:Base-Agent]]**
* **[[xref:Loaded-Agentic-Workspace]]**
* **[[xref:Installed-Agent]]**

## 5.3 Multi-Agent & Multi-Workspace Systems

Describes collaboration and isolation models.

## 5.4 Distributed Execution

Uses **[[xref:OCAP|Object-Capabilities]]** for secure remote or nested execution.

---

# 6. Network-Level Identity & Discovery

Systems like NANDA provide verifiable **AgentFacts**, serving as identity passports for agents.

---

# 7. Certification

## 7.1 Atomic & Composable Trust

Every component—including agents, workflows, models—may be independently certifiable.

## 7.2 Generator Verification

The certification focuses exclusively on generated media quality and safety.

## 7.3 Orchestrator Verification

Certification verifies safe interpretation and actuation.

## 7.4 Chains of Trust

Composable certifications build hierarchical assurances.

---

# 8. Recommended High-Assurance Implementation

Supports the **Fractalic Single Document Lifecycle**, unifying workflow, workload, and execution record.

---

# Appendix A: Embeddedness Taxonomy

This appendix formalizes embedded states of agents and workflows.

## A.1 Foundational States

* **[[xref:Base-Model]]**
* **[[xref:Base-Component]]**
* **[[xref:Base-Workflow]]**
* **[[xref:Base-Agent]]**

## A.2 Instantiated States

* **[[xref:Loaded-Agent]]**
* **[[xref:Stateful-Workflow]]**
* **Bio-Augmented State** (included, but not as a core term)

## A.3 Deployed States

* **[[xref:Workload]]**
* **[[xref:Workload-Execution-Record]]**
* **[[xref:Installed-Agent]]**
* Workspace variants: Standard, TEE, Ephemeral, Simulated, Hybrid, Contractual

## A.4 Multi-Agent Embeddedness

* Supervisor / subordinate hierarchies
* Sub-agents vs peer agents

## A.5 Additional Configurations

* **[[xref:Segregated-Domain-Embeddedness]]**
* **[[xref:Auditable-Replica-Embeddedness]]**
* **UI-Embedded Agent** (not core term but referenced)
* **Societal Embeddedness**

---

# /spec/specs.json

```json
{
  "specs": [
    {
      "id": "t4as",
      "title": "Taxonomy for Agent Systems",
      "version": "0.3",
      "status": "draft",
      "documents": [
        "Taxonomy-for-Agent-Systems.md"
      ],
      "dependencies": ["ocap"]
    }
  ]
}
```

---

# /terms-definitions

Below are the core **Standard tier** term definitions.

Each definition follows:

```
[[def:Term]]
Definition text...
```

---

## /terms-definitions/Agent.md

[[def:Agent]]
A stateful, goal-oriented workflow whose output is strictly limited to generated media. Agents do not perform execution.

## /terms-definitions/Workflow.md

[[def:Workflow]]
A declarative or procedural sequence describing operations to be performed using components, agents, and models.

## /terms-definitions/Workspace.md

[[def:Workspace]]
The environment providing capabilities, state, and tools used by workflows.

## /terms-definitions/Model.md

[[def:Model]]
A probabilistic computational system that generates media outputs from inputs.

## /terms-definitions/Component.md

[[def:Component]]
A reusable, certifiable unit used to build workflows, agents, or frameworks.

## /terms-definitions/Framework.md

[[def:Framework]]
A deterministic architecture defining the structure and operation of an agent or workflow.

## /terms-definitions/Workload.md

[[def:Workload]]
An executing instance of a workflow, including its runtime state.

## /terms-definitions/Workload-Execution-Record.md

[[def:Workload-Execution-Record]]
The immutable post-execution record describing the final state and execution log of a workload.

## /terms-definitions/Perspective.md

[[def:Perspective]]
The persistent run-state of an agent that captures its evolving goals, memories, and identity.

## /terms-definitions/Sub-Agent.md

[[def:Sub-Agent]]
A stateful agent generated by a parent workflow for a scoped purpose.

## /terms-definitions/Sub-Workflow.md

[[def:Sub-Workflow]]
A workflow generated dynamically by another workflow and cryptographically tied to its origin.

## /terms-definitions/Sandbox.md

[[def:Sandbox]]
A highly constrained workspace designed to safely contain agent or workflow execution.

## /terms-definitions/Agential-Workspace.md

[[def:Agential-Workspace]]
A workspace configured for the open-ended operation of agents with defined security boundaries.

## /terms-definitions/Base-Agent.md

[[def:Base-Agent]]
A stateless, foundational set of components constituting an agent's logic before state is added.

## /terms-definitions/Base-Workflow.md

[[def:Base-Workflow]]
A workflow template prior to execution.

## /terms-definitions/Base-Model.md

[[def:Base-Model]]
A foundational generative model prior to fine-tuning or state attachment.

## /terms-definitions/Loaded-Agent.md

[[def:Loaded-Agent]]
A Base Agent combined with a specific state such as memory or knowledge.

## /terms-definitions/Installed-Agent.md

[[def:Installed-Agent]]
A Loaded Agent deployed within an operational workspace.

## /terms-definitions/OCAP.md

[[def:OCAP]]
A security model where capabilities are unforgeable tokens granting specific authority.

## /terms-definitions/Segregated-Domain-Embeddedness.md

[[def:Segregated-Domain-Embeddedness]]
A configuration where multiple agents inhabit distinct trust and privacy domains.

## /terms-definitions/Auditable-Replica-Embeddedness.md

[[def:Auditable-Replica-Embeddedness]]
A state where an agent provides a full, analyzable replica of its internal state to a trusted peer.

---

# /terms-definitions/term-index.json

```json
{
  "terms": [
    "Agent",
    "Workflow",
    "Workspace",
    "Model",
    "Component",
    "Framework",
    "Workload",
    "Workload-Execution-Record",
    "Perspective",
    "Sub-Agent",
    "Sub-Workflow",
    "Sandbox",
    "Agential-Workspace",
    "Base-Agent",
    "Base-Workflow",
    "Base-Model",
    "Loaded-Agent",
    "Installed-Agent",
    "OCAP",
    "Segregated-Domain-Embeddedness",
    "Auditable-Replica-Embeddedness"
  ]
}
```
