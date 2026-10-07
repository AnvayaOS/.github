# v1.8.3 coordinated patch release — interrupt-delivery repair

Kernel: [v1.8.3](https://github.com/AnvayaOS/anvaya/tree/v1.8.3), release source
`d8f2dab460173db4f9c33fe3194e3394e7adeac5` (nucleus 1.8.3), which is also the
tag's commit; the
[acceptance contract](https://github.com/AnvayaOS/anvaya/blob/v1.8.3/evidence/V1_8_3_CLOSURE.md)
binds its records.

v1.8.3 fixes the intermittent qemu-virt boot hang present since before v1.8.2:
a device interrupt taken while a client or service runs in user mode is now
claimed through the bare kernel map, fatal reports print through it, and a
restarted driver binding drains the PLIC source its predecessor left latched.
The SHAKTI kit packs Kit A as `anvaya-nucleus-shakti.bin`. The v1.8.2 owner
amendment does not apply: v1.8.3 requires the complete five-group local
release capture at its tag, including both SHAKTI `shakti_c` lanes and the
135-harness model union, then packages, nine coordinated releases and the
anvaya.dev deployment with a real public QEMU session. All work is local and
every commit carries `[skip ci]`; no GitHub Actions run.

Documentation: unchanged; the fix and its evidence live in the core repository.

v1.9 stays deferred. FML13V01 and SHAKTI physical acceptance and the external
audit remain pending; M1/M6/M8 remain PARTIAL, and this repository's
independent maturity and RFC statuses do not advance through coordination.

## Historical v1.8.2 coordination

# v1.8.2 coordinated patch release — SHAKTI boot readiness

Kernel: [v1.8.2](https://github.com/AnvayaOS/anvaya/tree/v1.8.2), release source
`26d17f0e028d3e9a89fc83752a1678fce60f4fd8` (nucleus 1.8.2); the tag adds only
documentation: the gate evidence and the
[closure record](https://github.com/AnvayaOS/anvaya/blob/v1.8.2/evidence/V1_8_2_CLOSURE.md).

v1.8.2 adds a third kernel target, `shakti-cclass`, for a SHAKTI C-class
bitstream on a Digilent Arty A7-100T. On QEMU `shakti_c` it reaches first light
under OpenSBI v1.7 and, under Anvaya's Rust machine-mode resident monitor, runs
the signed `hello-status` app and fires the PMP-gated escape from machine mode.
A private loading kit is prepared for IIT Madras outside the repositories.
SHAKTI is Buildable; no physical boot is claimed, and the private vendor device
tree is published only as its SHA-256.

By the owner's amendment in V1_8_2_GOAL.md, v1.8.2 is proven by both QEMU
`shakti_c` lanes, the three-feature build matrix, nucleus unit and DTB tests,
fmt and clippy on the touched crates, the unchanged qemu-virt boot regression
and the docs and claims checkers. The multi-day formal capture is not re-run
and no new formal result is claimed. anvaya.dev and the live demo stay on
v1.8.1; nothing is deployed for this patch. All work is local and every commit
carries `[skip ci]`; no GitHub Actions run.

Organization profile: unchanged by this patch; report SHAKTI only as Buildable.

v1.9 stays deferred. FML13V01 and SHAKTI physical acceptance and the external
audit remain pending; M1/M6/M8 remain PARTIAL, and this repository's
independent maturity and RFC statuses do not advance through coordination.

## Historical v1.8.1 coordination

# v1.8.1 coordinated maintenance release

Kernel source: `104deaa9c6912646f5526e35d78b6f743d95c2a9` on the v1.8.1 maintenance release line.
The [maintenance acceptance contract](https://github.com/AnvayaOS/anvaya/blob/v1.8.1/evidence/V1_8_1_CLOSURE.md)
retains all seven v1.8 requirements and all five complete local groups.

The patch makes the pinned Lean transport library build explicit and requires
all three compiled modules. Seven proof bodies are repaired; the thirteen
theorem statements and the model are unchanged. The QEMU/workspace group
fetches its eight pinned NIST ACVP inputs before its original 23 steps.
No v1.9 scale/HAL feature or full SHAKTI kernel target is included.

CPU ISA admission retains the unchanged predicate result without storing the
firmware description in a fixed property buffer. Long-description admission
and missing-extension, wrong-width and other-field-limit denials are retained.
The resource guard applies the selected 8 GiB cap to both job and aggregate,
with zero swap, one job and the startup reserve unchanged.

The source includes a software-only SHAKTI SBI handoff/serial diagnostic,
low-frequency timer conversion with ceiling rounding and final saturation,
and a separate explicitly authorized hardware-validation lane. Existing release
job/aggregate limits remain unchanged. No SHAKTI MMIO backend, complete kernel
target, physical boot or security acceptance is established. Private vendor DTS
and correspondence are excluded. The final merged source requires fresh complete
release validation; earlier-source results retain only their original provenance.

Version changes require fresh complete 135-harness model verification, Verus
36 obligations and four negative controls, other Kani tracks, Lean, native
six-boot/four-cut recovery, QEMU, PQC, accounting and claims. All execution is
local, guarded, single-job and zero-swap; no GitHub Actions are authorized.
Release completion requires exact package and uploaded digests, all-nine
source/tag provenance, portable image identities, healthy deployment, rendered
truth and public QEMU boot/shell/help. Publication receipts determine acceptance.

v1.9 work is deferred at the user's request, with source and evidence preserved.
No board is available. Physical acceptance and external audit remain pending;
M1/M6/M8 remain PARTIAL, transport=service-loopback, polling=0 and
kernel_fallbacks=0 retain their existing scope. This repository's independent
component maturity and RFC acceptance statuses do not advance through release
coordination alone.

## Historical v1.8.0 coordination

# v1.8 coordinated release

Status on 2026-10-01: **v1.8.0 coordinated release source**.
Kernel source: `c86a48f87b2d882adfbe9a70c0783576a6af2b11` at [v1.8.0](https://github.com/AnvayaOS/anvaya/tree/v1.8.0).

Organization profile: report the completed milestone and exact evidence links after acceptance.

The complete kernel acceptance contract is V1_8_GOAL.md and
evidence/V1_8_CLOSURE.md in the sibling anvaya repository.
All seven required behaviors and Gates A-F remain required. The five
complete local gate records are bound to the kernel source above; the
formal group validates the complete 135-harness model union and pinned
Verus/Lean tracks. Historical v1.7.2 records retain their original identity.
Release packaging additionally binds exact artifacts, portable checksums
and all-nine repository BUILDINFO provenance.

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
