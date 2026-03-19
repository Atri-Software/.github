# Atri Software

**Atri Software** is the independent development space behind **Atri OS** — a new operating system built entirely from scratch, with its own microkernel, filesystem, and distributed computing architecture.

---

## Vision

A fast, private, and predictable operating system where multiple devices — old PCs, servers, laptops — combine into a single computing environment with no upper limit on scale.

**Core principles:**
- Own microkernel written in Rust
- Distributed system as the key feature
- Capability-based security
- Immutable system image
- Privacy by design
- Performance first

---

## Architecture

| Layer | Technology |
|-------|-----------|
| Language | Rust |
| Kernel | Custom microkernel (scheduling, memory, IPC, capabilities) |
| Drivers | Userspace, stable ABI |
| Filesystem | Custom (built-in snapshots, compression, encryption) |
| Desktop Shell | Wry + HTML/CSS/JS |
| Window Manager | Custom, built from scratch |
| Bootloader | Limine (initial) → custom (later) |
| Platforms | x86_64, ARM64, RISC-V |

---

## Repositories

Most repositories are currently private while early development is underway. More will be published as the system takes shape.

See [`atri-os`](https://github.com/Atri-Software/atri-os) for the project's entry point and documentation.

---

## Status

Early stage — architecture and vision defined, implementation beginning.

---

## License

**Atri Public License v1.0 (APL-1.0)** — source-available.

- Free for personal, educational, and non-commercial use
- Commercial use: royalty-based (5% on revenue > $1M/year) or enterprise license
- Forking and rebranding prohibited
- Contributions accepted via CLA

See [LICENSE](https://github.com/Atri-Software/atri-os/blob/main/LICENSE) for full terms.
