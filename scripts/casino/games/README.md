# Games

Every game has its own file in `config/games/`. Bet limits are in chips, and every table maximum is also lowered to what the house pool allows (see [House pool](../configuration/economy.md#house-pool)).

| Game | File | Players |
| ---- | ---- | ------- |
| [Blackjack](blackjack.md) | `config/games/blackjack.lua` | Up to four against the dealer |
| [Roulette](roulette.md) | `config/games/roulette.lua` | Shared table |
| [Baccarat](baccarat.md) | `config/games/baccarat.lua` | Shared table |
| [Poker](poker.md) | `config/games/poker.lua` | Players against each other |
| [Slots](slots.md) | `config/games/slots.lua` | One player per machine |
| [Horse racing](horse-racing.md) | `config/games/track.lua` | One race for the whole casino |
| [Lucky wheel](lucky-wheel.md) | `config/games/wheel.lua` | One spin at a time |

Chips are bought and sold at the [Cashier](cashier.md).

## Common table settings

Blackjack, roulette, baccarat and poker share these keys:

| Key | Description |
| --- | ----------- |
| `BetTime`, `TurnTime`, `ResultTime` | Seconds for betting, for each turn and for showing the result. |
| Keys ending in `Time` with large values (`DealTime`, `SpinTime`) | Milliseconds. |
| `IdleRounds` | Rounds in a row without a bet before the seat is freed. |
| `RenderDistance` | How far away the table and its cards and chips are drawn. |
| `SitDistance` | How close a player must be to sit down. |
| `Board` | Position and size of the floating texts over the table. |
| `Tables` | One entry per table: `coords` (`vec4`), the table `model`, and its limits. |

Games can be closed, and table limits changed, live from the admin panel under **Settings**.
