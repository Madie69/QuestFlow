# QuestFlow

QuestFlow is a dependency-free live quest-routing addon for World of Warcraft Forever.

Instead of treating each quest as an isolated checklist item, QuestFlow continuously evaluates the active quest log, Blizzard quest POIs, nearby objective areas, turn-ins, player movement, and geographic clustering to reduce unnecessary backtracking.

## Current beta

**v0.3.25**

The current beta restores geographic clustering for nearby objectives from different quests while preserving each quest and all unfinished objectives in the shared route stop.

### Current features

- Live route optimization from the player's current position
- Geographic clustering of nearby quest objectives
- Separate objective and turn-in route stops
- CURRENT plus the next two route stops in the tracker
- All unfinished objectives shown for quests in a visible route stop
- Built-in directional arrow
- Blizzard quest-blob-aware arrow hiding for the CURRENT quest
- World-map and minimap route visualization
- Ghost mode routing back to the player's corpse
- Optional hiding of Blizzard's quest tracker
- Dependency-free implementation

## Install

Copy the `QuestFlow` folder into your World of Warcraft Forever `Interface/AddOns` directory, then enable **QuestFlow** from the AddOns screen.

## Commands

- `/qf` — toggle QuestFlow
- `/qf blizzard` — hide/show Blizzard's quest tracker
- `/qf arrow` — hide/show QuestFlow's navigation arrow
- `/qf map` — hide/show the map route
- `/qf recalc` — force a route recalculation
- `/qf reset` — clear ignored/deferred quest state
- `/qf lock` — compatibility command; routing is always live and this forces a re-optimization

## Design goal

> Don't optimize the next quest. Optimize the entire trip.

QuestFlow is currently in beta and is being tested against real leveling routes in WoW Forever.
