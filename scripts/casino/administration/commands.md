# Commands

## Players

| Command | Description |
| ------- | ----------- |
| `/casinohud` | Hide or show the chip HUD. Set by `Config.Atmosphere.Hud.Command`. |

## Admins

| Command | Where | Description |
| ------- | ----- | ----------- |
| `/casinoadmin` | In game | Open the admin panel. Set by `Config.Admin.Command`. |

## Server console

| Command | Description |
| ------- | ----------- |
| `casinoqa [server id]` | Self test. Checks the database, every bridge and the chip mode. With a server id it also checks that player's identifier, name, cash, bank, chips (adds and removes one chip), ban status and admin permissions. |
| `casinobridge` | Prints the picked bridges, the chip mode, the locale and whether the database is ready. |
| `casinopool [pool] [fund]` | Prints the pool, the max bet and the car fund. With values it sets the pool (in chips) and the car fund. |

## Debug only

These only exist while `Config.Debug = true`.

| Command | Where | Description |
| ------- | ----- | ----------- |
| `/casinotest` | In game | Tests notifications, the input dialog and the connection to the server, and prints what the client sees. |
| `/casinotarget` | In game | Adds a test target option to the slot machines to check the target bridge. |
| `casinochips <server id> <amount>` | Console, or in game with `economy` | Gives chips. A negative amount takes chips. |
| `/casinowheel [prize]` | In game with `rig` | Test spin of the lucky wheel, on a given prize index or a random one. |
