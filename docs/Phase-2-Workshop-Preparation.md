# Phase 2 Plan: Workshop Preparation (Weeks 11-12)

## Scope

- Workshop preparation buffer (15 Jun - 28 Jun)
- Produce and validate 5 interoperability artifacts as hex dumps
- Rehearse live exchange and decode workflows

## Objectives

- Ensure workshop-ready interoperability baseline
- Detect wire-format incompatibilities before Phase 3 complexity
- Build confidence in repeatable artifact generation/consumption

## Artifact Production Plan

1. Type F1 PLCW
      - Report Value 127, Retransmit false, PCID 0, Expedited Counter 3
2. Type F2 PLCW
      - Report Value 500, Retransmit true, PCID 1, Expedited Counter 6
3. Variable-length SPDU
      - Type 1 Directive, SET V(R), SEQ_CTRL_FSN 42
4. P-frame Version-3
      - Contains artifact #1, Expedited QoS
5. U-frame Version-3
      - 10-byte payload 0x00-0x09, Sequence Controlled QoS, seq 7

## Role Assignment

- Engineer A
     - Verifies bit-level compliance of each artifact
     - Signs off section-trace references
- Engineer B
     - Defines artifact verification scripts and expected decode outcomes
- Programmer A
     - Implements deterministic artifact generator CLI
- Programmer B
     - Implements parser/checker CLI and exchange harness

## Execution Steps

### Step 1: Deterministic Generation

- Freeze serialization options and endian assumptions
- Generate artifacts from known seed inputs
- Export canonical hex files with metadata

### Step 2: Independent Decode Verification

- Run decode on a separate tool path (avoid same-code false confidence)
- Validate fields against expected values
- Capture mismatch reports if any

### Step 3: Exchange Drill

- Simulate partner-team exchange loop locally
- Execute send -> receive -> decode -> compare cycle
- Record turnaround time and failure cases

### Step 4: Live Demo Rehearsal

- Timebox demo script to 15 minutes
- Include malformed frame example and graceful handling
- Produce one-page runbook for workshop operators

## Deliverables

- 5 artifact hex dumps with metadata
- Artifact generator/validator tools
- Interoperability rehearsal report
- Workshop runbook

## Acceptance Criteria

- Every artifact decodes byte-accurately to expected field values
- Generation and parsing are reproducible on clean environment
- Team can execute exchange demo without ad-hoc fixes

## Risks and Mitigations

- Risk: hidden parser/generator coupling bugs
     - Mitigation: independent validation path and randomized negative tests
- Risk: workshop day operational confusion
     - Mitigation: operator runbook and role-based live checklist

<div align="center">

[⬆️ Back to Top ⬆️](#phase-2-plan-workshop-preparation-weeks-11-12)

---

[Back Phase](./Phase-1-Foundation-Core-Protocol.md) | [Next phase](./Phase-3-Session-Control-Integration.md)

</div>
