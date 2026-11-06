# Events

Every event starts with the resource name. The examples assume it is named `casino`. These are local events, so listen with `AddEventHandler`.

## Server

| Event | Arguments | When |
| ----- | --------- | ---- |
| `casino:player:loaded` | `source`, `identifier` | A player's character is loaded into the casino. |
| `casino:player:unloaded` | `source`, `identifier` | A player's character is unloaded. |
| `casino:bigwin` | `{ id, name, game, wagered, won }` | A win of at least `Config.Stats.BigWin`. |
| `casino:audit` | `{ admin, action, target, time }` | An admin action was recorded. |
| `casino:rig:feed` | `entry` | An outcome was steered by a rig. |

```lua
AddEventHandler('casino:bigwin', function(win)
    print(('%s won %s on %s'):format(win.name, win.won, win.game))
end)
```

## Client

| Event | Arguments | When |
| ----- | --------- | ---- |
| `casino:active` | `active` (boolean) | The player entered or left the casino zone. |
| `casino:chips` | `amount` | The player's chip balance changed. |
| `casino:player:loaded` | | The character was loaded. |
| `casino:player:unloaded` | | The character was unloaded. |

```lua
AddEventHandler('casino:active', function(active)
    exports.casino:HideHud(not active)
end)
```

## Mute event

`Config.Atmosphere.MuteEvent` names an event of your own that the casino triggers with `true` when the crowd sound starts and `false` when it stops. See [Atmosphere](../configuration/atmosphere.md).
