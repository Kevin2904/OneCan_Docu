# The OneCan island!

## Interaction Flow


|  |  |  |
| :--- | :--- | :--- |
| Key Listener: They normaly are in the Client module files. From here we can call an event, send a message through the networker or set some configuration in the game. |  |  |  
| Call Event: They normaly are in the Client module files. From here we can call another event, send a message through the networker or set some configuration in the game. |  |  |
| Send message through the networker: It will go to `package/client/src/core/MessageHandler.ts`. According to the message type it can call an event, set some configuration for the functionability of the game or send a message to the networker manager in the server module. | If we send a message to the networker from here, it will go to `package/server/src/core/MessageHandler.ts`. So here we can get information, save information or just set a change to trigger an action. To display this to the front end, we need to go all the way back to the client module. |  |
| set configuration: just set some information to generate changes in the front end or other functionabilities |  |  |

<br><br>

## Set new message type
- Go to `Packages/common/src/messages/schema.proto` find message Server and add a new type in the enum.
- run yarn `proto:generate` command

<br><br>

## Set new event type

- Go to `Packages/client/src/utils/constants.ts` find the const Events and add `KEY:VELUE` element.