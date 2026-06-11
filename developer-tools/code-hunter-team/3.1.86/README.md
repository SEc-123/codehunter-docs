# Code Hunter Team Developer Tools 3.1.86

Install the Code Hunter Team developer plugin for your IDE. The plugin includes the Code Hunter Team agent and language service, so no separate agent download is required.

## Download

| IDE | Download | SHA-256 |
| --- | --- | --- |
| VS Code | [codehunter-team-vscode-3.1.86.vsix](plugins/vscode/codehunter-team-vscode-3.1.86.vsix) | `fb1a50908f10f64fce4b3fcbaaa7b87e1bf5b5efe128c3f74ee68ccdadae60cc` |
| JetBrains IDEs | [codehunter-team-jetbrains-3.1.86.zip](plugins/jetbrains/codehunter-team-jetbrains-3.1.86.zip) | `e853805ff23544b6a35e7b4940578c77f41f23e68e399000a9d7dbc19c6258fa` |

Supported developer platforms: macOS Apple Silicon, macOS Intel, Windows x64, and Linux x64.

## Install

VS Code:

```bash
code --install-extension codehunter-team-vscode-3.1.86.vsix
```

JetBrains IDEs:

Open **Settings / Plugins**, choose **Install Plugin from Disk**, then select `codehunter-team-jetbrains-3.1.86.zip`.

## Enroll

After installation, open Code Hunter Team in your IDE and enroll with the one-time code provided by your team administrator in Code Hunter Team Agent Management.

## Optional CLI Package For macOS

If your team wants to install the agent without an IDE plugin, use the signed macOS CLI package for your device:

| Platform | Download | SHA-256 |
| --- | --- | --- |
| macOS Apple Silicon | [Code Hunter Team Developer Tools-3.1.86-arm64.dmg](macos/darwin-arm64/Code%20Hunter%20Team%20Developer%20Tools-3.1.86-arm64.dmg) | `29c60d28ae9d4e6c4d630e312b02db33ebaf07fb81d742e7a2e13d3763d396d8` |
| macOS Intel | [Code Hunter Team Developer Tools-3.1.86-x64.dmg](macos/darwin-x64/Code%20Hunter%20Team%20Developer%20Tools-3.1.86-x64.dmg) | `5fa688e78cd8b7a632763d97902c89a836a7f2392c22700a9b86977e1a52b22b` |

The macOS packages are signed by Arvanta Cyber Inc. and notarized by Apple.
