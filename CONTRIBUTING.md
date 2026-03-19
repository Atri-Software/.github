# Contributing to Atri OS

We welcome contributions from the community! Atri OS is a **source-available** project — the code is open for viewing, studying, and contributing, but it is not open-source in the OSI sense. Please read this guide carefully before contributing.

---

## Contributor License Agreement (CLA)

**Before your first contribution can be merged, you must agree to our [Contributor License Agreement](https://github.com/Atri-Software/atri-os/blob/main/CLA.md).**

The CLA ensures that:
- You grant Atri Software the right to use and distribute your contribution
- You retain authorship credit and moral rights
- The project can maintain a consistent licensing model

### How to sign

When you open your first pull request, the CLA bot will ask you to confirm your agreement by commenting:

```
I have read the CLA and I agree to its terms.
```

Corporate contributors should contact burakov.work@gmail.com for a corporate CLA.

---

## How to Contribute

### 1. Find something to work on

- Check [Issues](https://github.com/Atri-Software/atri-os/issues) for tasks labeled `good first issue` or `help wanted`
- Read the [docs/](https://github.com/Atri-Software/atri-os/tree/main/docs) to understand the architecture
- Review the technical spec in `docs/_agent/spec.md`

### 2. Set up the development environment

```bash
# Clone the repository
git clone https://github.com/Atri-Software/atri-os.git
cd atri-os

# Build via Docker (recommended — no local Rust toolchain needed)
npm run os:build

# Run in QEMU (x86_64)
npm run run:iso:x86_64
```

See [docs/_howto/build.md](https://github.com/Atri-Software/atri-os/blob/main/docs/_howto/build.md) and [docs/_howto/develop.md](https://github.com/Atri-Software/atri-os/blob/main/docs/_howto/develop.md) for detailed instructions.

### 3. Make your changes

- Create a feature branch from `main`
- Follow the code guidelines below
- Ensure your changes compile for **all three target platforms** (x86_64, AArch64, RISC-V)

### 4. Submit a pull request

- Fill in the PR template
- Reference related issues
- Wait for review from a maintainer

---

## Code Guidelines

### General

- **Language:** Rust (`#![no_std]`, `#![no_main]`). No C/C++ unless absolutely unavoidable with justification.
- **Panic strategy:** `panic = "abort"` — no unwinding.
- **Synchronization:** `spin` crate (spin-locks). No std mutex.
- Keep code minimal, modular, and readable.
- Add comments where behavior is non-obvious.

### Multi-platform

All contributions must support or account for all three target architectures:
- `x86_64-unknown-none`
- `aarch64-unknown-none`
- `riscv64gc-unknown-none-elf`

If you use `cfg(target_arch = "...")`, provide implementations (or at minimum compilable stubs) for all three.

### Architecture

- **Microkernel:** only scheduler, memory management, IPC, and capabilities belong in the kernel. Everything else is a userspace service.
- **Capability-based security:** no global namespaces, no UID/GID-based permissions.
- **No POSIX in the kernel:** POSIX compatibility is handled by the userspace POSIX Compat Layer.

### Dependencies

- **Permitted:** MIT, BSD, Apache 2.0, or equivalent permissive licenses only.
- **Prohibited:** GPL, LGPL, AGPL, or any copyleft license.
- Minimize new dependencies — justify additions in your PR description.

---

## Licensing

Atri OS is licensed under the **Atri Public License v1.0 (APL-1.0)** — a source-available license. Key points:

- ✅ Free for personal, educational, and non-commercial use
- ✅ View, study, and modify the source code
- ✅ Contribute back via pull requests (with CLA)
- ❌ No forking to create separate projects
- ❌ No rebranding or redistribution without permission
- 💰 Commercial use requires a license (royalty-based or enterprise)

See the full [LICENSE](https://github.com/Atri-Software/atri-os/blob/main/LICENSE) for details.

---

## Contributor Recognition

We value every contribution. Contributors are recognized through:

- **AUTHORS file** — public record of all contributors
- **Contributor tiers** — Contributor → Core Contributor → Maintainer
- **Early access** — pre-release builds and roadmap discussions (for active contributors)
- **Revenue sharing** — may be offered to top contributors (separate agreement)

---

## Project Governance

Atri OS is maintained by **Nick Burakov / Atri Software**. Final decisions on architecture, features, and releases rest with the project maintainer. Contributions are welcome, but acceptance is at the maintainer's discretion.

---

## Questions?

- Open an [Issue](https://github.com/Atri-Software/atri-os/issues) for technical questions
- Email burakov.work@gmail.com for licensing or CLA questions
- See [SECURITY.md](https://github.com/Atri-Software/atri-os/blob/main/.github/SECURITY.md) for vulnerability reports

Thank you for your interest in Atri OS!
