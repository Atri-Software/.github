# Atri OS

An operating system built from scratch. Own microkernel, own filesystem, own desktop — and a distributed architecture that turns any number of machines into one.

---

**Your computer is yours.** No telemetry. No forced updates. No subscriptions. No ads. Offline account by default. Every byte of data encrypted on disk. Every application sandboxed. You decide what runs, what connects, and what stays private.

---

### Distributed by Design

Connect your laptop, desktop, and server into a single system. CPU, GPU, RAM, and storage are shared transparently across the network. A program starts on one machine and scales across all of them — or migrates to the one with the right hardware. Add a device to grow. Remove it and the system adapts.

### Security Without Compromise

Every process runs in a mandatory sandbox. There are no global namespaces, no root user, no ambient authority. Access to any resource — a file, a device, a network socket — requires an explicit capability. Capabilities are granted, attenuated, and delegated, but never forged.

Drivers run in userspace with stable ABI. A crashed driver restarts without taking the system down.

### Runs Anything

Native applications use the Atri SDK. Cross-platform apps ship as WebAssembly — one binary for x86, ARM, and RISC-V. A built-in compatibility layer runs unmodified Linux software. Full virtual machines handle the rest.

### Built to Last

The system image is immutable. Updates are atomic — applied in the background, verified, and rolled back automatically if anything goes wrong. Applications are self-contained packages with no dependency conflicts. The filesystem encrypts everything by default, supports snapshots, and handles compression transparently.

### Three Architectures

x86_64, AArch64, and RISC-V 64 — all first-class. Same kernel, same features, same applications.

---

Source code and documentation: [`atri-os`](https://github.com/Atri-Software/atri-os)

**Atri Public License v1.0** — source-available. Free for personal and non-commercial use. See [LICENSE](https://github.com/Atri-Software/atri-os/blob/main/LICENSE).
