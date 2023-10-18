# Heroes and Generals - 2016 - Maps
Maps extracted from the game Heroes and Generals - 2016 with Ninja Ripper and converted to Blender format.

# Conversion:
Due to the nature of extraction method (Ninja Ripper extracts models from GPU memory), a lot of work had to be done even before correcting the resulted output: finding correct FOV for reprojection, using correct files, flipping, rotating models and removing junk.

Original terrain was separated into two areas: 1) Playable area for ground vehicles 2) Playable area for flying vehicles.

First area covered 2000x2000 meters on big maps, and 1000x10000 on small maps and consisted of multiple parts. The further the part was, the less detail (number of polygons) it had (a form of LOD for terrain, to save processing power), with some parts missing around the edges. As a result a lot of terrain detail was lost. Polygon count was increased on low detailed parts to fit 2x2 meter grid smoothing the height of the vertices. In addition to that missing parts were generated alongside an additional terrain around existing area to fit 2048x2048 and 1024x1024 meters (this should save time, if you want to convert terrain to other game engines, usually number fits x2 muliplication size). All parts were stitched together into one big model. `Map.png` file, contains ingame terrain map, with additional terrain, generated around existing area to fit 2048x2048 and 1024x1024 meters.

Second area covered an additional 1000 meters on big maps and 500 on small maps around the first area and consisted of mirrored parts from it. This area had the lowest detail (16 polygons), didn't have any objects on it and was removed becouse of that.

Original objects had their position (X, Y, Z) at 0, 0, 0, with some models stitched together into one. Almost all models were represented with lowest LOD possiable (to the point of beeing a cube). All models were sorted into groups for easier use (Bush, Rock, Structure, Tree). Bush and Tree models were unstitched and their model origin was reset to geometry (the center of mass), as a result you can use their X and Y position (Z position will be off, so you will need to get around that, I suggest casting a ray at X, Y in the air, down towards the terrain and spawn a required model on collision). Positions were exported into `.txt` files, located in map's `Object` folder. Rock models weren't sorted (there are almost 3000 of them on every map, sorting and unstitching them into separate models will be a pain). Structure models weren't sorted and may contain dynamic objects (units, vehicles), extracted from the GPU memory.

# To Do:
ColmarHamlet - Unstitch objects, reset objects origin, export objects positions.

Factory - Sort objects, unstitch objects, reset objects origin, export objects positions.

ForwardAirfield - Unstitch objects, reset objects origin, export objects positions.

Hill60 - Unstitch objects, reset objects origin, export objects positions.

Khutor - Reset objects origin, export objects positions.

KrepostOutpost - Process terrain, Sort objects, Unstitch objects, reset objects origin, export objects positions.

MountainTown - Unstitch objects, reset objects origin, export objects positions.

SamreeDepot - Process terrain, Sort objects, Unstitch objects, reset objects origin, export objects positions.

Sawmill - Reset objects origin, export objects positions.

Town - Unstitch objects, reset objects origin, export objects positions.

VillageSkirmish - Process terrain, Sort objects, Unstitch objects, reset objects origin, export objects positions.

# Thanks:
Elkkut - Providing Ninja Ripper files.

BluRay - Helping in sorting objects into groups in Blender.
