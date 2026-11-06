# Poker

Texas Hold'em between players. The house does not play; it only takes a rake from pots that saw a flop.

File: `config/games/poker.lua`

Players buy in with chips when they sit down, can check, call, bet, raise, go all-in and fold, and can rebuy when their stack runs out.

| Key | Default | Description |
| --- | ------- | ----------- |
| `TurnTime` | `25` | Seconds for each player's turn. |
| `ResultTime` | `8` | Seconds the result is shown. |
| `IdleRounds` | `3` | Hands in a row without chips for the big blind before the seat is freed. |
| `DealTime` | `1500` | Milliseconds between the streets. |
| `DealCard` | `900` | Milliseconds between hole cards as they are dealt. |
| `Rake` | `0.05` | The part of each pot the house takes. |
| `RakeCap` | `500` | The most the house takes from one pot. |

## Tables

```lua
Tables = {
    { coords = vec4(1026.73, 67.01, 71.48, 10.79), model = 'vw_prop_casino_3cardpoker_01', small = 10, big = 20, min = 400, max = 4000 },
    { coords = vec4(1019.49, 44.72, 72.28, 195.79), model = 'vw_prop_casino_3cardpoker_01b', small = 50, big = 100, min = 2000, max = 20000 },
},
```

`small` and `big` are the blinds. `min` and `max` are the buy-in.
