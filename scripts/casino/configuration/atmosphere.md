# Atmosphere

File: `config/atmosphere.lua`

Everything that makes the casino feel alive. All of it only runs while a player is inside the casino zone.

| Key | Description |
| --- | ----------- |
| `Blip` | Map blip at `Config.Locations.Center`. `Label = nil` uses the locale's casino name. |
| `Crowd` | Crowd murmur played while inside. `Height` is the metres above the player it plays from: higher is quieter. |
| `MuteEvent` | An event triggered with `true`/`false` when the crowd sound starts and stops, for resources that mute the world with audio scenes (they can block streamed sound). Example: `'misc:worldMute'`. `nil` means none. |
| `Wall` | The big video wall of the casino interior: the GTA playlist (`CASINO_DIA_PL`) with animated effects on top. |
| `Hud` | Chip tracker next to the minimap: chips, start of session, net and a bar for every round. |
| `Ipls` | IPLs requested when the resource starts, for interiors that need them. Leave it empty for an MLO or bob74_ipl. |

## Chip HUD

```lua
Hud = { Enabled = true, Command = 'casinohud', Keep = 15 * 60, Bars = 24, Offset = { x = 0.8, y = 0.03 } },
```

Players can hide and show the HUD with `/casinohud`. `Keep` is how many seconds a session is kept, `Bars` how many rounds are drawn and `Offset` the screen position. Other resources can hide it with the [`HideHud` export](../developers/exports.md#client).
