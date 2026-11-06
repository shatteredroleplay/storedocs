# Troubleshooting

Start with `casinoqa` in the server console, or `casinoqa <server id>` with a player online. Every check prints `PASS` or `FAIL`.

## The database is not set up

The console says `database setup failed`. Run `sql/install.sql` and then `sql/002_owed.sql` by hand, and restart the resource. Check that `oxmysql` starts before the casino.

## A bridge is not usable

The console says an adapter `is selected but ... is not running`, `does not exist` or `is missing ...`.

* Check that the resource set in `Config.Bridge` is running and starts before the casino.
* Use `'auto'` to let the casino pick what is running.
* For a `custom` bridge, fill in every function the console lists.

See [Bridges](developers/bridges.md).

## Players get no chips at the cashier

* In `item` mode the item from `Config.Chips.Item` (default `casino_chips`) must exist in your inventory, and the inventory bridge must not be `none`.
* With the standalone framework, use `Config.Chips.Mode = 'wallet'`.
* Chips that did not fit are paid out automatically when the player has room.

## The tables or screens don't load

Everything only runs inside the casino zone. If you use another interior or an MLO, update `Zone`, `Center` and `Range` in `config/locations.lua`. See [Locations](configuration/locations.md).

## The crowd sound is silent

Some resources mute the world with audio scenes, which can block streamed sound. Set `Config.Atmosphere.MuteEvent` to an event that turns that off while inside the casino.

## The wheel car is not stored

The car is stored through the framework bridge. On qbx this needs `qbx_vehicles` to be running. Check that `Car.Garage` in `config/games/wheel.lua` is a garage your garage resource knows.

## I can't open the admin panel

Check that you have an ACE such as `casino.admin` or a group listed in `Config.Admin.Groups`. `casinoqa <your server id>` lists the admin permissions you have. See [Permissions](administration/permissions.md).
