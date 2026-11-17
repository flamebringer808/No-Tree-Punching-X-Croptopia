# No Tree Punching X Croptopia

Compatibility fix for **No Tree Punching (`notreepunching`)** and **Croptopia** (plus vanilla plants/saplings) on **Minecraft 1.20.1**, available as a **Fabric mod**, **Forge mod**, and standalone **Datapack**.

## Fixes Included

### 1. Croptopia Crops & Tree Saplings
- Fixes left-click breaking drops for all **58 Croptopia farmland crops** (`CroptopiaCropBlock` and `TallCropBlock`), which previously yielded zero drops when **No Tree Punching** was installed.
- Fixes left-click breaking drops for all **27 Croptopia tree saplings** (`CroptopiaSaplingBlock`, including `grapefruit_sapling`), which were previously blocked by `#minecraft:mineable/axe` / `#minecraft:sword_efficient`.
- Preserves age-dependent loot (`age < 7` drops nothing, `age == 7` drops normal crop loot), Fortune bonuses, Croptopia right-click harvesting, and tree leaf crop rules (`LeafCropBlock` + shears/bare hand).
- Leaves Croptopia logs (`cinnamon_log`, `cinnamon_wood`, `stripped_*`) and ores (`salt_ore`) governed by No Tree Punching rules.

### 2. Vanilla Saplings, Flowers, Sugar Cane, Crops & Farm-Like Plants
In Minecraft `1.20.1`, vanilla placed saplings, crops, flowers, and soft plants into `#minecraft:sword_efficient` / `#minecraft:mineable/*`, which **No Tree Punching** (`7.1.0`) includes inside `#notreepunching:mineable` while `#notreepunching:always_drops` and `#notreepunching:always_breakable` omit them. Because NTP defaults `doInstantBreakBlocksDropWithoutCorrectTool = false`, breaking these blocks yielded zero drops (and hardness `> 0` plants like melons, pumpkins, cocoa, chorus flowers, moss carpet, big dripleaf, and vines had zero break speed without tools).

**No Tree Punching X Croptopia** restores proper vanilla harvestability and break speed for:
- **Saplings**: All **10** vanilla `#minecraft:saplings` (`oak_sapling`, `spruce_sapling`, `birch_sapling`, `jungle_sapling`, `acacia_sapling`, `dark_oak_sapling`, `cherry_sapling`, `mangrove_propagule`, `azalea`, `flowering_azalea`).
- **Flowers**: All `#minecraft:small_flowers` (including `torchflower`), all `#minecraft:tall_flowers` (`sunflower`, `lilac`, `rose_bush`, `peony`), `pitcher_plant`, `pink_petals`, and `spore_blossom`.
- **Sugar Cane & Crops**: `sugar_cane`, `wheat`, `carrots`, `potatoes`, `beetroots`, `torchflower_crop`, `pitcher_crop`, `melon_stem`, `pumpkin_stem`, `attached_melon_stem`, `attached_pumpkin_stem`, `nether_wart`, `cocoa`, `sweet_berry_bush`, `cave_vines`, `cave_vines_plant`, `melon`, `pumpkin`, `chorus_flower`, `chorus_plant`.
- **Mushrooms, Fungi, Scaffolding & Aquatic Farmables**: `brown_mushroom`, `red_mushroom`, `crimson_fungus`, `warped_fungus`, `lily_pad`, `big_dripleaf`, `big_dripleaf_stem`, `bamboo_sapling`, `scaffolding`.
- **Soft Foliage & NTP Knife / Shears Plants**: `grass`, `tall_grass`, `fern`, `large_fern`, `dead_bush`, `moss_carpet`, `small_dripleaf`, `vine`, `weeping_vines`, `twisting_vines`, `glow_lichen`, `hanging_roots`, `warped_roots`, `crimson_roots`, `nether_sprouts` (preserving vanilla/NTP tool loot tables—e.g. NTP Flint Knife drops `plant_fiber` from tall grass/ferns and shears harvest vines/glow lichen/leaves).

## Preserved Behavior
- Logs, planks, stone, ores, rails, crafted blocks, `bamboo`, `carved_pumpkin`, and `jack_o_lantern` remain restricted by No Tree Punching.
- Unrelated third-party mods' crops are left untouched for dedicated compatibility updates.
- Safe no-op if **No Tree Punching** or **Croptopia** is not installed.

## Downloads & Building

```bash
# Build Fabric JAR + Standalone Datapack ZIP
./gradlew build

# Build Forge JAR
cd forge && ../gradlew build
```

All release outputs are written to `build/libs/`:
- **Fabric Mod (`1.20.1`)**: `build/libs/no_tree_punching_x_croptopia-1.0.0-1.20.1-fabric.jar`
- **Forge Mod (`1.20.1`)**: `build/libs/no_tree_punching_x_croptopia-1.0.0-1.20.1-forge.jar`
- **Datapack (`1.20.1` Fabric & Forge)**: `build/libs/no_tree_punching_x_croptopia-1.0.0-1.20.1-datapack.zip`
