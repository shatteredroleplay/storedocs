# Blackjack

Up to four players against the dealer. Six decks, the dealer stands on 17 and blackjack pays 3:2. Players can hit, stand, double and split.

File: `config/games/blackjack.lua`

| Key | Default | Description |
| --- | ------- | ----------- |
| `BetTime` | `15` | Seconds to place a bet. |
| `TurnTime` | `20` | Seconds for each player's turn. |
| `ResultTime` | `6` | Seconds the result is shown. |
| `IdleRounds` | `3` | Rounds in a row without a bet before the seat is freed. |
| `DealTime` | `2000` | Milliseconds between dealt cards. |
| `HitTime` | `1500` | Milliseconds after a hit before the next action. |
| `RevealTime` | `2000` | Milliseconds the hidden card shows before the dealer draws. |
| `PromptDelay` | `2000` | Milliseconds after the table is cleared before the keys show again. |
| `SplitOffset` | `0.1` | How far a split hand lies from the first one. |

## Tables

```lua
Tables = {
    { coords = vec4(1023.62, 62.40, 71.48, 192.99), model = 'vw_prop_casino_blckjack_01', min = 25, max = 5000 },
    { coords = vec4(1024.57, 58.28, 71.48, 12.99), model = 'vw_prop_casino_blckjack_01', min = 25, max = 5000 },
    { coords = vec4(1021.55, 48.90, 72.28, 282.99), model = 'vw_prop_casino_blckjack_01b', min = 500, max = 10000 },
    { coords = vec4(1015.58, 47.49, 72.28, 103.30), model = 'vw_prop_casino_blckjack_01b', min = 500, max = 10000 },
},
```

`min` and `max` are in chips.
