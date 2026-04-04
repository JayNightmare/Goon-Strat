# Documentation Migration Map

This map helps the team transition from the original single-folder planning pack to the track/source-type structure under `docs/tracks/*`.

## Old Path -> New Path

- `docs/README.md` -> `docs/README.md` (updated hub)
- `docs/Program-Execution-Plan.md` -> `docs/tracks/CCSDS/deliverables/Program-Execution-Plan.md`
- `docs/Phase-1-Foundation-Core-Protocol.md` -> `docs/tracks/CCSDS/deliverables/Phase-1-Foundation-Core-Protocol.md`
- `docs/Phase-2-Workshop-Preparation.md` -> `docs/tracks/CCSDS/deliverables/Phase-2-Workshop-Preparation.md`
- `docs/Phase-3-Session-Control-Integration.md` -> `docs/tracks/CCSDS/deliverables/Phase-3-Session-Control-Integration.md`
- `docs/Phase-4-Validation-Documentation.md` -> `docs/tracks/CCSDS/deliverables/Phase-4-Validation-Documentation.md`
- `docs/IDA-Blueprint-Pack.md` -> `docs/tracks/CCSDS/deliverables/IDA-Blueprint-Pack.md`
- `docs/ida/IDA-00-Overview.md` -> `docs/tracks/CCSDS/deliverables/ida/IDA-00-Overview.md`
- `docs/ida/IDA-01-System-Context-and-Requirements.md` -> `docs/tracks/CCSDS/deliverables/ida/IDA-01-System-Context-and-Requirements.md`
- `docs/ida/IDA-02-Layered-Architecture.md` -> `docs/tracks/CCSDS/deliverables/ida/IDA-02-Layered-Architecture.md`
- `docs/ida/IDA-03-Interfaces-and-Wire-Format.md` -> `docs/tracks/CCSDS/deliverables/ida/IDA-03-Interfaces-and-Wire-Format.md`
- `docs/ida/IDA-04-VandV-and-Test-Strategy.md` -> `docs/tracks/CCSDS/deliverables/ida/IDA-04-VandV-and-Test-Strategy.md`
- `docs/ida/IDA-05-Risk-and-Safety-Case.md` -> `docs/tracks/CCSDS/deliverables/ida/IDA-05-Risk-and-Safety-Case.md`

## New Additions (No Old Equivalent)

- `docs/tracks/CCSDS/requirements/*`
- `docs/tracks/CCSDS/interoperability/*`
- `docs/tracks/CCSDS/spec/*`
- `docs/tracks/CCSDS/submission-template/*`
- `docs/tracks/LunaNet/*` (full track set)
- `docs/tracks/LunaNet/spec-tables/*`

## Rollout Steps

1. Update team bookmarks and runbooks to point at `docs/tracks/*` locations.
2. Update any scripts that reference old `docs/Phase-*` and `docs/ida/*` paths.
3. Use `docs/README.md` as the only root navigation entry.

[⬆️ Back to Top ⬆️](#documentation-migration-map)

---

[Back Page](./README.md) | [Next Page](./tracks/CCSDS/README.md)
