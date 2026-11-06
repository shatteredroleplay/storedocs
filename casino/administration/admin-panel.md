# Admin panel

Open it in game with `/casinoadmin` (the command is set by `Config.Admin.Command`). Only players with at least one admin permission can open it. See [Permissions](permissions.md).

## Dashboard

Profit today, this week and this month, the RTP of the month (the share of bets paid out), the players inside right now, the house pool, the current max bet, the car fund, table occupancy, the biggest wins and a live feed of big wins and admin actions.

## Games

Per game: wagered, paid out, house profit, RTP, rounds, profit and wagered per day, and the biggest win.

## Players

Search for any player, see who is online and the top winners. For one player you can:

* see their net result and round history
* give or take chips (online players only)
* reset their lucky wheel cooldown
* ban or unban them from the casino
* rig them, or pick their next lucky wheel prize (see [Rigging](rigging.md))

## Rigging

Set a global rig for everyone, see the active rigs and the live feed of steered outcomes, and clear all rigs at once. See [Rigging](rigging.md).

## Economy

* Set the house pool and see what it is worth and the current max bet.
* See and set the car fund for the lucky wheel car.
* See the house income mode and any income still waiting to be paid.
* Change the pool protection (bias, curve and high roller settings) live.

See [Economy](../configuration/economy.md).

## Settings

* Open or close each game.
* Set the lucky wheel cooldown in hours.
* Change the min and max of each table, or reset them to the config value.

These are saved in the database and override the config files.

## Audit log

Every admin action with time, admin, action, target and details, 50 rows per page.
