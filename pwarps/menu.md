# Menu

The Menu size must remain at 9, 18, 27, 36, 45, or 54.&#x20;

You can use any command you'd like to be executed

If you use "-close" as the player's command, it will close their inventory



Example config ran on carbonmc.net:&#x20;

```
menu:
  title: '&8Select a location...'
  # Valid sizes: 9, 18, 27, 36, 45, 54
  size: 9
warps:
  furniture:
    slot: 0
    # Item names: https://www.digminecraft.com/lists/index.php
    material: ARMOR_STAND
    display_name: '&aFurniture Showcase'
    lore:
    - '&8Warp Location'
    - ''
    - '&eClick to teleport to &aFurniture Showcase&e!'
    command: warp <name>
  afk:
    slot: 1
    material: CHEST
    display_name: '&aAFK Area'
    lore:
    - '&8Warp Location'
    - ''
    - '&eClick to teleport to &aAFK Area&e!'
    command: warp <name>
  pvp:
    slot: 2
    material: DIAMOND_SWORD
    display_name: '&aPvP Arena'
    lore:
    - '&8Warp Location'
    - ''
    - '&eClick to teleport to &aPvP Arena&e!'
    command: warp <name>
  spawn:
    slot: 3
    material: RED_BED
    display_name: '&aSpawn'
    lore:
    - '&8Warp Location'
    - ''
    - '&eClick to teleport to &aSpawn&e!'
    command: warp <name>
  crates:
    slot: 4
    material: ENDER_CHEST
    display_name: '&aCrates'
    lore:
    - '&8Warp Location'
    - ''
    - '&eClick to teleport to &aCrates&e!'
    command: warp <name>
  parkour:
    slot: 5
    material: RABBIT_FOOT
    display_name: '&aParkour'
    lore:
    - '&8Warp Location'
    - ''
    - '&eClick to teleport to &aParkour&e!'
    command: warp <name>
  rtp:
    slot: 7
    material: GREEN_WOOL
    display_name: '&aRandom Teleport'
    lore:
    - '&8Random Teleport'
    - ''
    - '&eClick to &aRandom Teleport&e!'
    command: rtp
  close:
    slot: 8
    material: BARRIER
    display_name: '&cClose'
    lore:
    - '&cClick to close the menu'
    command: -close
```
