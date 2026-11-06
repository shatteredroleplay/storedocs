# Economy

File: `config/economy.lua`

## House pool

The house bankroll, counted in chips. Every bet goes into it and every win is paid from it.

```lua
Config.Pool = {
    Start = 500000,
    Cap = 5000000,
    MaxBetPct = 0.015,
    Protection = {
        Bias = { Max = 0.3, Curve = 2 },
        HighRoller = { Loss = 5000, Chance = 0.25 },
    },
}
```

| Key | Description |
| --- | ----------- |
| `Start` | The pool on the very first start. |
| `Cap` | The pool never grows past this. |
| `MaxBetPct` | The largest single bet as a part of the pool. `0.015` is 1.5%. Table maximums are lowered to it. |
| `Protection.Bias.Max` | The highest chance (`0.3` = 30%) that the house steers an outcome, used when a win is as big as the max bet. |
| `Protection.Bias.Curve` | Makes small wins much less likely to be steered. |
| `Protection.HighRoller.Loss` | A loss of this many chips or more is steered with `HighRoller.Chance`. |

Set `Bias.Max` and `HighRoller.Chance` to `0` to turn protection off. Protection can also be changed live in the admin panel under **Economy**.

## Cashier

```lua
Config.Cashier = {
    MaxExchange = 100000,
    Account = 'cash',
}
```

`MaxExchange` is the most that can be exchanged at once. `Account` is where the money is taken from and paid to: `'cash'` or `'bank'`. See [Cashier](../games/cashier.md).

## House income

A part of the casino's takings can be paid to a society account.

```lua
Config.HouseIncome = {
    Mode = 'none',
    Percent = 0.1,
}
```

| Mode | Description |
| ---- | ----------- |
| `none` | Nothing is paid out. |
| `turnover` | `Percent` of every bet. |
| `profit` | `Percent` of what the house wins. Losses are carried over. |

The society system is set with `Config.Bridge.Society` and the account name in `config/server.lua`. See [Server settings and logs](server.md).

## Rigging

```lua
Config.Rig = {
    Tries = 100,
    Feed = 50,
}
```

`Tries` is how many alternative outcomes are rolled to find one that matches a rig. `Feed` is how many steered outcomes the live feed remembers. See [Rigging](../administration/rigging.md).

## Statistics

```lua
Config.Stats = {
    Flush = 15,
    RetentionDays = 14,
    BigWin = 50000,
}
```

| Key | Description |
| --- | ----------- |
| `Flush` | Seconds between database writes. |
| `RetentionDays` | How long single rounds are kept for player history. Totals are kept forever. |
| `BigWin` | A win of this much money is logged and shown in the live feed. |
