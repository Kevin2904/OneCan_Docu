# Internal Documentation

## How to add elements to the game screen.

Just Line the NPCs, the logic to add elements to the screan is already done, what we need to do is desing a little bit our element and define when to display it or hide it.

- Go to `package/client/src/ui` and create a new .tsx file to design the element.
- Do some css, add the necesary listeners and return the correct HTML (Check the existen elements to have a better idea, sice all of them follows the same structure).
- Go to `package/client/src/utils`. In const UserInterface, add a new KEY:VALUE element to identify when to desplay or hide the new element (you can use the ones that already exists).
- go to `package/client/src/ui/main.tsx`. Add the new element where you need it to be.

> ### Note
> Ensure this condition exists before to return the HTML since it desides if the element is displayes or hidden
> ```ts
>if (!interfaces[UserInterface.CONSTANT]) {
>    return null;
>  }
>```
> ___
>
> You can create elements to add inside anoter element and then add the last one to the `main.tsx` file. just ensure the `UserInterface.CONSTANT` for the condition mentioned above is the same for all the elements related.

Once you have averything in place, you can do something like this to display/hide an element whenever you need:
```ts
// display
Emitter.emit(Events.OPEN_UI, UserInterface.CONSTANT);

//hide
Emitter.emit(Events.CLOSE_UI, UserInterface.CONSTANT);
```

> ### Note
> You can update or animate the elements using the `useEffect()` method and adding listeners.
> 
> You can use the browser `inspector` to play arround with the css of the elements.

<br><br>
|  |  |  |
| :--- | :--- | :--- |
| [Prev page](./NewNPC.md) |  | [Next page](./Phaser3.md) | 