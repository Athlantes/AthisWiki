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
- `commands` — Custom Items that can run commands when right-clicked

---

## Example Loot Tables

- Common Loot Crate
```
common_lootcrate: # Entry name - Can be anything in this format (no spaces and special characters)
  chance: 0.7  # 70% chance to pick this loot table
  min-items: 1 # Minimum items that can be in the crate
  max-items: 5 # Maximum items that can be in the crate
  loot:
    iron_ingot: # Entry name - Can be anything in this format (no spaces and special characters)
      material: IRON_INGOT # Java ID materials, UPPERCASE
      min: 3 # Minimum items that can be in this stack
      max: 8 # Maximum items that can be in this stack
      chance: 0.8 # Chance for this item to spawn in this loot table
  commands:
    creative: # Entry name - Can be anything in this format (no spaces and special characters)
      name: "&eCreative Gamemode" # Name of the item (Visible In-Game)
      material: PAPER # Java ID materials, UPPERCASE
      amount: 1 # Number of items given in this lootcrate
      command: "gamemode creative %player%" # Executed command when right-click
      executor: console # Executor of the command (console/player)
      chance: 1 # The chance for this command to spawn in this loot table
      consume_on_use: true # If the item will be consumed when right-click or not
      cooldown_seconds: 60 # Cooldown before you can use another voucher of the same time
      silent: false # If the command will runt silent (No global output in chat)
      lore:
       - "&eGives you Creative!"
        - ""
        - "&7Right Click to redeem"
    starter_bundle:
      name: "&6Starter Bundle"
      material: BUNDLE
      amount: 1
      commands:
       - "give %player% minecraft:stone 64"
       - "give %player% minecraft:oak_log 32"
      executor: console
      chance: 0.5
      consume_on_use: true
      cooldown_seconds: 300
      silent: true
      lore:
       - "&7Redeem to receive starter items"
```

- Uncommon Loot Crate
```
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