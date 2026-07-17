# 🧟 100 Things You Can Give a Mob

A menu of real Minecraft Bedrock **components** (power-ups). Almost all of these go inside the `components` block of the behavior file (`grass_golem_BP/entities/grass_golem.json`). Each one has its own settings — this list is for **ideas**; look up the exact setup when you pick one.

> 💡 Some powers need a partner. Example: `minecraft:attack` (how hard it hits) usually needs a `behavior` that tells it *who* to attack.

---

## 🩹 Body & Stats
1. `minecraft:health` — how many hearts it has
2. `minecraft:movement` — how fast it walks
3. `minecraft:scale` — makes it bigger or smaller
4. `minecraft:collision_box` — its invisible size (space it takes up)
5. `minecraft:physics` — gravity affects it (falls, bumps into things)
6. `minecraft:knockback_resistance` — how hard it is to knock back when hit
7. `minecraft:push_through` — how easily it slides through other mobs
8. `minecraft:pushable` — whether players/mobs can shove it
9. `minecraft:type_family` — labels it (like "monster" or "pet") so rules can find it
10. `minecraft:variant` — a number to make different-looking versions
11. `minecraft:mark_variant` — extra number for patterns/markings
12. `minecraft:color` — its dye color (like sheep wool)

## 🏃 Getting Around
13. `minecraft:navigation.walk` — finds paths on land
14. `minecraft:navigation.swim` — finds paths in water
15. `minecraft:navigation.fly` — finds paths in the air
16. `minecraft:navigation.climb` — can path up climbable blocks
17. `minecraft:navigation.float` — drifts/floats while pathing
18. `minecraft:navigation.generic` — all-purpose pathfinding
19. `minecraft:movement.basic` — normal walking
20. `minecraft:movement.fly` — flying movement
21. `minecraft:movement.amphibious` — moves on land AND in water
22. `minecraft:movement.hover` — hovers in the air
23. `minecraft:movement.skip` — hops like a rabbit or slime
24. `minecraft:can_climb` — can climb ladders
25. `minecraft:buoyant` — floats in liquids
26. `minecraft:jump.static` — gives it a set jump height
27. `minecraft:behavior.random_swim` — swims around randomly
28. `minecraft:behavior.swim_wander` — explores while swimming

## ⚔️ Fighting & Attacks
29. `minecraft:attack` — how much damage it deals
30. `minecraft:attack_cooldown` — wait time between attacks
31. `minecraft:behavior.melee_attack` — walks up and hits targets
32. `minecraft:behavior.ranged_attack` — shoots from a distance
33. `minecraft:shooter` — what projectile it fires
34. `minecraft:area_attack` — hurts everything close around it
35. `minecraft:behavior.nearest_attackable_target` — picks the closest enemy
36. `minecraft:behavior.hurt_by_target` — fights back whoever hit it
37. `minecraft:behavior.ram_attack` — charges and rams like a goat
38. `minecraft:behavior.charge_attack` — rushes at its target
39. `minecraft:behavior.swoop_attack` — dive-bombs from the air
40. `minecraft:behavior.roar` — a scary roar before attacking
41. `minecraft:behavior.sonic_boom` — the Warden's long-range blast
42. `minecraft:behavior.stomp_attack` — stomps its targets

## 🛡️ Defense & Toughness
43. `minecraft:fire_immune` — never burns
44. `minecraft:damage_sensor` — reacts to (or ignores) certain damage
45. `minecraft:hurt_on_condition` — takes damage in special spots (like lava)
46. `minecraft:combat_regeneration` — heals after fighting
47. `minecraft:cannot_be_attacked` — can't be hit at all
48. `minecraft:mob_effect_immunity` — immune to potion effects
49. `minecraft:burns_in_daylight` — catches fire in sunlight (zombie-style)
50. `minecraft:behavior.flee_sun` — runs to shade during the day
51. `minecraft:behavior.hide` — hides when scared
52. `minecraft:behavior.play_dead` — plays dead to avoid danger

## 🐾 Friendly, Pets & Taming
53. `minecraft:tameable` — can be tamed with items
54. `minecraft:tamemount` — tamed by riding it (like a horse)
55. `minecraft:is_tamed` — marks it as already tamed
56. `minecraft:rideable` — you can ride it
57. `minecraft:behavior.follow_owner` — follows its owner around
58. `minecraft:behavior.teleport_to_owner` — warps to its owner if far away
59. `minecraft:behavior.tempt` — follows a player holding a food it likes
60. `minecraft:trusting` — can learn to trust players (like an axolotl)
61. `minecraft:behavior.stay_while_sitting` — sits and stays put
62. `minecraft:leashable` — can be tied with a lead

## 🍼 Babies & Family
63. `minecraft:breedable` — two of them can make a baby
64. `minecraft:ageable` — grows from a baby into an adult
65. `minecraft:is_baby` — marks it as a baby
66. `minecraft:is_pregnant` — currently expecting a baby
67. `minecraft:behavior.lay_egg` — lays eggs
68. `minecraft:behavior.make_love` — looks for a mate
69. `minecraft:genetics` — passes traits to babies (like frogs or pandas)

## ✨ Fun Powers & Tricks
70. `minecraft:transformation` — turns into a different mob (zombie → drowned)
71. `minecraft:teleport` — warps around like an enderman
72. `minecraft:behavior.summon_entity` — summons other mobs to help
73. `minecraft:is_ignited` — lit up and about to explode (creeper)
74. `minecraft:explode` — blows up
75. `minecraft:spell_effects` — casts magic spells (evoker-style)
76. `minecraft:break_blocks` — can break certain blocks
77. `minecraft:grows_crop` — makes nearby crops grow (bee-style)
78. `minecraft:boostable` — speeds up with a boost item (pig + carrot on a stick)
79. `minecraft:is_shaking` — does a shaking animation
80. `minecraft:is_dyeable` — you can color it with dye
81. `minecraft:flocking` — moves in a group/school with others
82. `minecraft:vibration_listener` — senses vibrations (Warden-style)
83. `minecraft:entity_sensor` — reacts when other mobs come near

## 🎒 Items, Trading & Talking
84. `minecraft:interact` — does something when you use/tap it
85. `minecraft:inventory` — gives it storage slots
86. `minecraft:is_chested` — can wear a chest to carry items
87. `minecraft:equippable` — can wear armor or a saddle
88. `minecraft:equip_item` — auto-equips items it picks up
89. `minecraft:trade_table` — lets it trade with players (villager-style)
90. `minecraft:economy_trade_table` — villager-style economy trading
91. `minecraft:loot` — what items it drops when it dies
92. `minecraft:experience_reward` — how much XP it gives when killed
93. `minecraft:nameable` — can be named with a name tag
94. `minecraft:item_hopper` — sucks up nearby items (like an allay)

## 🧠 Brain Goals (behaviors)
95. `minecraft:behavior.random_stroll` — wanders around randomly
96. `minecraft:behavior.look_at_player` — turns to look at nearby players
97. `minecraft:behavior.float` — bobs at the surface so it won't drown
98. `minecraft:behavior.panic` — runs around scared when hurt
99. `minecraft:behavior.random_look_around` — glances around naturally
100. `minecraft:behavior.sleep` — sleeps at night (villager-style)

---

### 📌 How to use this
- Pick a power, then look up its exact settings in the official docs (each one has its own options).
- Add it inside the `components` block, reload, and watch what happens.
- Not every combo works together — experiment! Breaking things and fixing them is how you learn.

**Where to find exact setups:**
- Microsoft's component list: https://learn.microsoft.com/en-us/minecraft/creator/reference/content/entityreference/examples/componentlist
- Bedrock Wiki (friendlier): https://wiki.bedrock.dev/
