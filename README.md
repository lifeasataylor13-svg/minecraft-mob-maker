# minecraft-mob-maker

A kid-friendly project for building your own custom **Mob** (creature) for **Minecraft Bedrock Edition** and playing it on a **Nintendo Switch 2**.

This repo contains a working custom mob — the **Grass Golem** — plus a step-by-step guide written for a 10-year-old (with a grown-up helping).

## What's in here

| File / folder | What it is |
|---|---|
| `Make-Your-Own-Minecraft-Mob-Switch2-Guide.md` | The full step-by-step guide. **Start here.** (Uses a "Glow Slug" as its teaching example — same steps apply to the Grass Golem.) |
| `grass_golem_BP/` | Behavior Pack — the mob's "brain" (health, speed, behavior, drops) |
| `grass_golem_RP/` | Resource Pack — the mob's "looks" (model, texture, name) |

```
grass_golem_BP/
├── manifest.json
├── entities/grass_golem.json
└── loot_tables/entities/grass_golem.json

grass_golem_RP/
├── manifest.json
├── entity/grass_golem.json
├── texts/en_US.lang
├── models/entity/        ← add your Blockbench model (grass_golem.geo.json)
└── textures/entity/      ← add your painted texture (grass_golem.png)
```

## Grass Golem stats (in `grass_golem_BP/entities/grass_golem.json`)

- **Health:** 30 (tough, like a golem should be)
- **Speed:** 0.18 (slow and heavy)
- **Behavior:** wanders around, looks at players, friendly
- **Drops:** wheat seeds
- **Identifier:** `mymob:grass_golem` (this is how you summon it)

## The two things you still add yourself

The code is done. To finish the mob you make two files in [Blockbench](https://www.blockbench.net/) (free):

1. **The 3D model** → save as `grass_golem.geo.json` in `grass_golem_RP/models/entity/`
   (its identifier inside must be `geometry.grass_golem`)
2. **The texture (paint)** → save as `grass_golem.png` in `grass_golem_RP/textures/entity/`

## How to play it (the short version)

You build and test on a **PC, phone, or tablet** — the Switch can't import add-on files directly. To get it onto the **Switch 2**, you put the mob in a world and upload that world to a **Realm**, then join the Realm from the Switch. Full instructions are in the guide.

## Quick test (on PC/phone/tablet)

1. Zip `grass_golem_BP` + `grass_golem_RP` together, rename the zip to `.mcaddon`, open it in Minecraft.
2. Make a world, turn on both packs and cheats.
3. In chat, type: `/summon mymob:grass_golem`

Happy mob making! 🌱🗿
