# BetterLoot (Performance Enhanced)

BetterLoot is a powerful and lightweight loot container modification plugin for Rust, designed to fully control and customize loot tables with support for rarity, loot groups, attachments, ammo, and more.

This version includes significant runtime performance optimizations and bug fixes for improved server stability under heavy load.

---

## Features

- Fully customizable loot tables per container
- Loot Groups system with probability-based selection
- Weapon attachments and ammo generation
- Item durability control
- Guaranteed item support
- Item blacklist system
- Prefab-based container control
- Blueprint generation control
- Scrap multipliers and loot multipliers
- Duplicate item handling controls
- Compatible with CustomLootSpawns

---

## Performance Improvements (This Version)

- Replaced dictionary iteration with cached indexed arrays
- Reduced runtime allocations during loot generation
- Cached sanitized item names (removed repeated regex calls)
- Cached ammo definitions (removed repeated lookups)
- Optimized attachment and ammo application logic
- Replaced duplicate tracking lists with hash sets
- Reduced redundant container and attachment scans

These changes significantly reduce CPU usage and GC pressure during heavy loot spawning.

---

## Bug Fixes

- Fixed bonus item duplicate logic removing the wrong item
- Bonus items now correctly respect duplicate tracking
- Guaranteed items now correctly apply:
  - display names
  - attachments
  - ammo
  - durability
  - blacklist checks
- Fixed attachment items not being removed on failed application
- Fixed probability calculation using incorrect data types
- Improved item validation and cleanup

---

## Installation

1. Place `BetterLoot.cs` in your `/oxide/plugins/` directory
2. Restart your server or reload the plugin:
   ```
   oxide.reload BetterLoot
   ```

---

## Configuration

The plugin will generate a configuration file at:

`/oxide/config/BetterLoot.json`

Key settings include:
- Blueprint probability
- Loot multiplier
- Scrap multiplier
- Duplicate item rules
- Prefab monitoring system

---

## Data Files

Located in:

`/oxide/data/BetterLoot/`

- `LootTables.json` — container loot definitions
- `LootGroups.json` — reusable loot group profiles
- `Blacklist.json` — blocked items

---

## Permissions

- `betterloot.admin` — allows admin commands

---

## Commands

- `/blacklist additem "itemname"`
- `/blacklist deleteitem "itemname"`
- `/looty "table-id"`

---

## Notes

- Supports wipe-aware prefab updates
- Automatically detects new containers (optional)
- Compatible with Looty editor: https://looty.cc/betterloot-v4

---

## Credits

## Credits
- dcode — Original author.
- Fujicura — Maintainer.
- Misticos — Maintainer.
- Tryhard — Maintainer.
- TGWA — Author of Version 4 & Current Maintainer.
- Performance optimization and fixes by ***Milestorme***

---

## License

Use freely on your server. Do not redistribute without proper credit.
