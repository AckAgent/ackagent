# AckAgent

Out-of-band approval platform with hardware-backed cryptographic signing.

AckAgent routes signing and authorization requests from desktop tools and web applications to iOS devices, where users approve them with biometric authentication. Private keys never leave the device's Secure Enclave.

## Installation

### macOS (Homebrew)

```bash
brew install ackagent/tap/ackagent
```

### macOS (Package Installer)

Download the `.pkg` from the [latest release](https://github.com/ackagent/ackagent/releases/latest).

### Linux

Download the `.deb`, `.rpm`, or `.tar.gz` from the [latest release](https://github.com/ackagent/ackagent/releases/latest).

## Quick Start

1. Install the AckAgent iOS app from TestFlight
2. Login from your terminal:

```bash
ackagent login
```

3. Scan the QR code with the iOS app and verify the short authentication string

## Features

- **SSH Authentication** - Use your iOS device as an SSH security key
- **GPG Signing** - Sign git commits with biometric approval
- **Claude Code Hook** - Approve Claude Code permission requests from your phone

## SSH Setup

Add to `~/.ssh/config`:

```
SecurityKeyProvider /usr/local/lib/libackagent-sk.dylib
```

## GPG Signing

Configure git to use AckAgent:

```bash
git config --global gpg.program "ackagent gpg"
git config --global commit.gpgsign true
```

## Claude Code Hook

Auto-configure:

```bash
ackagent hook claude --configure
```

## License

Proprietary. See LICENSE file for details.
