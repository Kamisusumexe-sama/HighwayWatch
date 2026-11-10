# Highway Watch

A 2.5D arcade game set in a Madina-style market on a busy highway. You are the
keeper of the crossing: scare wanderers back with your school cane before they
cross, chain scares into combos, and survive wave after wave.

## Run it

Open `index.html` in any modern desktop or mobile browser (Chrome, Edge, Firefox,
Safari). It needs WebGL. Everything is bundled, so it works offline:

- `index.html` – the whole game (HTML, CSS, JavaScript, shaders)
- `three.min.js` – three.js r128 (MIT licence)
- `fonts/` – Ultra, Anton, Bowlby One, Nunito (SIL Open Font Licence)

If your browser blocks anything when opening the file directly, serve the folder:

    python3 -m http.server 8000      # then open http://localhost:8000

## Controls (keyboard, rebindable from Controls in the menu or pause screen)

| Action | Default |
|---|---|
| Move | W A S D (arrow keys also work) |
| Swing cane | Space (or mouse click) |
| Beat dash | Hold E to aim, release to dash |
| Pause | P or Esc |

Touch: drag to move, tap **Swing**, hold **Beat** to aim and release to dash.
Touch controls are fixed. Key bindings and your high scores are saved in the
browser (localStorage).

## How it plays

- Wanderers cross from either side, hop the median, and head for the far side.
  Each one who makes it costs a life (5 lives).
- Scares chain into combos. Higher combos make you faster, change your cane
  swing (double whip, spin, flurry), and make crossers react more wildly.
- Scared crossers drop water sachets (+1 Beat Dash charge) and, rarely, health
  packs (+1 life).
- Beat dash charges through every crosser in your aim line and makes you immune
  to cars for the dash. Cars never stop for you, so watch the traffic.
- Waves start small, build into patterned formations (line, pincer, V, columns,
  fan, rush), then pause. Later waves add zigzag, stop-and-go and sprinting walkers.

## Things you can tweak

All code is in `index.html`. Useful spots (search for the names):

- `buildWave`, `waveUpdate` – wave sizes, formations and pacing
- `patFor` – when special walking patterns unlock
- `tierOf`, `scareHit`, `fleeFx` – combo tiers and crosser reactions
- `drawChar` – the character painter (all characters are drawn on canvas)
- `groundFrag`, `roadFrag` – market ground, cobblestone, asphalt and puddle shaders
- `BG_FRAG`, `FX_FRAG` – poster background and print-effect shaders
- `DEFAULT_KEYS` – default key bindings

## Credits

Built with three.js. Fonts: Ultra, Anton, Bowlby One and Nunito via Fontsource.
