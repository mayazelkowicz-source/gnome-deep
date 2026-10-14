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

The minimap shows only tunnels you've seen, your position, the cave-in front, and a glowing
marker pointing toward the exit — never the items.
