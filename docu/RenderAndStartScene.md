# Internal Documentation

## How to render a scene

Now that we have the scene.ts and the resourses preloaded in the preloader.ts; we need to render and start the scene in game. 

So, to render we just add the `new scene class` to the scene key in the `const config` that is in the `GameRender.tsx` and it will do the rest for us.

```ts
scene: [Preloader, World, NewSceneClass, ...],
```
And then start the scene wherever you need. 

```ts
this.scene.start(Scenes.CONSTANT);
```
Just remember, to do this, we use the scenes constant in `packages/client/src/utils/constants.ts`. 

<br><br>
|  |  |  |
| :--- | :--- | :--- |
| [Prev page](./Preloader.md) |  | [Next page](./TroubleshootScenes.md) | 