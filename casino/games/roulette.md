# Roulette

American roulette with 0 and 00. Players click the felt to bet and scroll to change the amount.

File: `config/games/roulette.lua`

Bets: single numbers, red/black, even/odd, low/high, the three dozens and the three columns.

| Key | Default | Description |
| --- | ------- | ----------- |
| `BetTime` | `25` | Seconds to place bets. |
| `SpinTime` | `15500` | Milliseconds the wheel spins. |
| `ResultTime` | `8` | Seconds the result is shown. |
| `IdleRounds` | `3` | Rounds in a row without a bet before the seat is freed. |
| `MaxBets` | `10` | Different bets one player may have in a round. |
| `PickRadius` | `30` | Pixels around a bet spot where the cursor picks it. |
| `Camera` | | The table camera and the camera that follows the wheel. |

## Tables

```lua
Tables = {
    { coords = vec4(1032.16, 60.02, 71.48, 13.30), model = 'vw_prop_casino_roulette_01', min = 25, max = 5000 },
    { coords = vec4(1031.20, 64.16, 71.48, 193.30), model = 'vw_prop_casino_roulette_01', min = 25, max = 5000 },
    { coords = vec4(1016.78, 69.57, 72.28, 282.99), model = 'vw_prop_casino_roulette_01b', min = 200, max = 10000 },
    { coords = vec4(1010.81, 68.19, 72.28, 103.30), model = 'vw_prop_casino_roulette_01b', min = 200, max = 10000 },
},
```

A bet on a single number may be at most `max / 35`.
