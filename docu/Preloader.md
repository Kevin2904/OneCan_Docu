# Internal Documentation

## Preloader.ts

`There is an scene.ts called Preloader`, in its class, we will call all the resources we need for the different scenes, so we don't need to do that in each scene.ts we create.

If we follow the same art line we will use the same assets for almost all the scenes, so it is better if we loaded them just once at the begining. It is better to have all that in just one place as well.

### load tilemapTiledJSON()


There is a method called `Phaser.Scene.load.tilemapTiledJSON()`, it is the one we will use to load the tilemaps. We will need to pass a `key:string` and an `url:string` as parameters: 
- key: how we identify the loaded map.
- url: path to the tilemap we want to load.

```ts
this.load.tilemapTiledJSON("map", "assets/tilemaps/Map1.json");
```

The importatn thing to know here is that the `key` you use to load the tilemap `is the same one` you need to pass as parameter to the `MapManager.load()` method to build the scene in the other scene.ts files. 

```ts
// preload() methon in preloader.ts
...
this.load.tilemapTiledJSON("map", "assets/tilemaps/Map1.json");
...


// create() method in world.ts
...
MapManager.load(this, "map");
...
```

<br><br>
|  |  |  |
| :--- | :--- | :--- |
| [Prev page](./NewScene.md) |  | [Next page](./RenderAndStartScene.md) | 