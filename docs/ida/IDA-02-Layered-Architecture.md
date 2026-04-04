# IDA-02 Layered Architecture

## 1. Architecture View

Target layered model:

1. Application/API layer
2. Session control layer (hailing, lifecycle, reconnect)
3. State machine layer (duplex mode transitions)
4. COP-P layer (FOP-P, FARM-P, coordinator)
5. SPDU layer (encode/decode, directives, PLCW)
6. Frame layer (P/U frame handling, QoS, versioning)
7. Physical channel abstraction (mock + TCP/UDP)

## 2. Module Decomposition

For each module record:

- Purpose
- Inputs/outputs
- Deterministic behavior constraints
- Failure modes and error signaling
- Performance-critical paths

## 3. Data Flow

Document:

- Tx path from application payload to wire frame
- Rx path from wire frame to protocol events
- State update points and sequencing dependencies

## 4. Concurrency Model

Define:

- Session concurrency strategy
- Synchronization boundaries
- Ownership/lifetime model for buffers and state
- Deadlock and race prevention strategy

## 5. Memory and Performance Strategy

- Pre-allocation policy
- Buffer reuse approach
- Avoided patterns (runtime allocation in hot paths)
- Measurement method for per-session overhead

## 6. Architecture Decisions (ADR links)

List key ADRs:

- Language and runtime choice
- Serialization strategy
- State transition representation
- Interface abstraction trade-offs

<div align="center">

[⬆️ Back to Top ⬆️](#ida-02-layered-architecture)

---

[Back IDA](./IDA-01-System-Context-and-Requirements.md) | [Next IDA](./IDA-03-Interfaces-and-Wire-Format.md)

</div>
