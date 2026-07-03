# HSK Grower Cut Trees Patch

Patch for RimWorld HSK 1.5: adds a separate **farmer** sub-work for cutting trees in growing zones before sowing.

## Dependencies

- Harmony
- Work Tab

SeedsPlease is **optional**. When present, the patch also covers `GrowerSowWithSeeds` and blocks SeedsPlease auto-designation of growing-zone trees for Gardener.

Load this mod after Harmony and Work Tab.

## What it fixes

In growing zones, HSK sowing (`GrowerSow`, and optionally SeedsPlease) embeds `CutPlant` jobs when a tree blocks a cell. That clearing shares the same Work Tab sub-priority as sowing, so pawns alternate in a loop:

1. cut one blocking tree;
2. walk to storage for seeds;
3. sow one or a few clear cells;
4. repeat.

The patch adds **fell trees** (`GrowerCutPlants`) as its own farmer sub-work and routes all growing-zone tree cuts through it. Embedded cut jobs from sow work givers are suppressed; Farmer no longer auto-takes those trees when SeedsPlease is loaded.