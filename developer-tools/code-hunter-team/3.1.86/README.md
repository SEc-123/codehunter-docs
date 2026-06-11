# Code Hunter Team Developer Tools 3.1.86

This folder contains developer-side tools for Code Hunter Team 3.1.86.

The developer tools are separate from the signed Code Hunter Team desktop app. Team administrators use the desktop app to create agent enrollments; developers install these tools in their local IDE/workspace and enroll with the one-time code shown by Team Agent Management.

## Artifacts

| Platform | File | Status | SHA-256 |
| --- | --- | --- | --- |
| macOS x64 | [Code Hunter Team Developer Tools-3.1.86-x64.dmg](macos/darwin-x64/Code%20Hunter%20Team%20Developer%20Tools-3.1.86-x64.dmg) | Developer ID signed, Apple notarized, stapled, Gatekeeper accepted | `5fa688e78cd8b7a632763d97902c89a836a7f2392c22700a9b86977e1a52b22b` |
| macOS arm64 | [Code Hunter Team Developer Tools-3.1.86-arm64.dmg](macos/darwin-arm64/Code%20Hunter%20Team%20Developer%20Tools-3.1.86-arm64.dmg) | Developer ID signed, Apple notarized, stapled, Gatekeeper accepted | `29c60d28ae9d4e6c4d630e312b02db33ebaf07fb81d742e7a2e13d3763d396d8` |
| Windows x64 | [CodeHunter-Team-Developer-Tools-3.1.86-win32-x64-unsigned-for-signing.zip](windows/win32-x64/CodeHunter-Team-Developer-Tools-3.1.86-win32-x64-unsigned-for-signing.zip) | Unsigned Authenticode handoff for signing; do not distribute to developers yet | `f4bcdc33d304da6a57c3e16774208d10fe2e125b9a20a653b871aeefc0924992` |

## macOS Verification

The macOS DMGs contain:

- `bin/code-hunter-team-agent`
- `bin/code-hunter-team-agent-lsp`
- `install.sh`
- `manifest.json`

Both embedded binaries and both DMGs were signed with:

```text
Developer ID Application: Arvanta Cyber Inc. (6G85L86XV7)
```

Apple notarization IDs:

| Platform | Notarization ID |
| --- | --- |
| macOS x64 | `48b12937-fc0f-4d83-b51f-8f9225c23fb4` |
| macOS arm64 | `6a964995-4266-4731-a269-9124cf4d49e0` |

The macOS release manifest is available at [macos/developer-tools-release-3.1.86.json](macos/developer-tools-release-3.1.86.json).

## Windows Signing Handoff

The Windows package is intentionally unsigned. It is for Authenticode signing only.

Sign every `sign_required=true` EXE in [windows/win32-x64/SIGNING_MANIFEST.json](windows/win32-x64/SIGNING_MANIFEST.json), preserving the same relative paths:

- `bin/code-hunter-team-agent.exe`
- `bin/code-hunter-team-agent-lsp.exe`

Before signing, both PE certificate tables are empty (`virtualAddress=0`, `size=0`). After signing, return the signed EXEs or a zip with the same `bin/` layout so the final Windows developer-tools package can be assembled and marked distributable.

## Linux Status

Linux x64 developer tools are not included in this folder. The local build host has the Rust `x86_64-unknown-linux-musl` target installed, but the build is currently blocked by the missing `x86_64-linux-musl-gcc` C toolchain required by `ring`.
