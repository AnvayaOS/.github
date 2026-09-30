# v1.8 coordinated release

Status on 2026-10-01: **candidate; validation and publication pending**.
The current stable kernel release remains v1.7.2.

Organization profile: report the completed milestone and exact evidence links after acceptance.

The complete kernel acceptance contract is V1_8_GOAL.md and
evidence/V1_8_CLOSURE.md in the sibling anvaya repository.
All seven required behaviors and Gates A-F remain required. Baseline results
retain their original v1.7.2 identity; the new v1.8.0 proof fingerprint requires
a complete current-source rerun, five completed local groups, exact artifacts,
portable checksums and all-nine repository BUILDINFO provenance.

Do not label this coordinated milestone released until the exact-source gates,
packaging, repository tags/main provenance, site proof/truth checks, deployment
health and rendered public/demo receipts have passed. Preserve historical
release entries and use [skip ci] commits; no GitHub Actions or paid runner
is authorized for this completion effort.

The scope remains QEMU-proven research software: transport=service-loopback,
polling=0, kernel_fallbacks=0, and M1/M6/M8 PARTIAL. Physical hardware and an
external security audit are not established by these software gates.

The user confirmed no physical board is available on 2026-10-01. Record the
acquisition review at the v1.8 tag; physical FML13V01 acceptance remains part
of the full v1.9 milestone and cannot be replaced by synthetic fixtures.
