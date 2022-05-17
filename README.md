# The OneCan island!

## How to run locally

Make sure to have Postgres running, and your variables
set on `packages/server/example.env` and `packages/client/.env.development`. Then set the variables in your terminal with:
```bash
export $(cat ./packages/client/.env.development ./packages/server/example.env | xargs)
```
> ### Note
> If you're on Windows Os, you have to add the variables to the System Environment Variables manually.
> - Go to the `Start` menu.
> - Look  for `Edid the system environment variables`.
> - Go to the `Advanced` tap and select `Environment Variables`.
> - In the `User variables for MyUser`, add the variables you need.
>  - Save the changes.
>
> Once you add the new environment variables, you will need to restart your machine.

Next, initialize the workspace:

```bash
yarn
yarn workspace @verso/server prisma generate
yarn workspace @verso/server prisma migrate dev
yarn dev
```  


<br><br>
## [Check Internal Documentation](/docu/TilesetsAndTilemaps)



