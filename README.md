# Hackboard

Hackboard is a keyboard customizer for macOS that extends what is traditionally possible with a keyboard. It turns letter keys into modifiers (like ⌘, ⌥, ⌃, ⇧) enabling namespaced shortcut systems that are easier to recall. Hackboard is built on [Karabiner Elements](https://karabiner-elements.pqrs.org/), the trusted open-source foundation for keyboard customization on macOS, with a visual editor on top.

## Beta

Hackboard is in public beta. It's functional and stable for daily use, but you may encounter rough edges. Your feedback is what shapes the product — please [report bugs and share ideas](https://github.com/farbe-software/hackboard-releases/issues).

## How It Works

Hackboard is a visual keyboard editor that includes Hb-Karabiner-Elements (a fork of Karabiner Elements), enabling:  

- **Letter keys as standalone modifiers** — e.g. holding `A`, then pressing `T` maps to an action, e.g. 'Open Terminal'. No prior modifier needed. Hackboard's key rollover behaviour enables standalone letter keys to act as modifiers without interfering with normal typing.
- **Standard modifier + letter key chains** — e.g. hold Left Command, then hold `A`, then press `T`. Standard modifiers and letter-key modifiers work together seamlessly. At least four letter keys can be chained (subject to hardware limitations on some machines).
- **Use of right modifiers with separate mapping** - typically unused right modifiers become useful and help make your keyboard more ergonomic.  
- **Triggering of actions** - such as shell commands, remapped standard shortcuts, simple remapping of keys to a different output (great for remapping to more ergonomic alternatives), and text insertion. 

*For Karabiner-Elements users: Hb-Karabiner-Elements is based on and fully compatible with Karabiner Elements 15.0.0. Hackboard's configs are added at the top of the first profile as the first rule object.*

## Get Started

### Requirements

- macOS 13 (Ventura) or later
- Apple Silicon (Intel builds are included but not actively supported)

### Install

Download the latest `.dmg` from the [Releases page](https://github.com/farbe-software/hackboard-releases/releases/latest) and open the installer package inside it. The installer includes both Hackboard and Hb-Karabiner-Elements — no separate Karabiner download is needed.

*For Karabiner-Elements users: Your existing Karabiner-Elements installation will need to be uninstalled first. Hb-Karabiner-Elements is currently based on version 15.0.0. We currently don't support automatic migration from other versions.*

### First Launch

After installation completes, **Hb-Karabiner-Elements** starts automatically and requests the necessary macOS permissions (Input Monitoring and a virtual HID driver approval). Follow the dialogs in the Hb-Karabiner-Elements UI until it no longer shows messages for missing permissions.

Note that the HID driver bundled with Hb-Karabiner-Elements is a signed build from pqrs.

*For Karabiner-Elements users: If there are problems, try deactivating and reactivating permissions.*

Once permissions are granted, **start Hackboard**. On launch, Hackboard runs an initial sanity check and asks for access to the folder containing `karabiner.json` via a system folder picker. This is required because Hackboard is sandboxed — it cannot access files outside its sandbox without explicit user consent.

Once folder access is granted, Hackboard loads an example configuration showcasing its capabilities. 



You can then also add your first own keymaps through the sidebar. 

*For Karabiner-Elements users:*  
*The configuration is injected into your `karabiner.json` as follows.*

- *Hackboard writes into the **first profile** in your karabiner.json*
- *It creates a single entry in `complex_modifications.rules` with the description `"hackboard"`*
- *All layer definitions are stored as manipulators of type `"layer"` inside that rule*
- *Only the Hackboard rule is touched — all other rules, profiles, and settings remain unchanged* 

### Updates

After installation, Hackboard checks for updates automatically and notifies you when a new version is available. Automatic updates are currently not supported for the Hb-Karabiner-Elements component. Future updates to it may require full uninstallation and re-installation. We are planning to add automatic updates here as well. 

## Privacy & Security

All keyboard input is processed locally by Karabiner's virtual keyboard driver. No keystrokes, usage patterns, or personal data leave your machine.

Hb-Karabiner-Elements **does not modify the Karabiner Elements security model**. The security architecture — including the root-privileged core service, virtual HID driver restrictions, and closed-process design — is inherited unchanged from upstream. For details, see the [Karabiner Elements security documentation](https://karabiner-elements.pqrs.org/docs/help/advanced-topics/security/).

Hackboard's only network activity:
- **Update checks** — Sparkle periodically fetches a small XML file from this repository to check for new versions
- **Crash reports** — anonymous crash data is sent to Sentry when the app encounters an error (`sendDefaultPii` is disabled)

## Feedback & Issues

Found a bug or have a suggestion? [Open an issue](https://github.com/farbe-software/hackboard-releases/issues) on this repository.

## License

Hackboard is proprietary software by [Farbe Software UG (haftungsbeschr.)](https://www.hackboard.app). See the [Terms of Service](https://www.hackboard.app/tos) for details.


## Examples

Hackboard ships with an example configuration that demonstrates its capabilities. The examples below are taken directly from it.

### A-layer: App Launcher (with sublayers)

Hold `A` to launch or switch to apps. Some entries use sublayers — a second letter key that narrows the selection.

| Hold | Then press | Action |
|------|------------|--------|
| `A` | `C` | Open Chrome |
| `A` `C` | `M` | Open Google Maps in Chrome |
| `A` `C` `M` | `K` | Open Google Maps in Chrome in a Specific Location|
| `A` | `F` | Open Finder |
| `A` `F` | `D` | Open Downloads folder |

The sublayer `A` → `C` → `M` demonstrates three-key chaining: hold `A`, press `C` to narrow to Chrome actions, then press `M` for Google Maps.


### Arrow Actions (move/select/delete, vim-inspired)

#### F-layer: Move Cursor / Use Arrow Keys 


Hold `F` for moving the cursor / arrow keys, `S` and `D` for corresponding select and delete actions. The arrow keys are mapped to `J` `K` `L` `;` on the home row — inspired by vim's `hjkl`. Hit enter and escape without stretching your pinky. 

| Hold | Then press | Action |
|------|------------|--------|
| `F` | `J` | Move cursor left |
| `F` | `K` | Move cursor down |
| `F` | `L` | Move cursor up |
| `F` | `;` | Move cursor right |
| `F` | `U` | Move cursor one word left |
| `F` | `P` | Move cursor one word right |
| `F` | `H` | Move cursor to line start |
| `F` | `'` | Move cursor to line end |
| `F` | `Space` | Enter |
| `F` | `A` | Escape |

Tap `F` by itself and it types "f" as usual.

#### S-layer: Selection 

Hold `S` to select text. Uses the same spatial layout as the F-layer, so the muscle memory carries over.

| Hold | Then press | Action |
|------|------------|--------|
| `S` | `J` | Select left |
| `S` | `K` | Select down |
| `S` | `L` | Select up |
| `S` | `;` | Select right |
| `S` | `U` | Select one word left |
| `S` | `P` | Select one word right |
| `S` | `H` | Select to line start |
| `S` | `'` | Select to line end |
| `S` | `F` | Select entire line |
| `S` | `A` | Select all |

### D-layer: Delete

Hold `D` to delete. Same spatial layout again — learn one, know all three.

| Hold | Then press | Action |
|------|------------|--------|
| `D` | `J` | Delete character left (Backspace) |
| `D` | `;` | Delete character right (Forward Delete) |
| `D` | `U` | Delete word left |
| `D` | `P` | Delete word right |
| `D` | `H` | Delete to line start |
| `D` | `'` | Delete to line end |
| `D` | `F` | Delete entire line |

### Number Row on Home Row

Hold Right Command to type numbers from the home row, eliminating the reach to the number row.

| Hold | Then press | Result |
|------|------------|--------|
| `Right ⌘` | `A` | 1 |
| `Right ⌘` | `S` | 2 |
| `Right ⌘` | `D` | 3 |
| `Right ⌘` | `F` | 4 |
| `Right ⌘` | `G` | 5 |
| `Right ⌘` | `H` | 6 |
| `Right ⌘` | `J` | 7 |
| `Right ⌘` | `K` | 8 |
| `Right ⌘` | `L` | 9 |
| `Right ⌘` | `;` | 0 |

