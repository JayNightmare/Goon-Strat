# Phase 1 Plan: Foundation and Core Protocol (Weeks 1-10)

## Scope

- Gateway 0: Design and Architecture (5 Apr - 19 Apr)
- Gateway 1: SPDU Layer (20 Apr - 10 May)
- Gateway 2: COP-P Layer (11 May - 31 May)
- Gateway 3: Frame Layer (1 Jun - 14 Jun)

## Phase Objectives

- Establish architecture and test strategy that can scale to full compliance
- Deliver protocol core needed for workshop participation
- Prove deterministic and performant implementation behavior early

## Workstreams

1. Architecture and design control
2. SPDU and directive serialization
3. COP-P behavior and state tracking
4. Frame construction/parsing + QoS
5. Unit tests and benchmark harness

## Week-by-Week Plan

### Weeks 1-2 (Gateway 0)

- Engineer A
     - Produce layer boundary design and section mapping
     - Draft initial ADRs for architecture choices
- Engineer B
     - Define verification strategy, coverage targets, and performance methodology
- Programmer A
     - Scaffold protocol crates/modules and shared types
- Programmer B
     - Configure build/test tooling and CI skeleton

Exit criteria:

- Architecture document complete
- Build passes in clean environment
- Test framework executes baseline tests

### Weeks 3-5 (Gateway 1)

- Engineer A + Programmer A
     - Implement SPDU encode/decode for F1, F2, 1-5
     - Implement directive decode for Type 1 and Type 2
- Engineer B + Programmer B
     - Build malformed input and negative test matrix
     - Add sub-1 ms microbench checks per SPDU class

Exit criteria:

- All SPDU variants pass golden tests
- Malformed SPDUs rejected gracefully
- Benchmarks indicate under 1 ms per SPDU

### Weeks 6-8 (Gateway 2)

- Engineer A + Programmer A
     - Implement FOP-P logic including 8/16-bit sequence handling
     - Implement FARM-P logic for receive/retransmit behavior
- Engineer B + Programmer B
     - Implement COP-P coordinator behavior for Expedited and Sequence Controlled modes
     - Add persistence process tests and wrap-around edge cases

Exit criteria:

- Sequence state variables validated under nominal and wrap conditions
- Retransmit and resynchronization scenarios pass
- Window logic enforces boundaries

### Weeks 9-10 (Gateway 3)

- Programmer B + Engineer A
     - Implement P-frame and U-frame tx/rx pipeline
     - Add Version-3/Version-4 frame support and QoS flag handling
- Programmer A + Engineer B
     - Build frame parser robustness tests and malformed frame rejection
     - Validate under 1 ms frame processing

Exit criteria:

- P-frame/U-frame handling correct and differentiated
- SPDU extraction from P-frames validated
- QoS and version flags verified

## Required Documents Produced in Phase 1

- Architecture baseline (for Gateway 0)
- Interface map for SPDU/COP-P/frame layers
- Unit test evidence report (Gateways 1-3)
- Initial benchmark report

## Key Risks and Mitigations

- Risk: misread section semantics
     - Mitigation: section-linked test names and review checkpoints
- Risk: hidden latency spikes
     - Mitigation: benchmark each merge on representative payloads

## Phase 1 Definition of Success

- Gateways 0-3 evidence complete
- Workshop prerequisites met (working core + hex dump capability)

<div align="center">

[⬆️ Back to Top ⬆️](#phase-1-plan-foundation-and-core-protocol-weeks-1-10)

---

[Back Phase](./Program-Execution-Plan.md) | [Next phase](./Phase-2-Workshop-Preparation.md)

</div>
