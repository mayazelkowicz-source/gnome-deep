# Gnome Deep: Maze of Greed

A browser game that runs entirely client-side — a single `index.html`, no server, no build step.

**Play:** https://mayazelkowicz-source.github.io/gnome-deep/

A greedy gnome pushes his wheelbarrow through an endless mine, racing a cave-in toward the exit.

## Controls
- **A / D** or **← / →** — walk
- **Space** (or **W / ↑** away from ladders) — jump; hold for higher jumps
- **W / ↑** at a ladder junction — climb up a level
- **S / ↓** at a ladder junction — climb down a level
- **Enter / Space** — start
- **R** — restart after the results or cave-in screen (same mine, so scores are comparable)
- **M** — toggle minimap size
- **G** — route guide on/off
- **X** — sound on/off

## How it plays
- **Diamonds & Junk** lie along the tunnels. From afar they're identical glowing orbs — you only
  see what they really are up close. Jump over anything you don't want to collect.
- **Diamonds** pile up in your wheelbarrow.
- **Junk** knocks 3 diamonds out of the wheelbarrow and permanently slows you by 10% (down to 50%).
- **Route hints:** at junctions, a faint sparkle marks a route with more diamonds than junk; a dust
  cloud marks a junkier one.
- **Cave-in:** a collapsing wall advances from the left and speeds up over time. If it catches you,
  it's game over.
- **Exit:** always 15 tunnel segments (~350 m) to the right of the start. Reaching it freezes the game
  and shows your results.

## Scoring
**Final score = diamonds in the wheelbarrow × 100 × time bonus**

The time bonus is ×3.00 if you escape within 45 s, then drops by 1× every 45 s, bottoming out at ×1.00.
Your best score is saved in the browser with `localStorage`.

## Sound
All sound is synthesized live with the Web Audio API — a ding for diamonds (rising in pitch as the
pile grows), a buzz for junk, a rumble that swells as the cave-in closes in, a crash when it catches
you, and a fanfare at the exit. No audio files.

## The mine
Generated in chunks as you explore, so it never ends. All randomness is seeded: the same seed
always produces the same layout and items. The seed is shown under the minimap and stored in the
URL — share `?seed=12345` to play the same mine. A guaranteed path to the exit always exists.

Dead ends are rare (about 6% of junctions). Each one is blocked by rubble with a **✕ DEAD END**
sign in the tunnel and marked with a red ✕ on the minimap before you reach it.

## Minimap & route guide
- Tunnels you've explored, your position (red dot) and the cave-in front (red edge)
- **EXIT** in gold: a pulsing beacon when it's on the map, or an edge arrow with the distance
  (e.g. `EXIT 230 m`) when it's off the map
- A dashed green **route** from you to the exit, recalculated as you move
- A green arrow beside the gnome shows the next step: walk left/right, or climb up/down
- Red ✕ marks for dead ends on your level and the levels next to it
- Never shows items
