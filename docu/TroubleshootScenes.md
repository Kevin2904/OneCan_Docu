# Internal Documentation

## TroubleShoot

### Collisions

If you are having issues with the colissions when render a new tilemap:

- Ensure you uploaded the tilemap .json to `packages/client/public/assets/tilesets/` and to `packages/server/src/assets/tilemaps/` as well.
- Ensure the `GameManager.start()` class-method in the  `packages/server/` module is calling the correct tiledmap.
    - This method called `MapManager.load(tilemapPath)`, thats the one you need to check.

<br><br>

### Scene is not loaded

Probably the scene is being loaded, rendered and displayed but the camera y way to long from where the map is. Remember the `coords will change in each scene according with the size of the tilemap`. So try:

- Set your OneCan on the rigth x, y coords.

<br><br>
|  |  |  |
| :--- | :--- | :--- |
| [Prev page](./RenderAndStartScene.md) |  | [Next page](./NewNPC.md) | 
