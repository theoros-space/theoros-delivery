<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/logo/svg/mark-paper.svg">
  <img src="https://raw.githubusercontent.com/theoros-space/theoros-brand/main/logo/svg/mark-ink.svg" width="44" align="right" alt="Theoros">
</picture>

# theoros-delivery

**03  Signed model packages and over-the-air updates.** Part of the [Theoros](https://github.com/theoros-space) onboard AI product.

[![License: Theoros Source-Available 1.0](https://img.shields.io/badge/license-source--available-FF4B1F)](LICENSE)

> **Status: pre-release.** This repository is public so partners can follow our work. Source code lands here from December 2026.

## What it is

Everything between a trained model and a model running in orbit.

- **Package:** model, sensor fingerprint, capability matrix and manifest in one versioned file.
- **Sign:** Ed25519 signature; the satellite rejects anything unsigned or modified.
- **Uplink:** sized to fit a single ground pass, with resumable chunks.
- **Roll back:** the previous model stays on board until the new one passes its self-test.

## Planned layout

```
src/theoros_delivery/   package format, signing, verification, CLI
schemas/                manifest JSON schema
docs/                   requirements, package format specification
tests/
```

## Requirements

Requirements are listed in [docs/REQUIREMENTS.md](docs/REQUIREMENTS.md) with
the prefix `DEL-REQ`. Every requirement is verified by a test, an
analysis or an inspection, and referenced in the pull request that changes it.

## Contributing

See the organisation [contributing guide](https://github.com/theoros-space/.github/blob/main/CONTRIBUTING.md).
Outside contributions need a signed [CLA](https://github.com/theoros-space/.github/blob/main/CLA.md).

## License

Source-available under the [Theoros Source-Available License 1.0](LICENSE).
You may read and evaluate it; any use, copy or deployment needs a written
license from Theoros. Contact licensing@theoros.space.
