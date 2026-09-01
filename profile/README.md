# ANVAYA OS

<div align="center">

![ANVAYA OS](https://img.shields.io/badge/ANVAYA-OS-blue?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyTDIgN2wxMCA1IDEwLTUtMTAtNXpNMiAxN2wxMCA1IDEwLTV2LTJsLTEwIDUtMTAtNXYyeiIvPjwvc3ZnPg==)
![Status](https://img.shields.io/badge/Status-Active%20Development-green?style=for-the-badge)
![RISC-V](https://img.shields.io/badge/RISC--V-First-orange?style=for-the-badge)
![License](https://img.shields.io/badge/License-Apache%202.0%20%2B%20MIT-purple?style=for-the-badge)

### **The Operating System for the Intelligence Age**

*AI-Native • RISC-V First • Post-Quantum • Capability-Secure • Sustainable*

[Website](https://anvaya.dev) • [Manifesto](https://github.com/AnvayaOS/anvaya/blob/main/MANIFESTO.md) • [Documentation](https://docs.anvaya.dev) • [Contributing](https://github.com/AnvayaOS/anvaya/blob/main/CONTRIBUTING.md)

</div>

---

## 🌟 What is ANVAYA?

**ANVAYA** (Sanskrit: अन्वय — *logical connection, lineage*) is a new operating system built from first principles for a world of:

- 🤖 **AI agents** as primary users, not just human operators
- 🔐 **Capability-based security** enforced in hardware
- ⚛️ **Post-quantum cryptography** as the default, not an afterthought
- 🌱 **Sustainable computing** with energy as a first-class resource
- 🔓 **RISC-V native** — open hardware, no licensing fees

We are not patching UNIX. We are not forking Linux. We are building anew.

---

> **Now:** Anvaya **1.7.0** ("Capability Sockets") is released — the fifth kernel-to-userspace extraction in the 1.x line. A socket is now a capability carrying kind, resource identity, rights, and generation, and the TCP/UDP/IP/ARP/ICMP/DNS stack runs in a hybrid-signed U-mode network task with its own pid, CSpace, and page tables and no device authority; frames it composes transit the signed U-mode virtio-net driver interrupt-driven, and mesh object sync crosses those sockets. Product core compiles zero network names (core **20,740 lines**, counted privileged TCB **22,362**), and manifesto commitment M8 advances from DEBT to PARTIAL. The path here since 1.3.6: **1.4.0** ("The Real Launcher") gave running processes a real launch syscall, served the audit service through it as the second nucleus extraction, and made the package envelope an Ed25519+ML-DSA-65 hybrid; **1.4.1** ("Verify-Only Kernel") relocated signing, launcher, and energy-dispatch logic out of the kernel; **1.5.0** ("Driver Domains") moved the virtio-block and virtio-net drivers into hybrid-signed U-mode tasks with capability-scoped device, DMA, IRQ, and IPC authority, and **1.5.2** lifted the block client into a capability-scoped adapter with two-boot durability; **1.6.0** ("Content-Addressed Storage") moved durable content into a hybrid-signed U-mode storage task with SHA3-256/Merkle addressing and a Kani-proven CRDT namespace (M6 DEBT → PARTIAL). Every step is gated by a byte-exact boot-transcript marker oracle (1,425 markers at 1.7.0, diff=empty) and a self-tightening size ratchet on the privileged core. **Proven under QEMU — not a production network stack (socket payloads still reach their reader through the service's own receive queue, not the wire; no TLS, congestion control, or IPv6), no physical hardware exists yet, and a physical-hardware boot, an external third-party audit, and a hardware root of trust remain documented open items.** The full milestone history lives in the [milestone goal documents](https://github.com/AnvayaOS/anvaya#milestone-goal-documents).

## ✅ What Works Today

ANVAYA is early — but it is **not vaporware**. The nucleus boots and runs real
code right now, and every claim below is re-asserted by **repeatable QEMU
evidence** that CI checks on every push (241 verified releases and counting):

- 🥾 **Boots on RISC-V** in QEMU under OpenSBI (S-mode nucleus, first light)
- 🔑 **Full RFC 0010 syscall surface** — capabilities, IPC, memory, scheduling, wait/cancel — proof-backed with denial paths
- 🧩 **Real userspace processes** with per-process address spaces, a satp-keyed dispatch registry, and two live tasks exchanging capability-gated IPC
- 📦 **Signed WASM/WASI apps run** — twelve capability-scoped catalog apps install and execute through a signed-package runner with deny-by-default authority
- 🛠️ **External toolchain modules run** — WebAssembly compiled by real `rustc`/LLVM (not hand-written) parses and executes, including globals, memory, and inter-procedural calls
- 💾 **Live drivers** — virtio-blk with two-boot persistence, virtio-net TX/RX, DNS, and TCP with hardware-timer retransmission
- 🔢 **Bounded WASM interpreter** — all four numeric value types (i32/i64/f32/f64) with arithmetic, conversions, and memory load/store

See the live **[status page](https://anvaya.dev/status)** and the
[reproducible evidence guide](https://github.com/AnvayaOS/anvaya#getting-started-developer-preview).

---

## 🚀 Try It Yourself

```bash
# Prerequisites: Rust (stable) + the RISC-V target, and qemu-system-riscv64 (7.0+)
rustup target add riscv64gc-unknown-none-elf

git clone https://github.com/AnvayaOS/anvaya
cd anvaya

# Boot the nucleus in QEMU and assert every proof marker (clean exit == proof)
./scripts/check-qemu-boot.sh

# Run the full developer-preview demo: the twelve signed WASM apps end to end
./scripts/demo-v0-3-apps.sh

# Or just watch it boot interactively
./scripts/run-qemu.sh
```

Each script exits non-zero if any expected marker is missing or the boot log
contains a kernel panic — so a clean run *is* the evidence.

---

## 🎯 Why ANVAYA?

| Current Systems | ANVAYA |
|-----------------|--------|
| AI is an application fighting for GPU | AI agents are first-class citizens with identity, goals, and capabilities |
| Security through permissions and ACLs | Security through unforgeable capability tokens, hardware-enforced |
| RSA/ECC cryptography (quantum-vulnerable) | Lattice-based post-quantum cryptography from day one |
| Energy is a hidden cost to minimize | Energy is a visible resource with carbon-aware scheduling |
| Designed for x86, ported to others | Designed for RISC-V, exploiting open ISA extensions |
| Root user with ambient authority | No ambient authority — every access requires explicit capability |

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                    Applications (WASM)                       │
├─────────────────────────────────────────────────────────────┤
│  Intent Layer  │  AI Agents (AECs)  │  Intelligence Broker  │
├─────────────────────────────────────────────────────────────┤
│            Userspace Services (Rust, Sandboxed)             │
├─────────────────────────────────────────────────────────────┤
│           Privileged Extensions (Verified, Optional)         │
├─────────────────────────────────────────────────────────────┤
│              NUCLEUS (~15KB, Formally Verified)              │
│         Capabilities • IPC • Scheduling • Memory             │
├─────────────────────────────────────────────────────────────┤
│                    RISC-V + CHERI Hardware                   │
└─────────────────────────────────────────────────────────────┘
```

---

## 📦 Repositories

| Repository | Description |
|------------|-------------|
| [**.github**](https://github.com/AnvayaOS/.github) | Organization profile and community health files |
| [**anvaya**](https://github.com/AnvayaOS/anvaya) | 🎯 Main OS repository — kernel, services, runtime |
| [**anvaya-site**](https://github.com/AnvayaOS/anvaya-site) | Anvaya.dev website — manifesto and updates |
| [**anvaya-docs**](https://github.com/AnvayaOS/anvaya-docs) | Documentation and guides |
| [**anvaya-apps**](https://github.com/AnvayaOS/anvaya-apps) | Example applications and demos |
| [**anvaya-sdk**](https://github.com/AnvayaOS/anvaya-sdk) | Developer SDK and capability libraries |
| [**anvaya-hardware**](https://github.com/AnvayaOS/anvaya-hardware) | Hardware specs and RISC-V extensions |
| [**anvaya-infra**](https://github.com/AnvayaOS/anvaya-infra) | CI/CD, containers, and infrastructure automation |
| [**rfcs**](https://github.com/AnvayaOS/rfcs) | Design proposals and specifications |

---

## 🗓️ Roadmap

| Milestone | Scope | Status |
|-----------|-------|--------|
| **Anvaya 0.1** — Nucleus boots on RISC-V | First-light boot, capabilities, IPC, scheduling, memory isolation | ✅ Evidence-backed in QEMU |
| **Anvaya 0.3** — WASM applications run | Signed WASM/WASI apps, services, drivers, external-toolchain modules | ✅ **0.3.0 released** (developer preview) |
| **Anvaya 0.4** — Production substrate | Production loader, live TCP/IP, SHA-256 persistence, audit service, Ed25519 signatures | ✅ **0.4.0 released** |
| **Anvaya 0.5** — AI agents run natively | Agent Execution Contexts, Intelligence Broker, MCP/A2A | ✅ **0.5.0 released** |
| **Anvaya 0.6** — Constitution & human override | Constitutional constraints, hardware escape, interpretability | ✅ **0.6.0 released** |
| **Anvaya 0.7** — Post-quantum & hardware-anchored | ML-KEM/ML-DSA/SLH-DSA (NIST ACVP KAT), CHERI profile, measured boot | ✅ **0.7.0 released** |
| **Anvaya 0.8** — Multi-device mesh | PQC pairing, cross-device capabilities, CRDT sync, distributed agents | ✅ **0.8.0 released** |
| **Anvaya 0.9** — Usable & sustainable | Energy broker (SCI), intent router/CLI/compositor, PQC package manager | ✅ **0.9.0 released** |
| **Anvaya 1.0** — QEMU-Proven Milestone | Formal verification, threat model + design-time negative tests, PQC demonstrated across surfaces, benchmarks — QEMU-proven, no physical hardware, no external audit | ✅ **1.0.0 released** |
| **Anvaya 1.1** — North Star Realignment | Machine-checked manifesto alignment ledger, PQC as the operational default, first kernel-to-userspace extraction (energy broker), type-state capability traits | ✅ **1.1.0 released** |
| **Anvaya 1.2** — Scheduling & IPC to Spec | SMP multi-hart scheduling with work stealing, real-time priority inheritance with measured bounded dispatch latency, first-class asynchronous IPC, multicore soundness (Kani harnesses 7 → 13) | ✅ **1.2.0 released** |
| **Anvaya 1.3** — RSI arc: self-tightening ratchets | `main.rs` 76,824 → 470 lines, proof harness 55,254 → 239 lines then fully re-accounted to 1,235, byte-exact 1,571-marker boot-transcript oracle, honest core/harness accounting (1.3.0–1.3.6) | ✅ **1.3.6 released** |
| **Anvaya 1.4** — WASM/WASI Application Runtime ("The Real Launcher") | A real launch syscall any running process can invoke, the audit service served through it as the second nucleus extraction, an Ed25519+ML-DSA-65 hybrid package envelope; 1.4.1 relocates signing, launcher, and energy-dispatch logic out of the kernel (verify-only nucleus) | ✅ **1.4.1 released** |
| **Anvaya 1.5** — Driver Domains | Hybrid-signed virtio-block and virtio-net drivers as distinct scheduled U-mode tasks with capability-scoped device, DMA, IRQ, and IPC authority (polling=0, kernel_fallbacks=0), forced-death cleanup and restart; 1.5.2 lifts the block client into a capability-scoped adapter with two-boot durability | ✅ **1.5.2 released** |
| **Anvaya 1.6** — Content-Addressed Storage | Hybrid-signed U-mode storage task: algorithm-tagged SHA3-256/Merkle content addressing, capability-checked namespace, Kani-proven last-writer-wins CRDT with tombstones, AVCS A/B commits recovered and re-verified on a second boot; M6 DEBT → PARTIAL | ✅ **1.6.0 released** |
| **Anvaya 1.7** — Capability Sockets | Sockets as capabilities (kind, resource id, rights, generation), the TCP/UDP/IP/ARP/ICMP/DNS stack in a hybrid-signed U-mode network task, task-composed frames transiting the signed virtio-net driver interrupt-driven, mesh sync over sockets; M8 DEBT → PARTIAL, transport still service-loopback | ✅ **1.7.0 released** |

*Progress is tracked release-by-release with reproducible QEMU evidence — see the [changelog](https://github.com/AnvayaOS/anvaya/blob/main/CHANGELOG.md) and the [live status page](https://anvaya.dev/status).*

---

## 🤝 Get Involved

We're building something ambitious, and we need help from:

- **🦀 Rust developers** — Kernel, services, and applications
- **🔬 Verification experts** — Formal proofs with Verus/Creusot
- **🔐 Security researchers** — Capability systems, cryptography
- **🤖 AI/ML engineers** — Agent architectures, inference optimization
- **📝 Technical writers** — Documentation that welcomes newcomers
- **🎨 Designers** — UI/UX for the intent-based interface layer

**Ready to contribute?** Read our [Contributing Guide](https://github.com/AnvayaOS/anvaya/blob/main/CONTRIBUTING.md) and join the discussion!

---

## 📄 License

ANVAYA OS is dual-licensed under [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) and [MIT](https://opensource.org/licenses/MIT).

---

<div align="center">

**अन्वय — The unbroken thread from cause to effect.**

*Building the operating system the intelligence age deserves.*

[⭐ Star us on GitHub](https://github.com/AnvayaOS/anvaya) • [🐦 Follow updates](#) • [💬 Join discussions](https://github.com/AnvayaOS/anvaya/discussions)

</div>

## Citation

```bibtex
@misc{anvayaos,
  title        = {ANVAYA OS: The Operating System for the Intelligence Age},
  author       = {Alphin Tom},
  year         = {2026},
  month        = {jan},
  howpublished = {\url{https://anvaya.dev}},
  note         = {Published 2026-01-01; Contact: dev@mycel-ai.de; GitHub: https://github.com/alpha912; Accessed 2026-07-11}
}
```
