# Atesto agent — releases

This repository only distributes the Atesto agent. Each release ships the binaries for macOS (Apple Silicon and Intel) and Windows (x64), plus a `SHA256SUMS` file. The source code does not live here.

## Install

Use the command the Atesto **Devices** screen generates. It carries your organization's install key, downloads the binary from this repository, checks its SHA-256 against the value the Atesto server reports, and installs the service. If the hash does not match, nothing is installed.

## Verify by hand

Download the binary and the `SHA256SUMS` file from the same release, then compare:

- macOS: `shasum -a 256 atesto-sentinel-darwin-arm64`
- Windows: `Get-FileHash .\atesto-sentinel-windows-amd64.exe -Algorithm SHA256`

## What the agent does

It reads, and only reads: the machine's name, serial number and whether the company manages it; the OS version; the security configuration (disk encryption, firewall, antivirus, screen lock, Secure Boot and updates); installed programs; the AI tools installed or running; and the name of the account using the machine, which the company can switch off.

It changes nothing on the machine, and it never reads file, e-mail or message content, the screen, the clipboard, visited sites, keystrokes, or conversations with AI tools.

## Signing

The binaries are not yet code-signed by Apple and Microsoft; that comes in an upcoming release. Until then, the SHA-256 is how integrity is checked.
