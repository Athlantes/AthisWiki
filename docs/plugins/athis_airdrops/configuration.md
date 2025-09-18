## Configuration – Athi's Airdrops ⚙️

Athi's Airdrops is fully configurable via **`config.yml`**.  

### Automatic Airdrops
- `autostart`: `false` — Start automatic airdrops on server launch.  
- `spawn_interval_seconds`: `240` — Interval between automatic airdrops.  
- `time-before-despawn`: `120` — Duration airdrop stays in the world.  

### Location Settings
- `world`: `world` — Default world for drops.  
- `center_x` / `center_z`: Coordinates for center of drop area.  
- `spawn_radius`: `1000` — Maximum radius around center for crate spawn.  
- `max_location_attempts`: `100` — Max attempts to find valid spawn location.  
- `min_players_to_spawn`: `3` — Minimum players online for airdrop to spawn.  

### Chunk Handling
- `spawn_in_loaded_chunks_only`: `false` — Only spawn in loaded chunks.  
- `load_generated_chunk_if_unloaded`: `true` — Load chunks if unloaded.  

### Misc Settings
- `replace_existing_block`: `true` — Replace blocks where crates land.  
- `particle_interval_ticks`: `10` — Particle effect refresh rate.  

### Animation options
-  `enabled`: `true` — true = play drop animation; false = place chest immediately
-  `height`: `50` — starting height in blocks above target
-  `interval_ticks`: `2` — task interval in ticks (how often the armorstand teleports)
-  `blocks_per_tick`: `0.1` — blocks per tick the armorstand descends (speed)

### Compass Tracking
- `enable-compass`: `true` — Enable compass tracking system.  
- `compass-cooldown`: `10` seconds — Cooldown between compass uses.  

### Lock System
- `lock-airdrop`: `true` — Lock crates before looting.  
- `time-before-unlock`: `30` seconds — Time until crate can be looted.  

### Hologram Settings - Do not touch if you don't know what are you doing
-  `create_delay_ticks`: `2` — Delay before the holograms are created.
-  `spawn_retries`: `3` — Retries to spawn hologram if fails.
-  `retry_delay_ticks`: `10` — Delay between retries


---

## Loot Tables – Athi's Airdrops 🎁

All loot crates are defined in **`loot.yml`**. Each loot table has:

- `chance` — Probability of this table being selected.
- `min-items` / `max-items` — Number of items spawned.
- `loot` — Vanilla items with material, min/max, chance, enchantments.
- `itemsadder_loot` — Custom ItemsAdder items, same structure.
- `mmoitems_loot` — Custom MMOItems items.
- `nexo_loot` — Custom Nexo items.
- `commands` — Custom Items that can run commands when right-clicked.

---

## Example Loot Tables

- Common Loot Crate
```yaml
common_lootcrate:
  chance: 0.7  # 70% chance to pick this loot table
  min-items: 1
  max-items: 5
  loot:
    iron_ingot:
      material: IRON_INGOT
      min: 3
      max: 8
      chance: 0.8
  commands:
    creative:
      name: "&eCreative Gamemode"
      material: PAPER
      amount: 1
      console_commands:
        - "gamemode creative %player%"
      chance: 1
      consume_on_use: true
      cooldown_seconds: 60
      lore:
        - "&eGives you Creative!"
        - ""
        - "&7Right Click to redeem"
    starter_bundle:
      name: "&6Starter Bundle"
      material: BUNDLE
      amount: 1
      # Commands to execute as console
      console_commands:
        - "give %player% minecraft:stone 64"
        - "give %player% minecraft:oak_log 32"
      # Commands to execute as player (optional)
      player_commands:
        - "say Hello %player%"
      chance: 0.5
      consume_on_use: true
      cooldown_seconds: 300
      lore:
        - "&7Redeem to receive starter items"
```

- Uncommon Loot Crate
```yaml
uncommon_drop:
  chance: 0.3
  min-items: 1
  max-items: 5
  loot:
    diamond_sword:
      material: DIAMOND_SWORD
      min: 1
      max: 1
      chance: 0.4
      enchantments:
        SHARPNESS: 3
        UNBREAKING: 2
    golden_apple:
      material: GOLDEN_APPLE
      min: 1
      max: 2
      chance: 0.5
  itemsadder_loot:
    banana:
      material: "iasurvival:banana"
      min: 1
      max: 1
      chance: 0.6
```

- Legendary Loot Crate
```yaml
legendary_drop:
  chance: 0.1  # 10% chance to pick this loot table
  min-items: 1
  max-items: 5
  loot:
    netherite_sword:
      material: NETHERITE_SWORD
      min: 1
      max: 1
      chance: 0.4
  mmoitems_loot:
    long_sword:
      type: SWORD
      id: LONG_SWORD
      min: 1
      max: 1
      chance: 1.0
    blaze_wand:
      type: WAND
      id: BLAZE_WAND
      min: 1
      max: 1
      chance: 0.5
  nexo_loot:
    forest_axe:
      nexo_id: "forest_axe"
      min: 1
      max: 1
      chance: 1.0
```