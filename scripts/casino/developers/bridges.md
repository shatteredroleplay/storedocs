# Bridges

Every system the casino talks to goes through a bridge, picked in `Config.Bridge` in `config/main.lua`. The bridge files are not escrowed.

| Setting | Values |
| ------- | ------ |
| `Framework` | `auto`, `qbx`, `qb`, `esx`, `ox`, `nd`, `shattered`, `standalone`, `custom` |
| `Inventory` | `auto`, `ox`, `qs`, `codem`, `tgiann`, `core`, `qb`, `esx`, `shattered`, `none`, `custom` |
| `Target` | `auto`, `ox`, `qb`, `sleepless`, `interact`, `context`, `builtin` |
| `Notify` | `builtin`, `ox`, `qb`, `esx`, `okok`, `shattered`, `custom` |
| `VehicleKeys` | `none`, `item`, `custom` |
| `Society` | `none`, `esx`, `qb`, `renewed`, `okok`, `shattered`, `custom` |
| `Logs` | `none`, `discord`, `fivemanage`, `shattered`, `custom` |

* `auto` picks the first supported resource that is running.
* The `qb` inventory also covers ps-inventory and lj-inventory, since they hook the qb-core player functions.
* The `builtin` target needs no resource: players walk up to a table and press **E**.
* If nothing fits, the fallback is `standalone` (framework), `none` (inventory) and `builtin` (target).

The bridges that were picked are printed in the server console when the resource starts, and with `casinobridge`.

## Writing your own

Each kind has a `custom` template you can fill in:

| Kind | Template |
| ---- | -------- |
| Framework | `bridge/framework/custom/client.lua` and `server.lua` |
| Inventory | `bridge/inventory/custom/client.lua` and `server.lua` |
| Notify | `bridge/notify/custom.lua` |
| Vehicle keys | `bridge/vehiclekeys/custom.lua` |
| Society | `bridge/society/custom.lua` |
| Logs | `bridge/logs/custom.lua` |

Set the matching `Config.Bridge` value to `'custom'` and fill in every function. Keep the names and return values. If a function is missing, the console names it and the bridge is marked as not usable.

### Framework functions

| Side | Functions |
| ---- | --------- |
| Server | `GetIdentifier`, `GetSource`, `GetName`, `GetMoney`, `AddMoney`, `RemoveMoney`, `HasGroup`, `OnLoad`, `OnUnload`, `GiveVehicle` |
| Client | `IsLoaded`, `IsDead`, `OnLoad`, `OnUnload` |

`GetIdentifier` must return a stable id for the character (citizenid, identifier, charId), as a string. `GiveVehicle` receives `{ model, label, garage, props }` and returns the plate.

### Inventory functions

| Side | Functions |
| ---- | --------- |
| Server | `Count`, `Add`, `Remove`, `CanCarry` |
| Client | `Count`, `SetBusy` |

### Other kinds

| Kind | Function |
| ---- | -------- |
| Target | `AddModels`, `RemoveModels` (client) |
| Notify | `Send` (client) |
| Vehicle keys | `Give(src, plate, label)` (server) |
| Society | `Deposit(amount, reason)` (server). `amount` is money, not chips. Return `true` when paid. |
| Logs | `Send(category, title, fields)` (server). `category` is `admin`, `rig`, `economy` or `bigwin`. |
