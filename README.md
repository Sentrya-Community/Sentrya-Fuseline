# Sentrya Fuseline

**Secure-by-default configuration, auditing and provisioning for ESP32 devices — with a public threat model that states exactly what it protects against, and what it doesn't.**

> **Status: design phase.** There is no usable release yet. This repository
> currently holds the project scope and the draft threat model, published
> for public review. Do not use anything here on production devices.

---

## Why Fuseline exists

ESP-IDF already provides strong security building blocks: Secure Boot V2,
Flash Encryption, encrypted NVS, signed OTA updates with rollback and
anti-rollback, and eFuse-based disabling of JTAG and UART download mode.

Using them correctly is the hard part. Options are spread across Kconfig,
the partition table and eFuses; some steps are irreversible; and the
protection each one offers depends on the chip and its revision.

Fuseline does not add new security primitives. It aims to make the existing
ones **easy to configure correctly, possible to verify, and clear about
their limits.**

## Planned scope for v0.1

Target chip: **ESP32-S3** only.

- **Hardened profiles** — reference `sdkconfig` and partition table
  configurations, applied on top of ESP-IDF (Fuseline is not a fork).
- **Static audit tool** — analyzes a project's `sdkconfig` and partition
  table and reports which protections are enabled, missing or misconfigured.
- **Provisioning guide** — step-by-step eFuse provisioning for development
  and release modes, with every irreversible step clearly marked.
- **Public threat model** — for the ESP32-S3, linked to Espressif's
  security advisories.

Not planned for v0.1: live device auditing, other chip families,
Arduino/PlatformIO integration, fleet management or cloud services.
No release dates are committed at this stage.

## Threat model (summary)

The full draft is in [`docs/threat-model.md`](docs/threat-model.md).
We welcome review and criticism — please open an issue or a discussion.

**Fuseline aims to mitigate:**

- Malicious or downgraded firmware delivered via OTA
- Reading firmware and secrets from external flash
- Booting unsigned code
- Access through debug interfaces (JTAG, UART download mode)
- Configuration mistakes, such as partially enabled protections or keys
  shared across devices

**Out of scope:**

- **Hardware-level attacks** such as voltage or electromagnetic fault
  injection and power side-channel analysis. Several of these have been
  publicly demonstrated against ESP32-family chips and **cannot be fixed by
  firmware**. Fuseline documents them and the hardware design choices that
  reduce exposure, but does not claim to prevent them.
- **Vulnerabilities in application code** written by the user.

## Intended use

Fuseline is a general-purpose community project designed for commercial and
hobbyist ESP32 devices. It is **not intended for defense, safety-critical or
high-assurance applications**, and it is not used by Sentrya Defense.

Fuseline does not provide, and should not be described as providing,
certification or regulatory compliance (including under the EU Cyber
Resilience Act or any cybersecurity standard).

## Relationship with Espressif

Fuseline is an independent project built on top of
[ESP-IDF](https://github.com/espressif/esp-idf). It is not affiliated with,
endorsed by or sponsored by Espressif Systems. ESP32 and ESP-IDF are
trademarks of Espressif Systems.

Vulnerabilities that affect ESP-IDF or Espressif hardware are reported
upstream to Espressif. See [`SECURITY.md`](SECURITY.md).

## Contributing

During the design phase, the most valuable contributions are reviews of the
threat model and the planned scope. Contribution guidelines will be
published in `CONTRIBUTING.md`.

## Security

Please **do not report security vulnerabilities through public issues.**
See [`SECURITY.md`](SECURITY.md) for how to report them privately.

## License

Licensed under the [Apache License 2.0](LICENSE).

---

Sentrya Fuseline is developed by [Sentrya Community](https://github.com/<org>) — *Engineered in the open.*
