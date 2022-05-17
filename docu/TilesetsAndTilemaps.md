# Internal Documentation

## How to create/add Tilesets and TileMaps

First we need to create the `tilesets` and `tilemaps` our new scene will use. To do tha I will recomed to use [Tiled](https://www.mapeditor.org/), it is a free program that suits the porpuse here.

Useful things to know about the tilesets are:
- They have a size of 16 x 16 pixeles.
- You can use the ones that are already in the repo or create new ones.
- They are stored in `packages/client/public/assets/tilesets/`

Useful things to know about the tilemaps are:
- We need them to be `.json` extension files.
- For one full screen, we need a `30 x 20 orthogonal map`.
- The map should be contructer with the next layers: `ground`, `ground2`, `upper`, `upper2`, `above`, `above1`, `above2` and `collision` where:
    - `ground` and `ground2` will containt the base of the map. As the names says, the ground.
    - `upper` and `upper2` will contain any unevenness in the map. It could be mountains, floors or constructions or anyting upper the gorund.
    - `above`, `above1` and `above2` will contain anything that will be infront of our OneCan wen we pass through. We can give some depth effect with this, for example, we can set trees and buildings here so when the OneCan Pass through they will be above as the PJ was passing behaind the object.
    - `collision` will contain the limits and walls for our pj. We set them where we want block our OneCan to pass through. 
- They are stored in `packages/client/public/assets/tilemaps/`

> ### Note
> You can use Tiled and open the Open World map `packages/client/public/assets/tilemaps/Map1.json` to check the Layers and understand them.
>
> Here is a [tutorial](https://www.youtube.com/playlist?list=PLu4oc9P-ABcOXNOyoAvnMyUwn_kkiVA5B) about Tiled that could be helpful.
>

<br><br>
[Next page](./NewScene.md)

