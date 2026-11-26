# Blocks Client

A crystal PvP and base-hunting utility client for **Fabric**. This project builds the **Minecraft 26.3** version.
It's meant for singleplayer, private servers and anarchy servers that allow clients like this.
Settings live in `config/blocks`. If you used Summer Client before, its profiles and schematics are copied over automatically.

## Install

1. Install [Fabric Loader](https://fabricmc.net/use/) for Minecraft 26.3, plus the matching **Fabric API**.
2. Drop `blocks-client-1.0.0+26.3.jar` into `.minecraft/mods` (Java 25).
3. In game, press **Right Shift** to open the menu.

## The menu

**Right Shift** opens the menu. It comes in two designs (Preferences, **Menu Design**).

### Facet (default)

- **Hub:** a character showcase.
  - Your full character stands on a glowing glass pedestal block under a stage light. Body and head turn to face the cursor.
  - An isometric floor fades out around the pedestal, and light motes rise from it.
  - Your name plate floats above you.
  - Categories sit in a **dock** under the stage. Its cubes magnify as the cursor passes over them.
  - Everything stays centred, and the stage moves up if the dock would touch your HUD.
- **Module list:** no boxes. Each module is a soft row with a hexagon badge.
  - Click the **hexagon** to switch a module on or off; it lights up when on. Right-click a row does the same.
  - Click the **name** to open its settings. Middle-click binds a key.
- **Settings card:** a gem-cut glass panel, joined to its row by a glowing line with a bead flowing along it.
  - Switches and slider knobs are hexagons.
  - Mode selectors have a highlight that glides to your choice.
  - The keybind sits at the bottom.

### Classic

The earlier design: glass capsule rows, a settings card, and a petal hub with your head in a bubble.

### Both designs

- Search at the top, or just start typing.
- While the menu is open, drag any HUD element to move it.
- **Preferences:** theme (Amethyst, Diamond, Emerald, Redstone, Gold, Lapis, Netherite, Grass, Custom), menu design, hub on or off, panel opacity, font, GUI scale, effects, notifications and profiles.
- **Notifications:** one master switch, plus Toggle Alerts, Find Alerts and Sound.
- **Closing:** Esc closes the open card first, then the menu. Clicking empty space closes it too.

Every visual effect can be switched off.

## Modules

**Combat:** **Crystal Aura** (plays crystal PvP for you, see below), Auto Crystal (hold right click, Place/Break delay in ms), Auto Hit Crystal, Crystal Optimizer, Anchor Macro,
Safe Anchor, Double Anchor, Surround, Auto Inventory Totem, Hover Totem, Auto Double Hand, Totem Offhand, TriggerBot,
Aim Assist, Auto Mace, Mace Swap, **Totem Hit** (hit with your sword while holding a totem), Shield Disabler, Auto Jump Reset, Auto Pot.

**Visuals:** HUD (fps / ping / time bar, arraylist, now playing, speed graph, keybinds, coordinates, item counters,
**armor**, **potions**, target), Target HUD, ESP, Crystal Render, Target ESP, Hit Particles, Ambient Particles,
Chat (animated), Crosshair, Better Camera (F5), **Freecam**, Full Bright, **Nametags**, **Trails**, **Jump Circles**,
**Sun Hat**, **Block Highlight**, **Damage Numbers**, **Kill Effects**.

**Blatant PvP visuals (all off by default, each a single toggle):**
- **Blatant Pack:** turns the whole look on in one go, and turning it off puts everything back as it was.
- **Chams:** now **Glass** by default, so players show translucent and tinted.
- **Sun Hat:** gains the **China** style, and can be worn by You, You + Target, or Everyone.
- **Target ESP:** adds the **Orbit Arc**, a bright segmented arc sweeping around the target.
- **Trails:** can follow your target, or everyone.
- **Status Bars:** adds a **Sleek Hotbar**, with health and armour numbers above the bars.
- **Companion:** a little floating glass block with eyes by your shoulder.
- **Target ESP:** add the "Rune" style (a turning magic circle with a hexagram) and the Hitbox option.
- **Orbit Shards:** ice crystal shards circling your target.
- **Status Bars:** sleek health and hunger bars in place of the hearts.
- **Chams:** tints players a solid colour (ice blue, theme, rose or mint).
- **Aura Spikes:** a glowing crown of spikes around your target.
- **Hearts:** a Hit Particles style.
- **Boxed:** an Arraylist style.
- **Top Bar XYZ:** both live in the HUD settings.

**World (base hunting):** Storage ESP, Stash Finder, Sus Chunk Finder (grown kelp = player activity), Tunnel Finder,
Light Finder, Block ESP (block picker), Netherite Finder, **Auto Mine**, **Base Hunter**, **Auto Builder**.

**Utility:** Sprint, Fast Place, Key Pearl, XP Manager, Auto Tool, No Jump Delay, **Auto Reconnect**.

### Crystal Aura

**Off by default.**

- **Targeting:** picks the closest enemy in range. Set Targets to "All Living" to also fight mobs.
- **Placing:** scores every obsidian or bedrock spot in reach by the damage a crystal there would do to the target, minus the damage it would do to you. Damage is worked out like the server does it: distance, line of sight, difficulty, armour, Protection, Blast Protection and Resistance. It places on the best spot.
- **Breaking:** pops crystals the instant they appear. Place Delay and Break Delay are separate, in milliseconds.
- **Safety:** **Anti Suicide** and **Max Self Damage** keep you alive.
- **Face Place At:** drops the minimum damage when the target is low.
- **Support Obsidian:** puts down obsidian next to the target when there's nowhere to place.
- **Switch:** Silent swaps to crystals and straight back; Normal swaps; Off doesn't swap.
- **Other options:** Rotate, Pause While Eating, and Wall Range for placing through walls.
- **Visuals (each can be switched off):**
  - a glowing cyan glass box gliding to the next spot, with the predicted damage on it;
  - a white outline around the target;
  - sparkles when a crystal pops.

### Finders

- Chunks are scanned in the background on a small time budget, nearest first.
- Block ESP, Netherite Finder and Storage ESP draw **through walls**.
- A highlight disappears the moment its block is mined. Blocks placed or uncovered later show up straight away.
- **Anti-xray:** servers like Paper never send buried ores to the client until they're exposed. That's why debris can appear only when you're close, or when a bed blows the stone open. No client can see what the server never sends. Netherite Finder detects this and tells you, and shows exposed debris instantly.

### Base Hunter

1. Turn on Stash Finder and give Base Hunter a key.
2. When a stash shows up, look toward it and press the key. It locks onto that base; bigger stashes win ties.
3. Auto Mine tunnels there in a 1x2 tunnel with stairs. It plugs or goes around lava and water, bridges drops, and stops when you arrive.
4. Press the key again to stop.

### Auto Mine

- **Strip (default):** mines straight rows of a 2-high tunnel.
  - For each block: bottom block, then top block, then step forward.
  - At the end of a row it turns around and mines the next row back, until every row is done.
  - Set **Row Length**, **Rows**, **Row Spacing** (1 clears everything; 3 leaves strip-mining walls), which side the rows go, and the delay between steps.
  - It sneaks while walking, fills holes in the floor with cobble, and plugs fluids.
- **Other regions:** Layers (top-down box), Corners (look at a block and press Corner 1 / Corner 2), Radius, Mine To Y, Tunnel. Travel is used by Base Hunter.
- **Order:** layer by layer from the top, in a serpentine sweep, one block at a time. Vanilla's own break timing applies, so your tool, Efficiency and Haste all count.
- **Tools:** picks the fastest tool and swaps before one breaks (Save Tools At). If no tool can mine the block, it stops rather than chew through stone with a sword.
- **Fluids:** Plug (puts cobble into them), Skip or Stop. Bedrock is never mined. Obsidian, debris and ores can each be skipped.
- **Full inventory:** drops junk (cobble, dirt, netherrack and so on) or stops.
- **Movement:** walks into the cleared space as it goes. Pair it with Auto Reconnect to run it while you're away.

### Auto Builder

1. Put `.litematic`, `.schem` or `.nbt` files in `config/blocks/schematics`.
2. In the settings card, pick a file, then use Place here, Rotate and Start.

How it builds:
- **Modes:** Air Only, Replaceable, or Overwrite (mines wrong blocks first).
- **Order:** bottom-up and nearest-first. Blocks that need support wait for it.
- **Placement:** picks the face, look direction and hit point (upper or lower half) that make the block land exactly right. That covers stairs, top and bottom slabs, logs, observers and so on.
- **Recovery:** every placement is verified. A failure is retried once, then goes to a second pass that re-checks the world first. Nothing loops forever.
- **Materials:** come from the hotbar first, then the inventory. Missing ones are skipped and reported, and the rest still gets built.
- **Tall builds:** it scaffolds up under itself, then removes the scaffold at the end.

### Auto Reconnect

- Reconnects with backoff and jitter. A "Reconnecting in Ns - cancel" button appears on the disconnect screen.
- Won't reconnect when the kick reason contains one of your words. The default list is banned, x-ray, nuker and invalid move.
- Stops after 3 kicks right after joining (Kick Loop Guard).
- Picks Auto Mine or the build back up after rejoining.

## Build from source

Gradle (Loom 1.20) runs on JDK 25. The jar targets Java 25.

```bash
./gradlew build
```

The jar lands in `build/libs/blocks-client-1.0.0+26.3.jar`.

The in-game test creates a superflat world, checks the finders, Auto Crystal, anchors, Auto Mine and Auto Builder,
then saves screenshots to `build/run/clientGameTest/screenshots`:

```bash
xvfb-run -a ./gradlew runClientGameTest
```

## Layout

```
src/main/java/com/blocks/          modules, GUI (side panel, hub, menu), HUD, rendering, finders
src/main/java/com/blocks/compat/   the version-specific bits (drawing, screens, input, render types)
src/gametest/                      in-game test
```

Bundled fonts: Manrope (SIL Open Font License, `assets/blocks/font/OFL-Manrope.txt`) and
JetBrains Mono (Apache 2.0, `assets/blocks/font/LICENSE-JetBrainsMono.txt`).
