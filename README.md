# HoneyBees Quests 🐝🍯

## Overview
HoneyBees Quests is a third-person simulation game developed in Unreal Engine.  
The player takes the role of a beekeeper who collects pollen, transforms it into honey (the main currency), and buys bees to assist in their progression.  
The game includes mini-games (Tower Defense, DDR, Puzzle) and quests that unlock new areas and ultimately lead to a battle against a giant insect boss.

---

## Core Gameplay Loop
1. **Collect pollen** in flower fields.
2. **Convert pollen into honey** at the hive.
3. **Buy bee eggs** to obtain allies.
4. **Complete quests** to unlock new areas and mini-games.
5. **Progression**: unlock all zones, gather all bees, and defeat the giant insect.

---

## Main Systems

### Player
- Third-person movement
- Inventory: pollen, honey, bees
- HUD displaying resources and active quests
- Save/load system

### Bee System
- 15 bee types divided into 3 rarities
- Bees follow the player
- Bees affect collection speed/amount

### Economy
- Main currency: honey
- Shop for buying bee eggs
- Rarity chances managed through **DataTables**

### Zones
- Multiple flower zones
- Locked/unlocked progression based on quests
- Trigger-based area detection

### Quest System
- Objectives: collect pollen, complete mini-games, etc.
- Rewards: honey, bees, zone unlocks
- Managed via **DataTables** for easy expansion

### Mini-Games
- **Tower Defense**: enemy waves, defensive bee placement
- **DDR-style rhythm game**: music-timed input
- **Puzzle (Candy Crush-like)**: flower matching grid

### Boss Fight
- Giant insect enemy
- Bees auto-attack
- Boss HP bar and victory conditions

---
  
## Tools & Best Practices

- **Enums**
  - `EBeeRarity` → Common, Rare, Legendary
  - `EQuestType` → Collect, TowerDefense, DDR, Puzzle, BossFight
  - `EZoneState` → Locked, Unlocked

- **Structs**
  - `FBeeData` → Name, Rarity, Bonus, Mesh
  - `FQuestData` → ID, Type, Objective, Reward
  - `FShopItem` → Name, Price, Type

- **DataTables**
  - Centralize all gameplay data (bees, quests, shop)
  - Easily add new content without recompiling

- **Blueprint → C++ workflow**
  - Prototype in Blueprints for fast iteration
  - Migrate to C++ for optimized logic and maintainability
  - Keep UI and FX in Blueprints for flexibility

---

## Final Goal
A stable and playable prototype fully implemented in C++ for core systems, with UI and visuals in Blueprints.  
The game should include the full gameplay loop, quests, mini-games, and a final boss fight.
