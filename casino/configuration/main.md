# Main settings

File: `config/main.lua`

## Locale

```lua
Config.Locale = 'en'
```

The language file from `locales/`. `en` and `sv` are included. Keys missing in a language fall back to English. See [Locales](locales.md).

## Currency

```lua
Config.Currency = {
    Symbol = '$',
    Position = 'before',
    Space = false,
    Thousands = ',',
}
```

How money is written everywhere: chat, the UI and the admin panel. `Position = 'before'` gives `$1,000`. `Position = 'after'` with `Symbol = 'kr'`, `Space = true` and `Thousands = ' '` gives `1 000 kr`.

## Debug

```lua
Config.Debug = true
```

Prints what the bridge picked and every rejected request to the console, and enables the debug commands (`casinotest`, `casinotarget`, `casinochips`, `casinowheel`). Turn it off on a live server. See [Commands](../administration/commands.md).

## Bridges

`Config.Bridge` decides which resource handles each system. See [Bridges](../developers/bridges.md).

## Chips

```lua
Config.Chips = {
    Mode = 'item',
    Item = 'casino_chips',
    Rate = 10,
    PlaqueMin = 1000,
}
```

| Key | Description |
| --- | ----------- |
| `Mode` | `item`: an inventory item, bought and sold at the cashier. `wallet`: a balance stored in the casino's own database, no item needed, works on any framework. `cash`: no chips, bets are taken straight from cash and the cashier is not used. |
| `Item` | The item name used in `item` mode. |
| `Rate` | What one chip costs. In `cash` mode one chip is worth `Rate` in cash. |
| `PlaqueMin` | Bets of this many chips or more are shown on the table as plaques. |

{% hint style="info" %}
The standalone framework has no money or inventory, so it only works with `wallet` mode. `item` mode needs an inventory bridge other than `none`. `casinoqa` checks both.
{% endhint %}

## Car key item

```lua
Config.KeyItem = 'carkey'
```

The item given with the lucky wheel car when `Config.Bridge.VehicleKeys = 'item'`. It gets `{ plate, label }` as metadata.

## UI colour

```lua
Config.Ui = { Accent = '#d6b25e' }
```

The accent colour of the casino UI.

## Admin

```lua
Config.Admin = {
    Command = 'casinoadmin',
    Ace = 'casino.admin',
    Groups = {
        god = { 'view', 'rig', 'economy', 'settings' },
        superadmin = { 'view', 'rig', 'economy', 'settings' },
        admin = { 'view', 'rig', 'economy', 'settings' },
    },
}
```

The command that opens the admin panel, and who may use it. See [Permissions](../administration/permissions.md).

## Rate limit

```lua
Config.RateLimit = { Calls = 12, Window = 1000 }
```

How many requests a player may send to one server function per `Window` milliseconds. Requests over the limit are dropped.
