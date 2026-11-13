<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/banners/delivery-dark.png">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/banners/delivery-light.png">
  <img src="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/banners/delivery-light.png" width="100%" alt="theoros-delivery">
</picture>

<p><a href="LICENSE"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/badges/license-source-available-1-0-dark.png"><img src="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/badges/license-source-available-1-0-light.png" height="31" alt="license: source-available 1.0"></picture></a> <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/badges/status-pre-release-dark.png"><img src="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/badges/status-pre-release-light.png" height="31" alt="status: pre-release"></picture> <a href="https://github.com/theoros-space"><picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/badges/part-03-of-06-dark.png"><img src="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/badges/part-03-of-06-light.png" height="31" alt="part: 03 of 06"></picture></a></p>

> [!NOTE]
> **Status:** Pre-release. The repository is public so partners and reviewers can follow the work. Source code lands here from December 2026.

## Overview

Everything between a trained model and a model running in orbit: packaging,
signing, uplink and rollback. A satellite only ever runs a package that
Theoros signed and the operator approved.

<p>
  <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/stats/signature-dark.png"><img src="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/stats/signature-light.png" width="32%" alt="signature"></picture>
  <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/stats/update-dark.png"><img src="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/stats/update-light.png" width="32%" alt="update"></picture>
  <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/stats/flight-budget-dark.png"><img src="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/stats/flight-budget-light.png" width="32%" alt="flight budget"></picture>
</p>

## Where it fits

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/diagrams/flow-dark.png">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/diagrams/flow-light.png">
  <img src="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/diagrams/flow-light.png" width="100%" alt="How Theoros works: sensor, onboard inference, answers, ground, compiler, signed update">
</picture>

| | Repository | Role |
|:-:|---|---|
| `01` | [theoros-models](https://github.com/theoros-space/theoros-models) | Multi-task model, training and the ground compiler |
| `02` | [theoros-edge](https://github.com/theoros-space/theoros-edge) | Onboard int8 runtime and flight targets |
| `03` | **theoros-delivery** | Signed model packages and over-the-air updates |
| `04` | [theoros-ground](https://github.com/theoros-space/theoros-ground) | Customer API, mission dashboard and result tracking |
| `05` | [theoros-bench](https://github.com/theoros-space/theoros-bench) | Open benchmark for onboard Earth observation AI |
| `06` | [theoros-docs](https://github.com/theoros-space/theoros-docs) | Technical documentation and flight documents |

## Lifecycle

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/diagrams/delivery-lifecycle-dark.png">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/diagrams/delivery-lifecycle-light.png">
  <img src="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/github/diagrams/delivery-lifecycle-light.png" width="100%" alt="Package, sign, uplink, activate, roll back">
</picture>

| Step | What happens |
|---|---|
| Package | Model, sensor fingerprint, capability matrix and manifest in one versioned file |
| Sign | Ed25519 signature; the satellite rejects anything unsigned or modified |
| Uplink | Sized to fit a single ground pass, sent in resumable chunks |
| Activate | The new model runs its onboard self-test before it serves results |
| Roll back | The previous model stays on board until the new one passes |

## Repository layout

Planned structure. Directories appear as the code lands.

```text
src/theoros_delivery/   package format, signing, verification, CLI
schemas/                manifest JSON schema
docs/                   requirements, package format specification
tests/
```

## Requirements

Every requirement lives in [docs/REQUIREMENTS.md](docs/REQUIREMENTS.md) with
the prefix `DEL-REQ`. Each one names how it is verified (test, analysis or
inspection), and every pull request that changes behaviour cites the
requirement it serves.

## Contributing

Read the [contributing guide](https://github.com/theoros-space/.github/blob/main/CONTRIBUTING.md)
before opening a pull request. Outside contributions need a signed
[Contributor License Agreement](https://github.com/theoros-space/.github/blob/main/CLA.md).
Report vulnerabilities privately as described in the
[security policy](https://github.com/theoros-space/.github/blob/main/SECURITY.md), never in a public issue.

## License

Source-available under the [Theoros Source-Available License 1.0](LICENSE).
You may read and evaluate this repository. Production use, modification,
redistribution and training competing models need a written license from
Theoros: licensing@theoros.space. See [which license applies where](https://github.com/theoros-space/.github/blob/main/LICENSING.md).

---

<p align="center">
  <a href="https://github.com/theoros-space"><picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/logo/svg/mark-signal.svg">
    <img src="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/logo/svg/mark-signal.svg" width="28" alt="Theoros">
  </picture></a>
  <br>
  <sub>Theoros &nbsp;·&nbsp; Onboard AI for Earth observation &nbsp;·&nbsp; Baku and Helsinki &nbsp;·&nbsp; <a href="https://theoros.space">theoros.space</a></sub>
</p>
