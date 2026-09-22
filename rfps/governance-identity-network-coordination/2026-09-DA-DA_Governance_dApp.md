## Development Fund Proposal

**Organization:** Digital Asset

**Author / Primary Contact:** Itai Segall

**Status:** Draft

**Created:** 2026-09-21

**Proposal Type:** RFP-aligned

**RFP / Roadmap Area:** Governance, Identity & Network Coordination

**Champion:** [List Champion](https://github.com/canton-foundation/canton-dev-fund/blob/main/sig-directory.md) **OR** `Needs Champion`

**Total Funding Request:**

**Project Duration:**

**Label:**
- onchain-governance

---

## Abstract

Today, on-chain SV governance is tightly coupled with node
operations. Every node has a single on-ledger vote, and only the
SV operator party can submit votes (and vote requests) on behalf of that
node. This introduces operational complexities for SV operators (who often
need to seek approval to vote within their organizations from business owners),
as well as a security risk by reusing the same operator (internal) party for
all votes.

This proposal introduces a mechanism through which (external) parties
can be delegated by the node operator to be able to vote on behalf of the node,
and a dApp UI through which they can perform that. The delegee can choose to
host their own dApp UI, or use one hosted by the SV node for them. This
proposal takes over the remaining work out of XXX, which was discontinued after
delivering Milestone 2. The starting point for this proposal is therefore M2
in the above referenced one.

---

## Specification

### 1. Objective

Develop and deliver a mechanism for an SV node operator to delegate SV
governance voting to non-operator
parties, which may also be external and hosted on a different validator node,
and a dApp for them to do so.

### 2. Implementation Mechanics
Explain how the solution will be implemented and what it will do so that a technical expert in an adjacent
area will understand what is being built. Convince the reader that your grasp of the problem and solution are
broad enough to have confidence in the result. Include technologies, components, workflows, and operational approach.

### 3. Architectural Alignment
Describe how this work aligns with Canton architecture, ecosystem priorities, and relevant CIPs.

### 4. Backward Compatibility
Describe any impact on existing systems, integrations, or workflows.
If none, state: *No backward compatibility impact.*

---

## Milestones and Deliverables

### Milestone 1: Community Acceptance
- **Estimated Delivery:**
  - approval + 4 weeks
- **Focus:**
- **Deliverables / Value Metrics:**
  - Daml code is complete enough to be voted on in a CIP
  - CIP written, submitted and accepted

### Milestone 2: Production Readiness
- **Estimated Delivery:**
  - approval + 12 weeks
- **Focus:**
- **Deliverables / Value Metrics:**
  - Complete implementation, hardening and testing
    - Add support for node operators to configure their voting delegates.
    - Add support and documentation for SV node operators to host the voting UI for their voting delegates.
    - Add support for a single party being the governance voting party for more than one SV node.
      At submission time, the user can choose on behalf of which node they are voting.
    - SV dApp UI supports the `governance` tab from the existing SV UI,
      but hides all other functionality (which is either broken or irrelevant
      for voting parties).
    - Identify the parameters in votes that are clearly node operations-specific,
      and hide/disable changing them via the dApp UI.
    - Happy-path and error-path testing complete, code is production-ready
    - Functionality is tested against two different CIP-103 compliant wallet implementations
      (the reference wallet, and one more).
  - Functionality is presented and demonstrated to the SV node operators.
  - Deployment and usage fully documented in the canton-network public documentation.
  - All code is merged into Splice main, ready for release in the coming minor release.

### Milestone 3: Rollout and Adoption
- **Estimated Delivery:**
  - approval + 22 weeks
- **Focus:**
- **Deliverables / Value Metrics:**
  - Daml Model versions are voted in on DevNet, TestNet and MainNet, and the feature is available for use by SV nodes.
  - At least two different SV operators configuring delegation to governance parties and submitting at least one vote
    request or vote each as a delegate via the dApp.

---

## Acceptance Criteria
The Tech & Ops Committee will evaluate completion based on:

- Deliverables completed as specified for each milestone
- Demonstrated functionality or operational readiness
- Documentation and knowledge transfer provided
- Alignment with stated value metrics

(Add any project-specific acceptance conditions.)

The acceptance criteria is to be based on value to the ecosystem and not delivery of an artifact.
For example, a milestone of "10 dApps adopting this capability by August" shows value.  A milestone of
"Deliver this feature with 100% of CI/CD tests passing" does not demonstrate ecosystem value.

---

## Funding

**Total Funding Request:**

### Payment Breakdown by Milestone
- Milestone 1 _(Name)_: XX CC upon committee acceptance
- Milestone 2 _(Name)_: XX CC upon committee acceptance
- Milestone N _(Name)_: XX CC upon final release and acceptance

### Volatility Stipulation
If the project duration is **greater than 6 months**:
The grant is denominated in fixed Canton Coin and will require a re-evaluation at the 6-month mark.

If the project duration is **under 6 months**:
Should the project timeline extend beyond 6 months due to Committee-requested scope changes, any remaining milestones must be renegotiated to account for significant USD/CC price volatility.

---

## Co-Marketing
Upon release, the implementing entity will collaborate with the Foundation on:

- Announcement coordination
- Case study or technical blog
- Developer or ecosystem promotion

(Add any specific commitments.)

---

## Motivation
Why is this valuable to the Canton ecosystem?
Describe the ecosystem impact, expected adoption, or strategic importance.  Provide an estimate of the portion of the ecosystem that benefits (e..g, 50% of dApps use TypeScript and we expect 50% of them will use our TypeScript library).

---

## Rationale
Why is this the right approach to deliver that value?
Explain design decisions, alternatives considered, and why this solution is preferred.  In particular, explain how this proposal fits
into the existing ecosystem tooling, libraries, frameworks, etc. If this is a proposal to replace something that exists,
then explain why the proposal cannot fit into the existing component by extending what exists.  The default approach should be to extend what exists.
