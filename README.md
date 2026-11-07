<div align="center">

# gitlogue

**Replay Git commits as animated typing in your terminal.**

[![gitlogue](https://snapcraft.io/gitlogue/badge.svg)](https://snapcraft.io/gitlogue)
[![Base: core26](https://img.shields.io/badge/Base-core26-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core26)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64, arm64](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [gitlogue](https://github.com/unhappychoice/gitlogue), a terminal tool that replays Git history as typed-out code with syntax highlighting.

</div>

---

## Getting Started

<a href="https://snapcraft.io/gitlogue"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install gitlogue
cd ~/code/my-repository
gitlogue
```

Replay a specific commit with `gitlogue --commit HEAD~5`, filter with `--author`, and list themes with `gitlogue theme list`.

## Configure

There are no `snap set` options. Set a default theme with `gitlogue theme set dracula`, or edit `~/snap/gitlogue/current/.config/gitlogue/config.toml`:

| Setting | Accepted values | Default |
| --- | --- | --- |
| `theme` | A name from `gitlogue theme list` | `tokyo-night` |
| `speed` | Milliseconds per typed character | `30` |
| `background` | `true`, `false` | `true` |
| `order` | `random`, `asc`, `desc` | `random` |
| `loop` | `true`, `false` | `false` |
| `ignore_patterns` | List of glob patterns | `[]` |

For repositories on removable storage:

```bash
sudo snap connect gitlogue:removable-media
```

## Limitations

- Repositories must be in a normal folder under your home directory or on connected removable storage. Hidden folders directly under your home directory are not accessible.
- An existing configuration in the host's `~/.config/gitlogue` is not read; copy it to `~/snap/gitlogue/current/.config/gitlogue`.

## Build

```bash
git clone https://github.com/sidalit/gitlogue-snap.git
cd gitlogue-snap
sudo snap install snapcraft --classic
snapcraft pack
```

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/gitlogue-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/unhappychoice/gitlogue/issues).

## License

Snap packaging: [MIT](LICENSE).
