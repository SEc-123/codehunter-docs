# Code Hunter Team Developer Tools 3.1.86

This folder contains ready-to-install developer plugins for Code Hunter Team 3.1.86.

Team administrators create developer agent enrollments in the signed Code Hunter Team desktop app. Developers install one of the plugins below, then enroll with the one-time code shown by Team Agent Management.

## Download

| IDE | File | Status | SHA-256 |
| --- | --- | --- | --- |
| VS Code | [codehunter-team-vscode-3.1.86.vsix](plugins/vscode/codehunter-team-vscode-3.1.86.vsix) | Ready to install | `fb1a50908f10f64fce4b3fcbaaa7b87e1bf5b5efe128c3f74ee68ccdadae60cc` |
| JetBrains IDEs | [codehunter-team-jetbrains-3.1.86.zip](plugins/jetbrains/codehunter-team-jetbrains-3.1.86.zip) | Ready to install | `e853805ff23544b6a35e7b4940578c77f41f23e68e399000a9d7dbc19c6258fa` |

Both plugin packages bundle the Code Hunter Team agent and LSP binaries for:

- `darwin-arm64`
- `darwin-x64`
- `linux-x64`
- `win32-x64`

## Install

VS Code:

```bash
code --install-extension codehunter-team-vscode-3.1.86.vsix
```

JetBrains IDEs:

Install `codehunter-team-jetbrains-3.1.86.zip` from **Settings / Plugins / Install Plugin from Disk**.

## Verification

The VS Code package was checked with `scripts/ide-install-smoke.mjs` and contains:

- `extension/bin/darwin-arm64/code-hunter-team-agent`
- `extension/bin/darwin-arm64/code-hunter-team-agent-lsp`
- `extension/bin/darwin-x64/code-hunter-team-agent`
- `extension/bin/darwin-x64/code-hunter-team-agent-lsp`
- `extension/bin/linux-x64/code-hunter-team-agent`
- `extension/bin/linux-x64/code-hunter-team-agent-lsp`
- `extension/bin/win32-x64/code-hunter-team-agent.exe`
- `extension/bin/win32-x64/code-hunter-team-agent-lsp.exe`

The JetBrains package was built with `buildPlugin verifyPluginStructure` and contains the same `bin/` layout inside `codehunter-team-jetbrains-0.1.0.jar`.

Embedded binary verification:

- macOS binaries are signed with `Developer ID Application: Arvanta Cyber Inc. (6G85L86XV7)`.
- Windows binaries have non-empty Authenticode PE certificate tables.
- Linux binaries are `ELF 64-bit LSB pie executable, x86-64`, built for GNU/Linux.

## Provenance

The standalone macOS agent DMGs remain available for direct CLI distribution:

| Platform | File | Status | SHA-256 |
| --- | --- | --- | --- |
| macOS x64 | [Code Hunter Team Developer Tools-3.1.86-x64.dmg](macos/darwin-x64/Code%20Hunter%20Team%20Developer%20Tools-3.1.86-x64.dmg) | Developer ID signed, Apple notarized, stapled, Gatekeeper accepted | `5fa688e78cd8b7a632763d97902c89a836a7f2392c22700a9b86977e1a52b22b` |
| macOS arm64 | [Code Hunter Team Developer Tools-3.1.86-arm64.dmg](macos/darwin-arm64/Code%20Hunter%20Team%20Developer%20Tools-3.1.86-arm64.dmg) | Developer ID signed, Apple notarized, stapled, Gatekeeper accepted | `29c60d28ae9d4e6c4d630e312b02db33ebaf07fb81d742e7a2e13d3763d396d8` |

Apple notarization IDs:

| Platform | Notarization ID |
| --- | --- |
| macOS x64 | `48b12937-fc0f-4d83-b51f-8f9225c23fb4` |
| macOS arm64 | `6a964995-4266-4731-a269-9124cf4d49e0` |

The Windows signing handoff package is retained for audit only:

- [CodeHunter-Team-Developer-Tools-3.1.86-win32-x64-unsigned-for-signing.zip](windows/win32-x64/CodeHunter-Team-Developer-Tools-3.1.86-win32-x64-unsigned-for-signing.zip)
- [windows/win32-x64/SIGNING_MANIFEST.json](windows/win32-x64/SIGNING_MANIFEST.json)
