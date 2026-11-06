# Exports

The examples assume the resource is named `casino`.

## Server

### GetChips

```lua
local chips = exports.casino:GetChips(source)
```

The player's chip balance in the current chip mode. `0` when no character is loaded.

### AddChips

```lua
local ok = exports.casino:AddChips(source, 100)
```

Gives chips. Returns `true` when they were added.

### RemoveChips

```lua
local ok = exports.casino:RemoveChips(source, 100)
```

Takes chips. Returns `true` only when the player had enough and they were removed.

### PoolBalance

```lua
local money = exports.casino:PoolBalance()
```

The house pool, in money (chips × `Config.Chips.Rate`).

### CarFund

```lua
local fund = exports.casino:CarFund()
```

The car fund for the lucky wheel car.

### Rigging

```lua
exports.casino:RigState()
exports.casino:RigFeed(since)
exports.casino:RigSet(admin, target, mode, chance, games, options)
exports.casino:RigWheel(admin, target, index)
exports.casino:RigClear(admin)
```

| Argument | Description |
| -------- | ----------- |
| `admin` | Who made the change, for the audit log: `{ id = 'identifier', name = 'Name' }`. Calls without a valid admin are refused. |
| `target` | The player's character identifier, or `nil` for the global rig. |
| `mode` | `'off'`, `'win'` or `'lose'`. |
| `chance` | 1–100. |
| `games` | A list of `'blackjack'`, `'roulette'`, `'baccarat'`, `'track'` and `'slots'`. |
| `options` | `{ minutes = number, limit = number }`, both optional. |
| `index` | The lucky wheel prize index for the next spin. |

`RigState` returns the online players with their chips, whether they are inside the casino and their rig. `RigFeed(since)` returns the steered outcomes after the given feed id (`0` for all that are remembered).

## Client

### HideHud

```lua
exports.casino:HideHud(true)
exports.casino:HideHud(false)
```

Hides or shows the chip HUD, for example while another UI is open.

### IsHudHidden

```lua
local hidden = exports.casino:IsHudHidden()
```
