# Changelog

All notable public QuestFlow changes will be documented here.

## v0.3.27 Beta — 2026-09-20

### Ghost Mode
- Fixed Forever-client startup error caused by registering unsupported `CORPSE_POSITION_UPDATE`.
- Kept the v0.3.26 corpse-target acquisition fix: QuestFlow searches the current map and parent-map chain for Blizzard's corpse position.
- Uses supported death/resurrection events plus the existing live refresh/movement loop for corpse-run navigation.
- Preserves the v0.3.25 routing and UI baseline.

## v0.3.25 Beta — 2026-09-20

This is the clean public-development baseline for QuestFlow.

### Routing
- Added wider 7.5% geographic clustering for objective stops.
- Nearby objectives from different quests can share one route stop.
- Preserved individual quest identity and unfinished-objective text inside shared stops.
- Kept turn-in clustering at 4.5%.
- Objective stops and turn-in stops remain separate.
- Route order continuously recalculates from the player's current position.

### Navigation
- QuestFlow tracker, directional arrow, and map route consume the same optimized route.
- Navigation arrow uses the CURRENT quest's Blizzard objective blob when available.
- Point-POI fallback remains available for destinations without a Blizzard objective blob.
- Ghost mode routes the player back to their corpse before resuming normal quest routing.

### Tracker
- Displays CURRENT plus the next two optimized route stops.
- Displays all unfinished objectives for quests in a visible shared stop.
- Keeps quests with unresolved Blizzard POI data visible as LOCATION PENDING.

### UI
- Dependency-free navigation arrow.
- World-map and minimap route visualization.
- Draggable minimap control.
- Lockable/resizable QuestFlow tracker.
- Optional Blizzard quest-tracker hiding.

### Notes
- Timed-quest experiments are intentionally excluded from this baseline.
