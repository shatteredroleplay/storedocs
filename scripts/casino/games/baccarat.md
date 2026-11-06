# Baccarat

Punto banco. Every seat can bet on player, banker and tie at the same time.

File: `config/games/baccarat.lua`

| Key | Default | Description |
| --- | ------- | ----------- |
| `BetTime` | `20` | Seconds to place bets. |
| `DealTime` | `1500` | Milliseconds between dealt cards. |
| `ResultTime` | `7` | Seconds the result is shown. |
| `IdleRounds` | `3` | Rounds in a row without a bet before the seat is freed. |
| `Tie` | `8` | A tie pays this many times the bet. |
| `Commission` | `0.07` | The part of a banker win the house keeps. `0.05` is the usual casino rule. |

## Tables

```lua
Tables = {
    { coords = vec4(1028.92, 55.66, 71.48, 191.50), model = 'vw_prop_casino_baccarat_01', min = 25, max = 2000 },
    { coords = vec4(1013.18, 72.62, 72.28, 17.22), model = 'vw_prop_casino_baccarat_01b', min = 500, max = 5000 },
},
```
