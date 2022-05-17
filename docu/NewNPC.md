# Internal Documentation

## How to create a new NPC

This project already have all the logic to add a new npc, the only thing we need to do in order to add one more is set a couple of parameters.

- Go to `packages/common/src/utils/constants.ts` and find const `Names` if you need a new NPC name add a new `key: value` element.

- Go to `packages/server/src/events/`, there will be all the NPCs dialogs/interactions create a new one for the new NPC.

### Events

```ts
const ctx = {
  label: "start",
  choices: [],
};

const event = (id: number) => {
  const EventSystem = CreateEventSystem(id, GameManager.eventCtx[id]);
  const { Label, Say, GoToLabel, ExitEvent, Chose } = EventSystem;

  if (Label("start")) {
    Say("Hello stranger!");
    GoToLabel("greet");
  } else if (Label("greet")) {
    Say("I'm Lumen a completely normal OneCan as you. Not an alien at all.", [
      "Alien?",
    ]);
    GoToLabel("alien");
  } else if (Label("alien") && Chose("Alien?")) {
    Say(
      "Alien? What? Who says anything about aliens?"
    );
    GoToLabel("end");
  } else if (Label("end")) {
    ExitEvent();
  }
};
```

- `Label` is like a block an identifier the.
- `Say` is the NPC dialog for an specific label, it also containst the client input options.
- `GoToLabel` call an specific label.
- `Chose` is the client entry.
- The event always starts with the Label `start` and ends with the Label `end`.
___
- Once the event was created, go to `packages/server/src/events/index.ts` and map it to a numeric key in the export default.

### Add NPC

- Go to `packages/server/src/core/MapManager`, at the end of the load() method add:
```ts
this.createNPC(
    name: string,
    x: number,
    y: number,
    sprite: number,
    direction: Utils.Constants.Direction,
    event?: number
);
```

where: 
- name is the NPC name (use `Names` constant).
- x is x axis in the map where the NPC will be loaded.
- y is y axis in the map where the NPC will be loaded.
- sprite is the sprite how the NPC will look like. Check const Cans in `packages/common/src/utils/constants.ts` and add a new one if you need it.
- direction is the direction that the NPC will look at. Check enum Direction in `packages/common/src/utils/constants.ts`.
- event point to the events in `packages/server/src/events/index.ts`.

So it should look something like this:
```ts
this.createNPC(
      Names.lumen,
      2600,
      1996,
      this.CanNames["alien_can"],
      Utils.Constants.Direction.DOWN,
      3
    );
```

And thats it, you added a new NPC.

> ### Note
> We will need to find a way to load only the correct NPCs according to the scene.
>

<br><br>
|  |  |  |
| :--- | :--- | :--- |
| [Prev page](./TroubleshootScenes.md) |  | [Next page](./AddElementScreen.md) | 