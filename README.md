# Defend Your Dome

A solarpunk tower-defense battle: your living glass dome and its giant solar
cannon against the enemy's smog rig across the meadow. Browser-first,
mobile later.

## Play the prototype

Open `index.html` in any browser — no build step, no dependencies. For mobile
testing on your LAN: `python3 -m http.server` and visit `http://<your-ip>:8000`.

## Core loop (implemented)

- **Sunlight (gold)** accrues over time; kills pay bounties.
- **Troops:** Warden (cheap melee), Thornshot (ranged), Oakguard (slow tank).
  Friendly troops pass freely through each other, so melee can move ahead of
  archers. Enemy AI spawns waves that speed up over time.
- **Base economy:** three "Harvest" upgrades raise income.
- **Solar Cannon:** build it first (reaches only mid-field — shreds troops but
  can't touch the enemy base). Then exactly 3 upgrades: the **first must be
  Range**; the second and third are your choice of Range or Damage. Max range
  reaches the enemy base. The basic shell is single-target until a Damage
  upgrade gives it splash.
- **Cannon abilities (tap-to-fire, on cooldown, unlocked once the cannon is
  built):** 🌿 **Vine** roots enemies and thorns them over time · 💥 **Bomb**
  big splash damage · 🕳 **Void** a black hole that drags enemies back toward
  their base.
- **Enemy cannon:** the toxic rig fires back at your advancing troops, but at
  this difficulty it can't reach your dome (a `DIFFICULTY` flag unlocks that for
  future levels).
- **Win** by destroying the toxic rig; lose if your dome falls.

## Aesthetic

Solarpunk, golden hour, bright and dramatic. Troops are dark silhouettes with
glowing accents (a nod to the old Flash game *Stickman Defense*). Everything is
drawn in code on a single canvas — no image assets yet.

## Roadmap

1. **Tune the draft** — balance, multiple levels/waves, more unit types,
   sound, hit-feedback juice.
2. **Structure & mobile** — either stay vanilla canvas or move to Phaser 3;
   real art pass; PWA wrapper first, Capacitor for app stores later.
3. **Business model (parked for now)** — the savings-as-microtransactions
   idea: purchases move the player's own money from checking to their
   savings/investments via a banking-as-a-service partner (precedent: Blast,
   by the Acorns co-founder; prize-linked savings are legal under the
   American Savings Promotion Act of 2014). Requires a bank/broker partner —
   revisit after the game is fun.
