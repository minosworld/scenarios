# Navigation Benchmark Scenarios

This repository contains standard scenarios for benchmarking navigation agent performance on the [SUNCG](http://suncg.cs.princeton.edu/) and the [Matterport3D](https://niessner.github.io/Matterport/) datasets.

The scenarios are defined in CSV (comma separated value) format files where each row provides the state for one episode. The following column values are provided for each episode:

- `episodeId`: integer id for given episode within the set.
- `split`: `train`, `val`, or `test` indicating split for the episode.
- `task`: string id for task type, one of `p` for `point_goal`, `o` for `object_goal`, or `r` for `room_goal`.
- `sceneId`: id of scene within which episode takes place.
- `level`: integer id of level (typically floor) within scene.
- `startX`, `startY`, `startZ`: coordinates of agent starting position in scene space.
- `startAngle`, `startTilt`: azimuth angle (counter-clockwise from scene space +X axis) and vertical tilt angles of agent starting state.
- `goalRoomId`, `goalRoomType`: string id and category of room in which the goal resides. Required for `room_goal`, optional otherwise.
- `goalObjectId`, `goalObjectType`: string id and category of goal object. Required for `object_goal`, optional otherwise.
- `goalX`, `goalY`, `goalZ`: coordinates of goal point in scene space. Required for all task types. Position of goal for `point_goal`, position of object centroid for `object_goal`, or arbitrary point within goal room for `room_goal`.
- `goalAngle`, `goalTilt`: angles defining desired view of goal. Reserved, currently not used.
- `dist`, `pathDist`: Euclidean and geodesic (along shortest path) distance from agent start position to goal position
- `pathNumDoors`, `pathDoorIds`: integer number of doors along shortest path from start to goal, and string of `:`-separated door ids along path. Note that doors at start or goal points are included.
- `pathNumRooms`, `pathRoomIndices`: integer number of rooms along shortest path from start to goal and string of `:`-separated room ids along path. Note that starting and ending rooms are included.


# Changelog

## [0.1.0] - 2018-06-03
### Initial beta release
- Added v1 scenarios for SUNCG and Matterport3D
