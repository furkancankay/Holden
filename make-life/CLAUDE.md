# Make Life (student game)

Single-file Three.js (r128, CDN) game: `index.html`. No build step; open in a browser.
Keys: 1-7 game speed (1x-60x; above 15x each step is bigger), M mute. Nothing after the tribal era has been play-tested in a browser; only syntax-checked.

## Story flow (STAGES array, fired in order in updateLandLife)
star -> planet -> life -> land animals -> early humans (primitive AI) -> first idea -> cave -> spears
-> villages (huts with interiors) -> tribal era (hunting) -> over-hunting/extinction, vultures eat bones
-> pens and breeding, animals bounce back -> paths, population growth -> bronze ore, Bronze Age
-> pyramid built by enslaved poor/weak -> monuments -> castle (royal guards, king on throne)
-> crowd watches king place the capstone -> workers freed -> Bronze Age cities
-> rich take servants -> king bans slavery (gallows/guillotine; people vanish in a puff of smoke)
-> after 7 in-game days (DAY_SECONDS=120) the mob storms the castle and kills the king
-> Medieval Era with 16 "baffling" buildings (WEIRD)
-> whole island becomes a city (medieval houses, stone streets), one green park where nature still grows
-> population grows to 200 -> people fix every mistake (weird buildings replaced, wrong houses turned upright)
-> everyone swaps furs for real clothes -> wild horses in the park get tamed, then ridden -> carriages hitched to half the horses
-> blacksmith, bakery and stable open; owners hire 2 workers each, who do real job loops -> ending.

## Code map (search these names in index.html)
- Humans: `addHuman`, `POSES`, `doAct` (option `patience` = walk timeout, default 25s), `think`, `updateHuman`, `ROLES`.
- Speech: `SPEECH[topic]`, `line(topic)`, `sayBubble` (also calls `speak`).
- Sound: `startAudio`, `tone`, `noise`, `sfx`, `updateSound`, `speak` (browser text-to-speech, voice per personality).
- Tribal: `startTribal`, `kill`, `buildPens`, `updateTribal`.
- Civilization: `buildPaths`, `startBronze`, `startPyramid`, `buildCastle`, `gatherCrowd`, `updateCivilization`.
- Kingdom: `buildCities`, `makeServant`, `banSlavery`, `lead`, `updateDevices`, `stormCastle`, `killKing`, `buildWeird`, `updateKingdom`.
- Island city: `startMetropolis`, `medievalHouse`, `MISTAKES`, `pave`, `natureSpot`, `startFixing`, `fixBuilding`, `updateMetropolis`.
- Town life: `dress`, `getDressed`, `tame`, `rideHorse`, `updateHorse`, `dismount`, `addCarriage`, `addShop`, `JOBS` (blacksmith/baker/stablehand), `ROLES.hiring`, `buyBread`, `updateTown`.

## Where we stopped
- Last feature added: town life (clothes, horses, carriages, shops with workers). Only syntax-checked.
- Possible lag with 200 people; far humans (>110) are hidden in `updateMetropolis`. Lower the cap in `maxHumans` if needed.
- Backups in this folder: `index.before-sound.html`, `index.before-execfix.html`, `index.before-metropolis.html`, `index.before-town.html` (safe to delete once the game works).

## Notes
- Keep violence non-graphic (puff of smoke).
- Run a syntax check after big edits.
