# Vision: Soft Reset — Item Randomizer

A BepInEx mod for [Vision: Soft Reset](https://store.steampowered.com/app/1265910/Vision_Soft_Reset/) that shuffles all collectible items into random locations throughout the game, while guaranteeing every item remains logically obtainable.

---

## What is a Randomizer?

A randomizer is a game mod that shuffles items into different locations than intended. The goal is to find the items needed to progress while navigating a world that behaves unexpectedly. The concept was popularized by SNES classics like *The Legend of Zelda: A Link to the Past* and *Super Metroid*, and VSR's Metroidvania structure lends itself perfectly to the format.

---

## Features

- **Item Randomization** — All 52 collectible items (Creature Cards, Decryptors, Hearts, Phase Upgrades, and Orbs) are shuffled into random locations each run.
- **Logic-Guaranteed Seeds** — The randomizer uses a constraint-satisfaction algorithm to verify every item is reachable before accepting a seed. You will never be softlocked.
- **Puzzle Randomization** — Optionally randomizes the three in-game puzzles (Panel, Lab, and Music), with sticky note hints placed in the hub area showing the solutions.
- **Seed Control** — Enter a custom seed or generate a random one from the title screen. The same seed always produces the same randomization.
- **Out-of-Logic Detection** — If you somehow collect an item that shouldn't be reachable, the mod detects and logs it to help identify logic bugs.

---

## Installation

1. Install [BepInEx 5.x](https://github.com/BepInEx/BepInEx/releases) into your Vision: Soft Reset game folder.
2. Download the latest `ItemRandomizer.dll` from the [Releases](https://github.com/CaptainDapper/VSR-ItemRandomizer/releases) page.
3. Drop `ItemRandomizer.dll` into `<game folder>/BepInEx/plugins/`.
4. Launch the game.

---

## Usage

Controls are available on the **title screen**:

| Key | Action |
|-----|--------|
| `F1` | Toggle randomizer on/off |
| `F2` | Set username (for out-of-logic reports) |
| `F3` | Toggle puzzle randomization |
| `F5` | Enter a custom seed |
| `F6` | Generate a random seed |

Settings are saved to `rando-settings.cfg` in the game's persistent data folder and persist between sessions.

---

## Items

The randomizer shuffles 52 items across all locations:

| Type | Count |
|------|-------|
| Creature Cards | 24 |
| Decryptors | 16 |
| Phase Upgrades | 4 |
| Heart Upgrades | 4 |
| Orbs | 4 |

---

## Building from Source

**Requirements:**
- Visual Studio 2019+ (or any C# IDE with .NET 4.6 support)
- Vision: Soft Reset installed (for `Assembly-CSharp.dll` reference)
- BepInEx 5.x installed in the game folder

**Steps:**
1. Clone this repo.
2. Restore NuGet packages.
3. Update the post-build copy paths in `ItemRandomizer.csproj` to match your game install location.
4. Build in Debug or Release — the DLL will be copied to your plugins folder automatically.

---

## Related Repos

- [VSR-DependencyDiagramsAndOtherFunThings](https://github.com/CaptainDapper/VSR-DependencyDiagramsAndOtherFunThings) — Dependency diagrams and tooling for analyzing item logic.
- [VSR-ReversePolishTests](https://github.com/CaptainDapper/VSR-ReversePolishTests) — Unit tests for the logic expression (reverse Polish notation) evaluator.
