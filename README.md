# QuestFlow

**Live quest-route optimization for World of Warcraft Forever.**

QuestFlow continuously evaluates your active quest log and Blizzard's quest POI data to build a practical route through nearby objectives and turn-ins. The goal is simple: spend less time backtracking and more time actually questing.

> **Don't optimize the next quest. Optimize the entire trip.**

## Beta status

Current baseline: **v0.3.27 Beta**

QuestFlow is under active development and is being tested against real leveling routes. v0.3.27 is the current beta baseline for public development going forward.

## What it does

- Continuously re-optimizes as you move, accept quests, finish objectives, turn quests in, or change zones
- Groups nearby objectives from different quests into shared geographic stops
- Keeps objective work and turn-ins as separate route-stop types
- Shows **CURRENT** plus the next two optimized stops
- Shows every unfinished objective for quests grouped into a visible stop
- Uses Blizzard's quest-specific objective blobs when deciding when the navigation arrow should disappear
- Falls back to Blizzard POI coordinates when no objective blob exists
- Includes its own directional arrow with no TomTom dependency
- Draws the active route on the world map and minimap
- Routes ghosts back to their corpse, then resumes normal quest routing after resurrection
- Can hide Blizzard's default quest tracker
- Has no external addon dependencies

## Routing model

QuestFlow treats the active quest log as a routing problem rather than a fixed checklist.

Nearby objective POIs may be combined into a single geographic stop even when they belong to different quests. Each quest and its unfinished objectives remain individually visible inside that stop. Turn-ins are optimized as route nodes too, but objective stops and turn-in stops are never merged.

The tracker, navigation arrow, and map route all consume the same optimized route so the UI does not disagree with itself.

## Install

1. Download the current QuestFlow build.
2. Extract the `QuestFlow` folder into your WoW Forever `Interface/AddOns` directory.
3. Enable **QuestFlow** from the AddOns screen.
4. Enter the world and use `/qf` to toggle the tracker.

## Commands

| Command | Action |
| --- | --- |
| `/qf` | Toggle the QuestFlow tracker |
| `/qf arrow` | Show or hide the navigation arrow |
| `/qf blizzard` | Show or hide Blizzard's quest tracker |
| `/qf map` | Show or hide QuestFlow's map route |
| `/qf recalc` | Force an immediate route recalculation |
| `/qf reset` | Reset ignored/deferred quest state |
| `/qf lock` | Legacy compatibility command; forces re-optimization |

## v0.3.27

This release fixes Ghost Mode corpse-run navigation for the WoW Forever client. Corpse targeting now searches the player's current map and parent-map chain for Blizzard's corpse position, while avoiding the unsupported `CORPSE_POSITION_UPDATE` event registration discovered during Forever testing.

The v0.3.25 routing baseline remains intact: objective-area clustering is 7.5% normalized map distance, turn-in clustering is 4.5%, nearby objectives from different quests may share a geographic stop, and timed-quest experiment code remains excluded.

## Compatibility

QuestFlow currently targets the WoW Forever client interface used during beta testing (`Interface: 16001`).

## Project status

**Beta.** Expect route heuristics and UI behavior to continue evolving as more leveling routes and quest combinations are tested.

Bug reports and reproducible routing examples are welcome through GitHub Issues.
