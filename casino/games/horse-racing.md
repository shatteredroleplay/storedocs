# Horse racing

One race runs for the whole casino. Players sit at a betting terminal, pick a horse and bet on the winner. The race is also shown on the big betting screen of the casino interior.

File: `config/games/track.lua`

| Key | Default | Description |
| --- | ------- | ----------- |
| `Center` / `Radius` | `vec3(1000.0, 55.0, 72.0)` / `90.0` | Terminals further than `Radius` from `Center` can't be used. |
| `Model` | `vw_prop_casino_track_chair_01` | The terminal chair prop. |
| `Min` / `Max` | `25` / `5000` | Bet limits in chips. `Max` is lowered to what the house pool allows and divided by the odds of each horse. |
| `Edge` | `0.06` | The house edge built into the odds. |
| `BetTime` | `30` | Seconds betting is open. |
| `RaceTime` | `20000` | Milliseconds the race runs. |
| `ResultTime` | `12` | Seconds the result is shown. |
| `Seat`, `Console`, `Camera` | | Where the player sits, where the betting screen is drawn and the camera, relative to the chair. |
| `Screen` | | The race on the big betting screen. Set `Enabled = false` to turn it off. |
| `Terminals` | `{}` | Extra terminals as `vec4(x, y, z, heading)`. The chairs already in the interior work without this. |

Horse names are in the locales under `track.horses`, separated by `|`.
