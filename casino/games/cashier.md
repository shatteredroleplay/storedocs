# Cashier

Players buy and sell chips at the cashier peds. One chip costs `Config.Chips.Rate` in money.

* Positions and the ped model are set in `config/locations.lua` (see [Locations](../configuration/locations.md)).
* Whether money is taken from cash or bank, and the most that can be exchanged at once, are set in `Config.Cashier` (see [Economy](../configuration/economy.md#cashier)).
* The cashier is only used in `item` and `wallet` chip mode. In `cash` mode bets are taken straight from cash.

If chips can't be given to a player, for example because their inventory is full, they are stored as owed and paid out automatically when the player is back.
