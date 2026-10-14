# Gnome Deep: Maze of Greed

A browser game that runs entirely client-side — a single `index.html`, no server, no build step.

**Play:** https://mayazelkowicz-source.github.io/gnome-deep/

## Controls
- **A / D** or **← / →** — walk
- **Space** (or **W / ↑** away from ladders) — jump; hold for higher jumps
- **W / ↑** at a ladder junction — climb up a level
- **S / ↓** at a ladder junction — climb down a level
- **M** — toggle minimap size
- **Enter** — after reaching the exit, descend into the next mine

## The mine
The mine is generated in chunks as you explore, so it never ends. All randomness is
seeded: the same seed always produces the same layout. The current seed is shown under
the minimap and stored in the URL — share `?seed=12345` to play the same mine.

The minimap shows only the tunnels you've seen, your position, and a glowing marker
pointing toward the exit.
