# minecraft-mob-maker

A kid-friendly project for building your own custom **Mob** (creature) for **Minecraft Bedrock Edition** and playing it on a **Nintendo Switch 2**.

This repo contains a full, working starter mob — the **Glow Slug** — plus a step-by-step guide written for a 10-year-old (with a grown-up helping).

## What's in here

| File / folder | What it is |
|---|---|
| `Make-Your-Own-Minecraft-Mob-Switch2-Guide.md` | The full step-by-step guide. **Start here.** |
| `glow_slug_BP/` | Behavior Pack — the mob's "brain" (health, speed, behavior, drops) |
| `glow_slug_RP/` | Resource Pack — the mob's "looks" (model, texture, name) |

```
glow_slug_BP/
├── manifest.json
├── entities/glow_slug.json
└── loot_tables/entities/glow_slug.json

glow_slug_RP/
├── manifest.json
├── entity/glow_slug.json
├── texts/en_US.lang
├── models/entity/        ← add your Blockbench model (glow_slug.geo.json)
└── textures/entity/      ← add your painted texture (glow_slug.png)
```

## The two things you still add yourself

The code is done. To finish the mob you make two files in [Blockbench](https://www.blockbench.net/) (free):

1. **The 3D model** → save as `glow_slug.geo.json` in `glow_slug_RP/models/entity/`
2. **The texture (paint)** → save as `glow_slug.png` in `glow_slug_RP/textures/entity/`

The guide walks through both.

## How to play it (the short version)

You build and test on a **PC, phone, or tablet** — the Switch can't import add-on files directly. To get it onto the **Switch 2**, you put the mob in a world and upload that world to a **Realm**, then join the Realm from the Switch. Full instructions are in the guide.

## Quick test (on PC/phone/tablet)

1. Zip `glow_slug_BP` + `glow_slug_RP` together, rename the zip to `.mcaddon`, open it in Minecraft.
2. Make a world, turn on both packs and cheats.
3. In chat, type: `/summon mymob:glow_slug`

Happy mob making! 🟢🐌
