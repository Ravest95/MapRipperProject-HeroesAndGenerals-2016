# Heroes and Generals - 2016 - Maps
Maps extracted from the game Heroes and Generals - 2016 with Ninja Ripper and converted to Blender format.

# Conversion:
Due to the nature of extraction method (Ninja Ripper extracts models from GPU memory), a lot of work had to be done even before correcting the resulted output: finding correct FOV for reprojection, using correct files, flipping, rotating models and removing junk.

Original terrain was separated into two areas: 1) Playable area for ground vehicles 2) Playable area for flying vehicles.

First area covered 2000x2000 meters on big maps, and 1000x10000 on small maps and consisted of multiple parts. The further the part was, the less detail (number of polygons) it had (a form of LOD for terrain), with some parts missing around the edges. As a result a lot of terrain detail was lost. Polygon count was increased on low detailed parts to fit 2x2 meter grid smoothing the height of the vertices. In addition to that missing parts were generated alongside an extra terrain around existing area to fit 2048x2048 and 1024x1024 meters (this should save time, if you want to convert terrain to other game engines). All parts were stitched together into one model. `Map.png` file, contains biom terrain map, with extra terrain, generated around existing area to fit 2048x2048 and 1024x1024 meters.

Second area covered an additional 1000 meters on big maps and 500 on small maps around the first area and consisted of mirrored parts from it. This area had the lowest detail (16 polygons), didn't have any objects on it and was removed.

Almost all models were represented with lowest LOD possible (to the point of being a cube), with no information about original position and rotation. All models were sorted into groups (Bush, Rock, Structure, Tree) and subgroups (Bush1, Bush2, Bush3) based on the size (bushes, rocks) or model type (trees). Note that if the original bush model had different scale it could have gone into `Bush1`, `Bush2`, `Bush3` at the same time. Every model position and rotation (apart `Structure` group) was restored. Note that these models will have position slightly off, because of restoration method, with different rotation (should not matter for bushes, rocks, trees).

# To Do:
Factory - Sort Bush / Swap Bush, Rock, Tree

Hill60 - Sort Bush / Swap Bush

Khutor - Sort Bush / Swap Bush, Tree

KrepostOutpost - Sort Bush, Tree / Swap Bush, Tree

SamreeDepot - Unpack Terrain / Swap Rock

VillageSkirmish - Sort Bush / Swap Bush

# Thanks:
Elkkut - Providing Ninja Ripper files.

BluRay - Sorting objects into groups.
