# Installation

## 1. Add the resource

1. Put the `casino` folder in your `resources` folder.
2. Make sure `oxmysql` starts before it.
3. Add it to your `server.cfg`:

```
ensure oxmysql
ensure casino
```

The resource name is used as the prefix of every event (`casino:...`) and for exports (`exports.casino`). If you rename the folder, the prefix changes with it.

## 2. Database

The tables are created automatically on the first start. The resource keeps its own schema version in the `casino_schema` table and runs any new migration from `sql/` when you update.

If the automatic setup fails, the console prints `database setup failed`. Run `sql/install.sql` and then `sql/002_owed.sql` by hand, and restart the resource.

See [Database](developers/database.md) for a list of the tables.

## 3. Pick your systems

Open `config/main.lua` and set `Config.Bridge` to the framework, inventory, target and notify resources you use. `'auto'` picks the first supported one that is running.

```lua
Config.Bridge = {
    Framework = 'qbx',
    Inventory = 'ox',
    Target = 'ox',
    Notify = 'ox',
    VehicleKeys = 'none',
    Society = 'none',
    Logs = 'none',
}
```

See [Bridges](developers/bridges.md) for every supported value.

## 4. Chips

By default chips are the inventory item `casino_chips` (`Config.Chips.Mode = 'item'`). Add that item to your inventory if it does not exist yet. If you do not want an item, use `wallet` or `cash` mode instead. See [Main settings](configuration/main.md#chips).

## 5. Lucky wheel prizes

The default wheel gives the items `gold_ring`, `repair_kit`, `diamond_ring` and `diamond_necklace`. Make sure they exist in your inventory, or change the prizes in `config/games/wheel.lua`. See [Lucky wheel](games/lucky-wheel.md).

## 6. Admin access

Give your staff access to the admin panel with an ACE, for example:

```
add_ace group.admin casino.admin allow
```

See [Permissions](administration/permissions.md).

## 7. Check the setup

Start the server and run `casinoqa` in the server console. It checks the database, every bridge and the chip mode, and prints `PASS` or `FAIL` for each check. Add a player's server id (`casinoqa 1`) to also test their money, chips and permissions.

See [Commands](administration/commands.md) and [Troubleshooting](troubleshooting.md).
