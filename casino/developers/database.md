# Database

The tables are created and updated automatically through oxmysql. The current schema version is kept in `casino_schema`. The SQL files are in `sql/` if you need to run them by hand.

| Table | Contents |
| ----- | -------- |
| `casino_players` | One row per character: name, wallet balance, owed chips, wagered, won, rounds, biggest win, last wheel spin, ban flag and last seen. |
| `casino_games` | Totals per game: wagered, won, rounds and biggest win. |
| `casino_hourly` | Totals per game and hour, used for the charts in the admin panel. |
| `casino_rounds` | Single rounds for player history. Kept for `Config.Stats.RetentionDays` days. |
| `casino_state` | Saved state such as the house pool, the car fund and admin panel settings. |
| `casino_rigs` | Active rigs. |
| `casino_audit` | The admin audit log. |
| `casino_schema` | The schema version. |

## Owed chips

When chips can't be given to a player, for example because their inventory is full or they went offline, they are added to `owed` in `casino_players` and paid out automatically when the player is back.
