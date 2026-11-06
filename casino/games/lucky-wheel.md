# Lucky wheel

One free spin per character every 24 hours. Prizes can be chips, cash, items or a car that is stored in the player's garage.

File: `config/games/wheel.lua`

| Key | Default | Description |
| --- | ------- | ----------- |
| `Coords` | `vec4(978.01, 50.35, 73.68, 327.99)` | Where the wheel stands. |
| `Cost` | `0` | Chips per spin. `0` is free. |
| `Cooldown` | `24 * 60 * 60` | Seconds between spins for one character. Can also be changed in the admin panel. |
| `SpinTime` | `15000` | Milliseconds the wheel spins. |
| `Turns` | `10` | Full turns before it stops. |

## Prizes

```lua
Prizes = {
    { type = 'chips', amount = 50, weight = 22 },
    { type = 'item', name = 'gold_ring', amount = 1, weight = 8 },
    { type = 'money', amount = 1000, weight = 4 },
    { type = 'car', weight = 0, color = '#1f3f7a' },
    ...
},
```

| Type | Fields | Prize |
| ---- | ------ | ----- |
| `chips` | `amount` | Chips |
| `money` | `amount` | Cash |
| `item` | `name`, `amount` | An inventory item. Make sure it exists in your inventory. |
| `car` | | The car set in `Car` below, stored in the player's garage. |

`weight` is how likely a prize is compared to the others. `label` overrides the generated name and `color` the colour of the segment.

The default prizes use the items `gold_ring`, `repair_kit`, `diamond_ring` and `diamond_necklace`.

## The car

```lua
local Car = {
    Model = 'zentorno',
    Label = 'Pegassi Zentorno',
    Value = 700000,
    Garage = 'casino',
    Coords = vec4(963.34, 47.94, 74.97, 275.82),
    Speed = 8.0,
    RenderDistance = 60.0,
    Chance = { Min = 0.0005, Max = 0.005, Ramp = 3 },
}
```

| Key | Description |
| --- | ----------- |
| `Model` / `Label` | The car and its name. |
| `Value` | The car can only be won once the car fund (house profit) has reached this. |
| `Garage` | The garage the car is stored in, as your garage resource names it. |
| `Coords` / `Speed` | The show car on the podium and how many degrees per second it turns. |
| `Chance` | The car chance grows from `Min` to `Max` as the fund goes from `Value` to `Value * (1 + Ramp)`. |

The car is given through the framework bridge. Keys are handled by `Config.Bridge.VehicleKeys`: `none` (most key systems hand out keys on spawn), `item` (gives `Config.KeyItem` with the plate as metadata) or `custom`.

The car fund can be seen and set in the admin panel under **Economy**, or with the `casinopool` console command.
