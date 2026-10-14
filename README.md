# Gnome Deep: Maze of Greed

A browser game that runs entirely client-side — a single `index.html`, no server, no build step.

**Play:** https://mayazelkowicz-source.github.io/gnome-deep/

A greedy gnome pushes his wheelbarrow through an endless mine, racing a cave-in toward the exit.

## Controls
- **A / D** or **← / →** — walk
- **Space** (or **W / ↑** away from ladders) — jump; hold for higher jumps
- **W / ↑** at a ladder junction — climb up a level
- **S / ↓** at a ladder junction — climb down a level
- **M** — toggle minimap size
- **Enter** — next mine after reaching the exit, or retry after a cave-in

## How it plays
- **Diamonds & Junk** lie along the tunnels. From afar they're identical glowing orbs — you only
  see what they really are up close. Jump over anything you don't want to collect.
- **Diamonds** pile up in your wheelbarrow.
- **Junk** knocks 3 diamonds out of the wheelbarrow and permanently slows you by 10% (down to 50%).
- **Route hints:** at junctions, a faint sparkle marks a route with more diamonds than junk; a dust
  cloud marks a junkier one.
- **Cave-in:** a collapsing wall advances from the left and speeds up over time. If it catches you,
  it's game over.

## The mine
Generated in chunks as you explore, so it never ends. All randomness is seeded: the same seed
always produces the same layout and items. The seed is shown under the minimap and stored in the
URL — share `?seed=12345` to play the same mine. A guaranteed path to the exit always exists.

The minimap shows only tunnels you've seen, your position, the cave-in front, and a glowing
marker pointing toward the exit — never the items.
