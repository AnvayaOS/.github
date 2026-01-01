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

| Milestone | Target | Status |
|-----------|--------|--------|
| **Anvaya 0.1** — Nucleus boots on RISC-V | Dec 2026 | 🔄 In Progress |
| **Anvaya 0.3** — WASM applications run | Dec 2027 | ⏳ Planned |
| **Anvaya 0.5** — AI agents run natively | Dec 2028 | ⏳ Planned |
| **Anvaya 0.8** — Multi-device mesh | Dec 2029 | ⏳ Planned |
| **Anvaya 1.0** — Production release | Dec 2030 | ⏳ Planned |

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
