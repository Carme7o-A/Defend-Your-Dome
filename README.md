# Defend Your Dome

A solarpunk tower-defense battle: your garden city's glass dome and its giant
solar cannon against Synergy Plaza — a gray corporate box with no imagination —
across the meadow. Browser-first, mobile later.

**▶ Play the live demo:** https://carme7o-a.github.io/Defend-Your-Dome/

## Play locally

Open `index.html` in any browser — no build step, no dependencies. For mobile
testing on your LAN: `python3 -m http.server` and visit `http://<your-ip>:8000`.

## Core loop (implemented)

- **Sunlight (gold)** accrues over time; kills pay bounties. Three "Harvest"
  upgrades raise income.
- **Troops:** Warden (cheap melee), Thornshot (ranged), Oakguard (slow tank).
  Friendly troops pass freely through each other, so melee can move ahead of
  archers. Enemy waves speed up and lean into tanks as the match drags on.
- **Solar Cannon:** build it first (reaches only mid-field — shreds troops but
  can't touch the enemy base). Then exactly 3 upgrades: the **first must be
  Range**; the second and third are your choice of Range or Damage. Max range
  reaches the enemy base. The basic shell is single-target until a Damage
  upgrade gives it splash.
- **Cannon ammo (unlock with sunlight, then tap-to-fire on a cooldown):**
  - 🌿 **Vine** (☀150) plants a trap that lingers **10 seconds** — anyone who
    walks in gets rooted and thorned over time.
  - 💥 **Bomb** (☀250) huge splash damage.
  - 🕳 **Void** (☀200) a black hole dropped behind the pack that drags enemies
    back toward their own base.
- **Enemy cannon:** Synergy Plaza's roof gun shells your advancing troops, but
  at this difficulty it can't reach your dome (a `DIFFICULTY` flag unlocks that
  for future levels).
- **Win** by demolishing Synergy Plaza; lose if your dome falls.

## Aesthetic

Solarpunk garden-city vs. boring capitalist architecture. Bright blue sky,
cargo blimps, patchwork crop strips, wind turbines, a distant white eco-city;
your base is a tiered white terrace tower under a geodesic glass dome (gun
poking out the top). The enemy is a beige-podium office slab with an identical
window grid, rooftop HVAC, and a sad regulation shrub. Troops are dark
silhouettes with glowing accents (a nod to the old Flash game *Stickman
Defense*). Everything is drawn in code on a single canvas — no image assets.

## Roadmap

1. **Playtest round** — collect feedback from friends on pacing and clarity;
   keep tuning balance, add sound and hit-feedback juice.
2. **Structure & mobile** — either stay vanilla canvas or move to Phaser 3;
   deeper ability upgrade trees (thornier vines, bigger bombs); PWA wrapper
   first, Capacitor for app stores later.
3. **Business model (parked for now)** — the savings-as-microtransactions
   idea: purchases move the player's own money from checking to their
   savings/investments via a banking-as-a-service partner (precedent: Blast,
   by the Acorns co-founder; prize-linked savings are legal under the
   American Savings Promotion Act of 2014). Requires a bank/broker partner —
   revisit after the game is fun.
