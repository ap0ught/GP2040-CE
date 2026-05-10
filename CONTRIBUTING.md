# Contributing to GP2040-CE

Thank you for your interest in contributing to GP2040-CE! This document explains how to get involved and what we expect from contributors.

> For broader community discussion, feature ideas, and support, join the [OpenStick GP2040-CE Discord](https://discord.gg/k2pxhke7q8).

---

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Ways to Contribute](#ways-to-contribute)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Features](#suggesting-features)
- [Pull Requests](#pull-requests)
- [Development Setup](#development-setup)
- [Coding Style](#coding-style)
- [Commit Messages](#commit-messages)
- [License](#license)

---

## Code of Conduct

This project follows the [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md). By participating, you agree to uphold these standards. Please report unacceptable behaviour to a project maintainer.

---

## Ways to Contribute

- **Bug reports** — Open a GitHub issue using the bug report template.
- **Feature requests** — Open a GitHub issue using the feature request template.
- **Code contributions** — Submit a pull request with bug fixes, new features, or improvements.
- **Documentation** — Improve docs in this repo or at [gp2040-ce.info](https://gp2040-ce.info).
- **Hardware configs** — Add or improve board configuration files under `configs/`.
- **Community support** — Help others on Discord or by responding to issues.

---

## Reporting Bugs

Before opening a bug report:

1. Check the [documentation](https://gp2040-ce.info) to ensure the behaviour you're seeing isn't expected.
2. Search [existing issues](https://github.com/OpenStickCommunity/GP2040-CE/issues) to avoid duplicates.
3. Confirm the issue exists on the [latest release](https://github.com/OpenStickCommunity/GP2040-CE/releases/latest).

When filing a report, use the **Firmware Bug Report** issue template and fill in all sections.

For **security vulnerabilities**, please read [SECURITY.md](SECURITY.md) and do **not** open a public issue.

---

## Suggesting Features

Before opening a feature request:

1. Check existing [feature requests](https://github.com/OpenStickCommunity/GP2040-CE/issues?q=is%3Aissue+label%3Aenhancement) to avoid duplicates.
2. Confirm the feature doesn't already exist in the latest firmware.

Use the **Feature Request** issue template and describe both the problem and your proposed solution.

---

## Pull Requests

Pull requests are welcome and encouraged! Please follow these guidelines:

1. **Fork** the [upstream repository](https://github.com/OpenStickCommunity/GP2040-CE) and branch from `main`.
2. **Keep changes focused** — one logical change per PR makes review easier.
3. **Test your changes** — ensure the firmware builds and behaves as expected on real hardware when possible.
4. **Follow the coding style** of the file(s) you are modifying (see below).
5. **Update documentation** if your change affects user-visible behaviour.
6. **Reference related issues** in your PR description (e.g., `Fixes #123`).

### PR Checklist

- [ ] Code compiles without errors or warnings
- [ ] Tested on hardware (if applicable)
- [ ] Existing functionality is not broken
- [ ] Documentation updated (if needed)
- [ ] Commit messages are clear and descriptive

---

## Development Setup

### Prerequisites

- [CMake](https://cmake.org/) ≥ 3.13
- [Pico SDK](https://github.com/raspberrypi/pico-sdk) 2.x (fetched automatically by CI)
- [ARM GCC Toolchain](https://developer.arm.com/downloads/-/gnu-rm) (`arm-none-eabi-gcc`)
- [Node.js](https://nodejs.org/) ≥ 20.x (for the web configurator)

### Building the Firmware

```bash
# Clone the repo (with submodules)
git clone --recurse-submodules https://github.com/ap0ught/GP2040-CE.git
cd GP2040-CE

# Build the web configurator first
cd www && npm ci && CI=false npm run build && cd ..

# Configure and build firmware
PICO_SDK_PATH=/path/to/pico-sdk GP2040_BOARDCONFIG=Pico cmake -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build --parallel
```

The resulting `.uf2` file will be in `build/`.

---

## Coding Style

- Follow the style of the file you are editing.
- Respect the `.editorconfig` settings (indent style, line endings, etc.).
- C/C++ code generally follows a K&R-adjacent style — use 4-space indentation, no tabs.
- For the React web configurator (`www/`), follow the existing component and hook patterns.

---

## Commit Messages

- Use the imperative mood: *"Add support for X"*, not *"Added support for X"*.
- Keep the subject line under 72 characters.
- Reference issues where relevant: `Fixes #123`, `Closes #456`.

---

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](LICENSE) that covers this project.
