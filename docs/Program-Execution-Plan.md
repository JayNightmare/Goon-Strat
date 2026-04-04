# Program Execution Plan (Team of 4)

## 1. Mission Context

Build a specification-compliant, interoperable CCSDS 235.1-W-0.4 reference implementation by 31 Aug 2026, optimized for:

- Protocol correctness first
- Measurable interoperability
- Sub-1 ms encode/decode and frame processing
- Sub-50 KB session overhead
- Reproducibility and strong documentation

## 2. Team Operating Model

Role placeholders:

- Engineer A: Systems/Protocol Lead
- Engineer B: V&V and Performance Lead
- Programmer A: Core Protocol Developer
- Programmer B: Infrastructure/Tooling Developer

### Responsibility Split

- Engineer A
     - Owns interpretation of CCSDS sections and decision log
     - Owns state machine correctness and interface definitions
     - Co-owns workshop and interoperability readiness
- Engineer B
     - Owns test strategy, coverage model, benchmark design
     - Owns conformance matrix and PICS draft
     - Co-owns risk and failure-mode analysis
- Programmer A
     - Owns SPDU, COP-P core implementation, and parser rigor
     - Owns serialization/deserialization correctness and byte order utilities
- Programmer B
     - Owns frame layer implementation, physical channel adapters, CI/CD, reproducible builds, docs tooling

## 3. Cadence and Governance

- Planning: weekly Monday 45 minutes
- Daily sync: 15 minutes
- Spec alignment review: twice weekly (Engineer A leads)
- Test and benchmark review: weekly (Engineer B leads)
- Gateway readiness review: 48 hours before each gateway close
- Decision records: all non-trivial choices captured in ADR format

## 4. Quality Gates (apply to every phase)

- No merge without tests for changed behavior
- No open severity-1 bug older than 48 hours
- Coverage target trendline: >= 90% unit coverage by Gateway 8
- Deterministic behavior required in core protocol tests
- Public interfaces documented before phase close

## 5. Branching and Release Strategy

- `main`: releasable baseline
- `develop`: integration branch
- `feature/<gateway>-<topic>` branches
- Release tags:
     - `g0-arch`, `g1-spdu`, `g2-copp`, `g3-frame`, `g4-physical`, `g5-state`, `g6-session`, `g7-int`, `g8-conf`, `g9-interop`, `g10-docs`

## 6. Risk Register (initial)

- Ambiguity in spec interpretation
     - Mitigation: formal decision log + test vectors tied to sections
- Performance regressions near final phase
     - Mitigation: benchmark in CI from Gateway 1 onward
- Interoperability surprises
     - Mitigation: workshop artifact generation and decode replay tests
- Over-focus on implementation, under-focus on docs
     - Mitigation: documentation treated as parallel workstream every phase

## 7. Deliverable Control Board

Track each gateway with:

- Scope committed
- Scope delivered
- Validation checklist pass/fail
- Blockers and mitigations
- Evidence links (tests, benchmarks, reports)

## 8. Score Maximization Strategy

- 40 points correctness: strict section-to-test traceability
- 25 points testing/conformance: build conformance matrix early
- 15 points interoperability: artifact rehearsals and exchange drills
- 10 points performance: continuous microbench and stress profiles
- 10 points documentation: complete API, user, architecture docs with runnable examples

## 9. Immediate Next 7 Days (from 4 Apr 2026)

- Day 1-2: finalize stack, architecture boundaries, repository scaffolding
- Day 3-4: define SPDU data model and endian utility API
- Day 5: bring up test harness with golden vectors
- Day 6: set benchmark harness and memory measurement method
- Day 7: Gateway 0 readiness review and adjustments

<div align="center">

[⬆️ Back to Top ⬆️](#program-execution-plan-team-of-4)

---

[Back Phase](./README.md) | [Next phase](./Phase-1-Foundation-Core-Protocol.md)

</div>
