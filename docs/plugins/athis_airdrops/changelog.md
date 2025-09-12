# Changelog – Athi's Airdrops 📜

> ⚠️ Note: If you encounter any problems, you can join our Discord server for help: [Join Discord](https://discord.com/invite/PVVDJ7YE7b)

## v0.2.0a - Loot.yml Fix
- Fixed a bug where loot.yml didn't generate in 0.2.0.

## v0.2.0 - Command Vouchers
- Command Based Rewards:
Now, admins can create custom items that can be right-clicked to summon commands. For usage, check [Configuration](configuration.md) tab.
- If compass system is off, when an airdrop is spawned it will show coords instead of block distance.
- Added toggable animation in Config.yml
- Added customizable landing speed & height for animation in Config.yml

> ⚠️ Note: To ensure compatibility with the new updates, it’s recommended to **regenerate or edit your `config.yml`** after upgrading to v0.2.0. Check [Configuration](configuration.md) tab for changes.

## v0.1.4 - Fixes V2
- Lockdown Hologram no longer visible when `lock-airdrop` is false.  
- `/airdrop reload` now reloads `loot.yml` and stops the airdrop system to ensure proper functionality.  
- Plugin now checks for errors in `loot.yml` to verify item IDs.  
- Chance system simplified; Min/Max Items removed from `config.yml`.  
- Min/Max Items now defined per loot table.  
- Solved minimum player online problem for automatic drops.  
- Ghost chests removed on server stop to prevent leftover chests after restart.  
- Fixed ItemsAdder TileState error when closing chests with ItemsAdder active.

## v0.1.3 - Even More Fixes
- Improved cooldown logic for compass and manual commands.  
- Hologram management optimized for better stability.  
- Loot handling improved for performance and reliability.  
- Airdrop functionality refined for smoother gameplay.  
- Chunk loading and management optimized.  
- Animation and particle effects enhanced.  
- `/airdrop` command refactored for better tab completion.  
- Messaging system improvements for clarity.

> ⚠️ Note: To ensure compatibility with the new updates, it’s recommended to **regenerate your `config.yml`** after upgrading to v0.1.3 or later.

## v0.1.2 - Fixes & Animations
- **Chest protection:** Players can no longer break the chest; all players have a chance to get items.  
- **Chunk loading fix:** Airdrops spawned in unloaded chunks now load the chunk properly.  
- **Airdrop animation:** Airdrops spawn in the air with a drop animation (WIP).  
- **Enhanced cleanup:** Improved process for cleaning up airdrops after the timer ends.

## v0.1.1 - Config.yml Update
- **Config message fix:** A message was missing in `config.yml`.  
- You can either **regenerate `config.yml`** or manually **add the missing line** to the bottom of your config after updating the plugin.