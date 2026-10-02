# Changelog OctoWoW – ShaguTweaks-extras

> Branch `octowow` = Stand aus Henrys Installation „OctoWoW – HD Upgrade“ (WoW 1.12). Eigene Anpassungen sind im Code mit `-- [patch]` markiert.

**Basis:** shagu/ShaguTweaks-extras `e5140e5` (2025-08-15)

## Änderungen

### mods/worldmap-reveal.lua – Kartenaufdeckung für Turtle/Octo-Zonen
- **Zonentabellen ersetzt:** Die Overlay-Geometrie (Breite, Höhe, Offset) für 53 Zonen wurde durch die Werte des Turtle/OctoWoW-Clients ersetzt. Dadurch sind auch neue Gebiete wie „Anchor's Edge“, „Sparkwater Port“ oder „Ruins of Zul'Rasaz“ enthalten.
- **Echte Client-Geometrie hat Vorrang:** Für bereits erkundete Overlays liefert der Client die korrekten Maße. Das Modul hat diese bisher verworfen und auch dort die fest eingetragene Tabelle benutzt, die bei server-eigenen Zonen oft falsch ist. Jetzt werden die Client-Werte verwendet (`realgeom`).
- **Doppelt belegte Positionen werden übersprungen:** Tabelleneinträge, die sich eine Position teilen, stapelten Kartenteile übereinander (z. B. Thalassian Highlands). Solche unerkundeten Overlays werden nicht mehr gezeichnet, statt falsch.
