# Changelog OctoWoW – ShaguTweaks-extras

> Branch `octowow` = the state from Dinkleberrrg's "OctoWoW – HD Upgrade" install (WoW 1.12). Own changes are marked with `-- [patch]` in the code.

**Base:** shagu/ShaguTweaks-extras `e5140e5` (2025-08-15)


## Releases

Version scheme: `<upstream version>-octo.<n>`. Each release is a git tag `v<version>`; older versions can be downloaded from the tag page on GitHub.

### 2025.08.15-octo.2 – 2026-10-04
- Code comments of the changes translated to English. No functional change.

### 2025.08.15-octo.1 – 2026-10-03
- First tagged release with the changes listed below.

## Changes

### mods/worldmap-reveal.lua – map reveal for Turtle/Octo zones
- **Zone tables replaced:** The overlay geometry (width, height, offset) of 53 zones was replaced with the values from the Turtle/OctoWoW client. This also covers new areas such as "Anchor's Edge", "Sparkwater Port" and "Ruins of Zul'Rasaz".
- **Real client geometry wins:** For overlays you have already explored, the client reports the correct size. The module used to discard it and use the hard-coded table instead, which is often wrong for server-specific zones. The client values are now used (`realgeom`).
- **Overlapping positions are skipped:** Table entries that share a position stacked map tiles on top of each other (e.g. Thalassian Highlands). Such unexplored overlays are no longer drawn rather than drawn wrong.
