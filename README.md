# Last Light — Horde Defense

A playable browser tower defense game: hold three lanes against escalating zombie hordes using Gatling turrets, scatterguns, and explosive blast wire.

## Play

https://mysticalg.github.io/last-light-horde-defense/

## Controls

- Select a weapon with 1–3, then click an empty square to build.
- Click a turret to upgrade or sell it.
- Space starts the next wave, P pauses, M mutes.
- Survive ten waves to unlock endless play.
- Audio starts after the first click. Best kill count is stored in your browser.

## Run locally

No build or dependencies are required. Serve the static game folder:

```sh
python -m http.server 4173 --directory dist
```

Open http://localhost:4173.

## Publish updates

The main branch contains the source in dist/. GitHub Pages serves the gh-pages branch. After committing a change:

```sh
git push github main
git subtree push --prefix dist github gh-pages
```

## Artwork and implementation

Original image-generated terrain and transparent character/turret/trap artwork are included in dist/assets. Gameplay, particles, lighting feedback, and synthesized audio use browser Canvas and Web Audio APIs. No runtime API keys or external services are needed.

## Validation

Tested in desktop Edge with a mobile viewport check. Combat, placement, credit rewards, upgrades, selling, repair, pause, restart, blast-wire detonation, and controlled victory/loss/endless transitions passed without page runtime errors. A synthetic 360-zombie simulation/draw check averaged about 2.1ms per frame on the development machine. Full campaign balance, subjective audio quality, and other physical devices remain unverified.
