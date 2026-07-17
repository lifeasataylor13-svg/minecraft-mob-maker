# 🗿 Grass Golem — Files Cheat Sheet

Two folders: the **BRAIN** (how it acts) and the **LOOKS** (how it appears).

---

## 🧠 grass_golem_BP — the BRAIN

| File | What it's for | Edit today? |
|---|---|---|
| `entities/grass_golem.json` | Health, speed, size, powers, behavior | ✅ **YES — main file** |
| `loot_tables/entities/grass_golem.json` | What it drops when it dies | ✅ **YES — drops** |
| `manifest.json` | The pack's "ID card" | ❌ Don't touch |

## 🎨 grass_golem_RP — the LOOKS

| File | What it's for | Edit today? |
|---|---|---|
| `entity/grass_golem.json` | Connects model + texture + name + egg colors | ❌ Leave it |
| `models/entity/grass_golem.geo.json` | The 3D shape (from Blockbench) | ❌ Change in Blockbench |
| `textures/entity/grass_golem.png` | The paint job (from Blockbench) | ❌ Change in Blockbench |
| `texts/en_US.lang` | The name shown in-game | ✏️ Only to rename |
| `manifest.json` | The pack's "ID card" | ❌ Don't touch |

> **Today you really only touch 2 files** — both in the BRAIN folder.

---

## ⚡ Power-Ups (paste into `entities/grass_golem.json`)

All of these go **inside the `components` block**. Change one, reload, watch.

**Make it GIANT (or tiny):**
```json
"minecraft:scale": { "value": 2 }
```
*(try `0.5` for a baby golem)*

**Super speedy:**
```json
"minecraft:movement": { "value": 0.4 }
```

**Extra tough:**
```json
"minecraft:health": { "value": 100, "max": 100 }
```

**Rideable (Teddy can ride it):**
```json
"minecraft:rideable": {
  "seat_count": 1,
  "seats": [ { "position": [0, 1.5, 0] } ]
}
```

**Treasure drops** — in `loot_tables/entities/grass_golem.json`, swap the item name:
```
minecraft:sunflower   →   minecraft:diamond
```

---

## 🎮 In-game reminders

- Summon him: `/summon mymob:grass_golem`
- Turn on the mob: **Behavior Packs** → activate **Grass Golem Behavior**
- Remember to turn on **Cheats** in the world
- **Tip:** JSON is picky — every `{` needs a `}`, and items in a list are separated by commas.

---

*One power at a time. Have Teddy guess what it'll do before you reload — that's the fun part.*
