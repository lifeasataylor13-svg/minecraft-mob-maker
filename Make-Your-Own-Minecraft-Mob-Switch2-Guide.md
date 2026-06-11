# Make Your Own Minecraft Mob (and Play It on Switch 2)

*A step-by-step project for a kid (about 10) and a grown-up to do together.*

---

## Read This First: The Switch 2 Reality Check

Here's the most important thing to know before we start, because almost every other guide skips it.

A custom mob is a little **add-on** — a bundle of files you build. On a **PC, phone, or tablet**, you can import those files straight into Minecraft. But the **Nintendo Switch (including Switch 2) will NOT let you import add-on files directly.** The Switch keeps its files locked away, so there is no "open my .mcaddon file" button. Only two kinds of custom content work on Switch:

1. **Minecraft Marketplace** stuff (the official store inside the game), and
2. **Realms** — Minecraft's paid online worlds.

So here's the plan we'll use, and it really does work:

> **Build the mob on a PC, phone, or tablet → put the mob into a world → upload that world to a Realm → join the Realm from the Switch 2.** When you join a Realm that has an add-on, the Switch downloads the mob automatically.

**Grown-up note:** This means you need (a) a Windows PC, Android/iPhone, or iPad/tablet to *build* on, and (b) a **Minecraft Realms subscription** (about $4–8/month, free trial usually available) so the Switch can join. There is no safe, supported way to sideload custom files onto a Switch — please don't follow YouTube videos that tell you to hack the console. The Realms path is the official, safe one.

If that sounds like a lot — it's really just "build on the computer, play on the Switch." Let's go.

---

## Part 1 — What Even *Is* a Mob? (The Big Picture)

A **mob** is any living creature in Minecraft — a cow, a zombie, a bee. When you make your own, you're really making two little gift boxes of files:

- **Behavior Pack** = the creature's **brain and body rules.** How much health it has, how fast it walks, whether it's friendly or mean, what it drops when it dies.
- **Resource Pack** = the creature's **looks and sounds.** Its 3D shape (the *model*), its paint job (the *texture*), how it moves (the *animations*), and its name.

> **Think of it like a puppet:** the Behavior Pack is the puppeteer pulling the strings (what it *does*), and the Resource Pack is the puppet itself — the cloth, the paint, the voice (what it *looks and sounds* like).

Minecraft reads both boxes and — boom — a new creature appears in your world.

---

## Part 2 — Tools You'll Need (All Free Except the Realm)

You'll do the building on a **PC, phone, or tablet** — not the Switch. Here's the kit:

| Tool | What it's for | Cost |
|---|---|---|
| **Minecraft Bedrock** on a PC/phone/tablet | To test the mob before it goes to Switch | You likely own it |
| **A text editor** — [Visual Studio Code](https://code.visualstudio.com/) is free and great | To write the "rules" files (they're just text) | Free |
| **Blockbench** — [blockbench.net](https://www.blockbench.net/) | To build the 3D model, paint the texture, and animate | Free |
| **Minecraft Realms** | So the Switch 2 can join and see your mob | Paid (subscription) |

**Grown-up note:** Blockbench runs in a web browser too (no install needed) at blockbench.net — handy on a school laptop. Visual Studio Code is a free Microsoft program; install it on the building computer.

> **Try this (5 min):** Before building anything, open Blockbench and click around. Make a cube. Spin it. Get comfortable — it's like digital LEGO.

---

## Part 3 — Plan Your Mob (Do This With the Kid!)

Don't touch the computer yet. Grab paper and decide together. This is the funnest part and it makes everything else easier.

- **Name:** What's it called? (Example: *Glow Slug*)
- **Look:** What shape and colors? Draw it!
- **Health:** How tough? (A chicken has 4, a player has 20, an iron golem has 100.)
- **Personality:** Friendly like a cow? Scared like a rabbit? Mean like a zombie?
- **Speed:** Slow and shuffly, or zippy?
- **Drops:** What do you get when it dies? (Example: glow ink)
- **Sound:** Squeaky? Growly? Silent?

Write all of this down. We'll plug these exact answers into the files.

> **For the rest of this guide, we'll build an example mob called the *Glow Slug*** — a slow, friendly, glowing green creature with 10 health that drops slime balls. Swap in your own choices as you go.

---

## Part 4 — Build the Mob, Step by Step

We'll make a folder on your computer, drop the right files inside, and Minecraft will read them.

### Step 4.1 — Make the folders

Create a folder anywhere (like your Desktop) called `glow_slug`. Inside it, make **two** folders:

```
glow_slug/
├── glow_slug_BP/      ← Behavior Pack (the brain)
└── glow_slug_RP/      ← Resource Pack (the looks)
```

### Step 4.2 — Give each pack an ID card (the manifest)

Every pack needs a `manifest.json` — its **ID card** so Minecraft knows what it is. You need a **UUID**, which is just a random ID code. Get two free ones at [uuidgenerator.net](https://www.uuidgenerator.net/) (you need 4 total — 2 per pack).

Put this in `glow_slug_BP/manifest.json`:

```json
{
  "format_version": 2,
  "header": {
    "name": "Glow Slug Behavior",
    "description": "The brain of the Glow Slug",
    "uuid": "PUT-A-RANDOM-UUID-HERE",
    "version": [1, 0, 0],
    "min_engine_version": [1, 21, 0]
  },
  "modules": [
    {
      "type": "data",
      "uuid": "PUT-A-DIFFERENT-UUID-HERE",
      "version": [1, 0, 0]
    }
  ]
}
```

Put this in `glow_slug_RP/manifest.json` (note `"resources"` instead of `"data"`):

```json
{
  "format_version": 2,
  "header": {
    "name": "Glow Slug Looks",
    "description": "The looks of the Glow Slug",
    "uuid": "PUT-A-THIRD-RANDOM-UUID-HERE",
    "version": [1, 0, 0],
    "min_engine_version": [1, 21, 0]
  },
  "modules": [
    {
      "type": "resources",
      "uuid": "PUT-A-FOURTH-RANDOM-UUID-HERE",
      "version": [1, 0, 0]
    }
  ]
}
```

> **Grown-up note:** All four UUIDs must be different. If two are the same, Minecraft gets confused and the pack won't load. Just generate four and paste one into each slot.

### Step 4.3 — The mob's BRAIN (behavior file)

Inside `glow_slug_BP`, make a folder called `entities`, and inside that a file called `glow_slug.json`:

```
glow_slug_BP/entities/glow_slug.json
```

Paste this in:

```json
{
  "format_version": "1.21.0",
  "minecraft:entity": {
    "description": {
      "identifier": "mymob:glow_slug",
      "is_spawnable": true,
      "is_summonable": true
    },
    "components": {
      "minecraft:health": { "value": 10, "max": 10 },
      "minecraft:movement": { "value": 0.15 },
      "minecraft:movement.basic": {},
      "minecraft:navigation.walk": { "can_walk": true },
      "minecraft:physics": {},
      "minecraft:jump.static": {},
      "minecraft:collision_box": { "width": 0.8, "height": 0.6 },
      "minecraft:behavior.random_stroll": { "priority": 1, "speed_multiplier": 1.0 },
      "minecraft:behavior.look_at_player": { "priority": 2, "look_distance": 6 },
      "minecraft:loot": { "table": "loot_tables/entities/glow_slug.json" }
    }
  }
}
```

**What the kid is reading here** (point at each line!):

- `identifier` — the mob's secret code name. `mymob:glow_slug`. We'll use this to summon it.
- `health` — 10 hearts of toughness. Change the number for a tougher or weaker mob.
- `movement` `0.15` — walking speed. Bigger = faster. (A cow is about 0.25.)
- `random_stroll` — makes it wander around like a cow.
- `look_at_player` — makes it turn and look at you. Cute!
- `loot` — what it drops (we set that up next).

### Step 4.4 — What it drops (loot table)

Make `glow_slug_BP/loot_tables/entities/glow_slug.json`:

```json
{
  "pools": [
    {
      "rolls": 1,
      "entries": [
        { "type": "item", "name": "minecraft:slime_ball", "weight": 1 }
      ]
    }
  ]
}
```

Now it drops a slime ball when it dies. Want it to drop something else? Change `minecraft:slime_ball` to another item like `minecraft:emerald`.

### Step 4.5 — The mob's LOOKS (client entity file)

Now over in the Resource Pack. Make `glow_slug_RP/entity/glow_slug.json`:

```json
{
  "format_version": "1.10.0",
  "minecraft:client_entity": {
    "description": {
      "identifier": "mymob:glow_slug",
      "materials": { "default": "slime" },
      "textures": { "default": "textures/entity/glow_slug" },
      "geometry": { "default": "geometry.glow_slug" },
      "render_controllers": [ "controller.render.default" ],
      "spawn_egg": { "base_color": "#33ff66", "overlay_color": "#116622" }
    }
  }
}
```

This file is the **connector** — it tells Minecraft which model, which texture, and which spawn egg colors go with the mob. The `identifier` must match the brain file **exactly** (`mymob:glow_slug`).

### Step 4.6 — The 3D model and texture (Blockbench)

This is where Blockbench shines and the kid gets to be an artist.

1. Open **Blockbench** → **New** → choose **Bedrock Model**.
2. When it asks for the model name/identifier, type `glow_slug`.
3. Build the body out of cubes (start with one big box for a slug!).
4. Click **Paint** and color the texture however you like.
5. **File → Export → Export Bedrock Geometry** → save it as `glow_slug.geo.json` into `glow_slug_RP/models/entity/`.
6. **File → Export → Export Texture** (or save the texture PNG) as `glow_slug.png` into `glow_slug_RP/textures/entity/`.

> **Try this:** Give your slug glowing eyes by painting two bright dots. Little details make it feel *alive*.

Your folders should now look like this:

```
glow_slug/
├── glow_slug_BP/
│   ├── manifest.json
│   ├── entities/glow_slug.json
│   └── loot_tables/entities/glow_slug.json
└── glow_slug_RP/
    ├── manifest.json
    ├── entity/glow_slug.json
    ├── models/entity/glow_slug.geo.json
    └── textures/entity/glow_slug.png
```

### Step 4.7 — (Optional) Give it a name tag and sounds

To make the name show up nicely, add `glow_slug_RP/texts/en_US.lang`:

```
entity.mymob:glow_slug.name=Glow Slug
```

Sounds are a bigger topic — feel free to skip them for your first mob and add them later as a "next step."

---

## Part 5 — Test It on Your PC/Phone/Tablet FIRST

Always test where it's easy *before* sending it to the Switch.

### Step 5.1 — Package it
Select both `glow_slug_BP` and `glow_slug_RP` folders, zip them together, and rename the zip's ending from `.zip` to **`.mcaddon`**. Double-click it — Minecraft opens and imports both packs automatically.

*(On phone/tablet, save the folders, zip them, rename to `.mcaddon`, and tap it to open in Minecraft.)*

### Step 5.2 — Turn it on in a world
1. Create a new world (or edit one).
2. In **Behavior Packs**, activate **Glow Slug Behavior**. Minecraft usually auto-adds the matching Resource Pack — if not, activate **Glow Slug Looks** too.
3. Turn on **cheats** so you can summon it.

### Step 5.3 — Summon it!
Enter the world, open chat, and type:

```
/summon mymob:glow_slug
```

Your mob should pop into existence. 🎉 Use the spawn egg from the Creative inventory too.

---

## Part 6 — Get It Onto the Switch 2 (The Realms Path)

Once the mob works on your PC/phone/tablet, here's how the Switch player gets to meet it.

1. **On the building device,** make sure your test world has the Glow Slug packs active and is saved.
2. **Upload that world to a Realm:** open the world's settings → choose to upload/replace it on your Realm. (You need a Realms subscription — start a free trial if you don't have one.) The add-on goes up *with* the world.
3. **On the Switch 2,** sign in with the **same Microsoft account** (or be invited to the Realm by that account).
4. Open **Play → Realms**, join the Realm, and step into the world.
5. The Switch downloads the add-on automatically, and your **Glow Slug is there** — playable on the Switch 2. 🎮

> **Grown-up note:** The Switch player and the building device must be linked by the same Microsoft account or a Realm invite. The custom mob lives *inside the Realm world* — Switch players can't install it on their own, they just join and play.

---

## Part 7 — Troubleshooting (When Things Go Wrong)

Things *will* go wrong — that's normal and part of coding! Here's the fix-it table:

| Problem | Likely cause | Fix |
|---|---|---|
| Pack won't show up in Minecraft | Two UUIDs are the same, or a typo in `manifest.json` | Generate fresh UUIDs; check every `{ }` and `,` |
| `/summon` says "unknown entity" | `identifier` doesn't match | Make sure brain + looks files both say `mymob:glow_slug` exactly |
| Mob spawns but is invisible | Texture or model path is wrong | Check the file names and folders match the looks file |
| Mob is a giant pink-and-black cube | Texture missing or wrong name | Confirm `glow_slug.png` is in `textures/entity/` |
| Mob won't move | Missing movement/navigation components | Keep `minecraft:movement` AND `minecraft:navigation.walk` |
| Changes don't appear | Old pack still loaded | Remove the pack, re-import the `.mcaddon`, restart Minecraft |

> **Pro tip for kids:** Change **one thing at a time**, then test. If it breaks, you know exactly what caused it.

---

## Part 8 — Final Checklist

- [ ] Two folders: `_BP` (brain) and `_RP` (looks)
- [ ] A `manifest.json` in each, with **4 different UUIDs**
- [ ] Brain file in `entities/` with your health, speed, behavior
- [ ] Loot table for what it drops
- [ ] Looks file in `entity/` connecting model + texture
- [ ] Model (`.geo.json`) and texture (`.png`) from Blockbench
- [ ] Tested with `/summon mymob:glow_slug` on PC/phone/tablet
- [ ] World uploaded to a **Realm**
- [ ] Joined the Realm from the **Switch 2** and saw the mob

---

## Part 9 — Fun Next Steps (Keep Going!)

Once the basic mob works, try leveling up — one new thing at a time:

- Make it **tameable** like a wolf (add `minecraft:tameable`).
- Make it **hostile** so it chases players (add `minecraft:behavior.nearest_attackable_target` + `minecraft:attack`).
- Make it **breed** and have babies.
- Add **custom sounds**.
- Add **glowing** so it lights up in the dark.
- Make it **ride-able**!

Each one is a small new component — perfect bite-sized challenges.

---

## A Note on Versions (Important for Accuracy)

Minecraft updates a lot, and in 2026 it switched to a year-based version number (2026 versions start with **"26"**). The **`format_version`** numbers inside the files (like `1.21.0`) are separate from the game's version and each file type uses its own. The versions in this guide are good starting points, but if a pack ever refuses to load after a Minecraft update, check the **current numbers** in Mojang's official up-to-date example pack:

- **Official sample packs:** [aka.ms/behaviorpacktemplate](https://aka.ms/behaviorpacktemplate)
- **Microsoft's official creator docs:** [learn.microsoft.com/minecraft/creator](https://learn.microsoft.com/en-us/minecraft/creator/documents/entitybehaviorintroduction)
- **Community wiki (kid-friendly tutorials):** [wiki.bedrock.dev](https://wiki.bedrock.dev/guide/custom-entity)

When something doesn't work, copy the `format_version` and `min_engine_version` from the official sample pack into your files — that almost always fixes version problems.

---

*You did it! You're now a Minecraft creature creator. Have fun, and remember: every cool mob started as a single cube.*
