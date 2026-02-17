# Hackboard

Hackboard is a keyboard customization app for macOS that goes beyond what is traditionally possible with a computer keyboard. Hackboard turns letter keys into modifiers, enabling namespaced shortcut systems where shortcuts are grouped by context and easier to recall. Built on [Karabiner Elements](https://karabiner-elements.pqrs.org/), the trusted open-source foundation for keyboard customization on macOS, with a visual editor on top.

This is the releases repository. Downloads, changelogs, and the Sparkle update feed are published here.

**Website:** [www.hackboard.app](https://www.hackboard.app)

## Beta

Hackboard is in public beta. It's functional and stable for daily use, but you may encounter rough edges. Your feedback is what shapes the product — please [report bugs and share ideas](https://github.com/farbe-software/hackboard-releases/issues).

## Get Started

### Requirements

- macOS 13 (Ventura) or later
- Apple Silicon (Intel builds are included but not actively supported)

### Install

Download the latest `.dmg` from the [Releases page](https://github.com/farbe-software/hackboard-releases/releases/latest) and open the installer package inside it. The installer includes Hackboard and a bundled fork of Karabiner Elements — no separate Karabiner download is needed.

### First Launch

On first launch, Hackboard walks you through a short setup:

1. **Grant permissions** — Karabiner needs Input Monitoring and a virtual HID driver permission in System Settings. The setup dialog guides you through each one.
2. **Grant config access** — Hackboard asks for access to the Karabiner configuration folder via a folder picker.

Once all checks pass, you're ready to go. For more details on the Karabiner permissions, see the [Karabiner Elements documentation](https://karabiner-elements.pqrs.org/docs/getting-started/installation/).

### Updates

After installation, Hackboard checks for updates automatically and notifies you when a new version is available.

## Privacy & Security

All keyboard input is processed locally by Karabiner's virtual keyboard driver. No keystrokes, usage patterns, or personal data leave your machine. The Karabiner fork used by Hackboard has its upstream auto-updater fully disabled.

Hackboard's only network activity:
- **Update checks** — Sparkle periodically fetches a small XML file from this repository to check for new versions
- **Crash reports** — anonymous crash data is sent to Sentry when the app encounters an error (`sendDefaultPii` is disabled)

## Feedback & Issues

Found a bug or have a suggestion? [Open an issue](https://github.com/farbe-software/hackboard-releases/issues) on this repository.

## License

Hackboard is proprietary software by [Farbe Software UG (haftungsbeschr.)](https://www.hackboard.app). See the [Terms of Service](https://www.hackboard.app/tos) for details.
