# MapRipperProject - Heroes and Generals - 2016
The project contains restored maps from the game Heroes and Generals - 2016, converted into Blender format.

Notice: Maps are restored and don't have 100% accurate terrain, object position and rotation (although this is the best accuracy you can achieve). This is due to the nature of application that was used to extract assets (Ninja Ripper extracts models from GPU memory, that are rendered in the game window, everything that is not present is not extracted). Because the extraction was performed at the spawn screen (usually, the camera is above the center of the map, showing only half of it) a lot of the objects are missing.

# Files:
`MAP_NAME\Map.blend` - Restored map.

`MAP_NAME\GameMap.png` - Unpacked game texture, adjusted to new 2048x2048 and 1024x1024 terrain size (green colour).

`MAP_NAME\TerrainFeatures.png` - Unpacked game texture, adjusted to new 2048x2048 and 1024x1024 terrain size (green colour).

`MAP_NAME\TerrainMaterialIndex.png` - Unpacked game texture, adjusted to new 2048x2048 and 1024x1024 terrain size (green colour).

`MAP_NAME\Object\OBJECT_GROUP\OBJECT_SUBGROUP.txt` - Exported Blender objects position and rotation.

# Restoration:
- Terrain:

  Original terrain was segregated into two areas: 1) Area for ground battles that covered 2000x2000 meters on big maps, and 1000x10000 on small maps and consisted of multiple parts. The further the part was from the center, the lower level of detail it had, with some parts missing around the edges (due to Ninja Ripper). As a result a lot of terrain detail was lost. Polygon count was increased on low detailed parts to fit 2x2 meter grid smoothing the height of the vertices. In addition to that missing parts were generated based on existing terrain, alongside an extra terrain around whole area to fit 2048x2048 and 1024x1024 meters (this should save time, if you want to port terrain to other game engines). All parts were stitched together into one model. 2) Area for air battles that covered an additional 1000 meters on big maps and 500 on small maps around the first area and consisted of mirrored parts from it. This area had the lowest detail (16 polygons), didn't have any objects on it and was removed.

- Objects:

  Almost all models were extracted with lowest level of detail possible, sometimes to the point of being a cube, with no information about position and rotation. All models were sorted into groups (Bush, Rock, Structure, Tree) and subgroups (Bush1, Bush2, Bush3) based on the size or model type (notice that if the original rock model had different scale it could have gone into Rock1, Rock2, Rock3 at the same time). Every model position and rotation (apart from Structure group) was restored (notice that rotation was simply randomized, but it shouldn't matter for bushes, rocks and trees).

# To Do:
Sort bushed for: Factory, Hill60, Khutor, KrepostOutpost

# Thanks:
Elkkut - Providing Ninja Ripper files.

BluRay - Sorting objects into groups.
