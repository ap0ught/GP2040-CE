# Security Policy

## Supported Versions

The following versions of GP2040-CE firmware receive security updates:

| Version | Supported          |
| ------- | ------------------ |
| Latest stable release | :white_check_mark: |
| Previous minor release | :white_check_mark: |
| Older releases | :x: |

We strongly recommend always using the [latest release](https://github.com/OpenStickCommunity/GP2040-CE/releases/latest).

## Reporting a Vulnerability

We take security issues seriously. If you believe you have found a security vulnerability in GP2040-CE, please **do not** open a public GitHub issue.

Instead, please report it privately using one of the following methods:

1. **GitHub Private Security Advisory** (preferred):  
   Open a [private security advisory](https://github.com/ap0ught/GP2040-CE/security/advisories/new) directly on this repository. This keeps the report confidential until a fix is available.

2. **Direct contact**:  
   If you are unable to use GitHub's advisory system, you may contact the maintainers through the [OpenStick GP2040-CE Discord](https://discord.gg/k2pxhke7q8) server via a private message to an administrator.

## What to Include

To help us triage and address the issue quickly, please include:

- A description of the vulnerability and its potential impact
- Steps to reproduce the issue or a proof-of-concept
- Any relevant firmware version, board configuration, or hardware details
- Your suggested fix or mitigation, if you have one

## Response Process

1. **Acknowledgement** — We will acknowledge receipt of your report within **5 business days**.
2. **Assessment** — We will assess the severity and scope of the issue and keep you informed of our progress.
3. **Fix & Disclosure** — We will work on a fix and coordinate a disclosure timeline with you before publishing any details publicly.

## Scope

Security reports are most applicable to:

- The embedded web configurator (HTTP server running on device)
- USB descriptor handling and HID report parsing
- Flash memory read/write routines
- Any authentication or pairing logic (e.g., PS4/PS5 passthrough)

Reports about third-party libraries included in this project should be directed to the respective upstream maintainers. We will update bundled libraries in response to known CVEs.

## Out of Scope

- Physical access attacks (an attacker with physical access to the device can always reflash it)
- Denial-of-service against the embedded web server via flooding
- Issues already publicly disclosed upstream in [OpenStickCommunity/GP2040-CE](https://github.com/OpenStickCommunity/GP2040-CE)

## Thank You

We appreciate responsible disclosure and will credit reporters in release notes (unless you prefer to remain anonymous).
