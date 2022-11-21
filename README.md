# ragemp-gtav-heightmap
 
The repository contains a helpful file with Z-heights for any given X,Y coordinate in GTA:V. I originally wrote a client-side script in JavaScript back in 2018 that would teleport the player in a grid pattern and grab the heights around him using
```
entity.getHeight(X, Y, Z, atTop, inWorldCoords);
```
from https://wiki.rage.mp/index.php?title=Entity::getHeight
This is not perfect, and I'm pretty sure that there exists proper height maps that would produce the same.

The result of running the height grabber was the file ```data_file/GTAV_HeightMap_Data.data```.
All heights are within a bounded box with a lower left point and upper right point: 
* LOWER LEFT: (-4100,-4300)
* UPPER RIGHT: (4300, 7825)

Beaware that some heights might be 0, but my experience is that this is only a few of them.

<h2>To use</h2>

Just invoke GetHeightAtXY(...) from MapDataLibrary as such:
```
float height = GetHeightAtXY(goto.X, goto.Y);
NAPI.Entity.SetEntityPosition(ply, new Vector3(goto.X, goto.Y, height));
```