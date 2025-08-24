# Configuration – Athi's Airdrops ⚙️

Athi's Airdrops is fully configurable via **`config.yml`**.  

## Automatic Airdrops
- `autostart`: `false` — Start automatic airdrops on server launch.  
- `spawn_interval_seconds`: `240` — Interval between automatic airdrops.  
- `time-before-despawn`: `120` — Duration airdrop stays in the world.  

## Location Settings
- `world`: `world` — Default world for drops.  
- `center_x` / `center_z`: Coordinates for center of drop area.  
- `spawn_radius`: `1000` — Maximum radius around center for crate spawn.  
- `max_location_attempts`: `100` — Max attempts to find valid spawn location.  
- `min_players_to_spawn`: `3` — Minimum players online for airdrop to spawn.  

## Chunk Handling
- `spawn_in_loaded_chunks_only`: `false` — Only spawn in loaded chunks.  
- `load_generated_chunk_if_unloaded`: `true` — Load chunks if unloaded.  

## Misc Settings
- `replace_existing_block`: `true` — Replace blocks where crates land.  
- `particle_interval_ticks`: `10` — Particle effect refresh rate.  

## Compass Tracking
- `enable-compass`: `true` — Enable compass tracking system.  
- `compass-cooldown`: `10` seconds — Cooldown between compass uses.  

## Lock System
- `lock-airdrop`: `true` — Lock crates before looting.  
- `time-before-unlock`: `30` seconds — Time until crate can be looted.  

## Hologram Settings - Do not touch if you don't know what are you doing
hologram:
-  `create_delay_ticks`: `2` — Delay before the holograms are created.
-  `spawn_retries`: `3` — Retries to spawn hologram if fails.
-  `retry_delay_ticks`: `10` — Delay between retries


---

# Loot Tables – Athi's Airdrops 🎁

All loot crates are defined in **`loot.yml`**. Each loot table has:

- `chance` — Probability of this table being selected.
- `min-items` / `max-items` — Number of items spawned.
- `loot` — Vanilla items with material, min/max, chance, enchantments.
- `itemsadder_loot` — Custom ItemsAdder items, same structure.

---

## Example Loot Tables

### Common Loot Crate
```yaml
common_lootcrate:
  chance: 0.7
  min-items: 1
  max-items: 5
  loot:
    iron_ingot:
      material: IRON_INGOT
      min: 3
      max: 8
      chance: 0.8
```
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