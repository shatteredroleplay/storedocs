# Rigging

Rigging lets admins steer outcomes for one player or for everyone. It needs the `rig` permission and is done from the **Rigging** and **Players** tabs of the admin panel.

## A rig

| Setting | Description |
| ------- | ----------- |
| Mode | `Off`, `Win` or `Lose`. |
| Chance | 1–100%: how often a round is steered. |
| Games | Which games it applies to: blackjack, roulette, baccarat, horse racing and slots. |
| Minutes | Optional: the rig ends after this many minutes. Leave empty for forever. |
| Until won / lost | Optional: the rig ends once the player has won or lost this many chips. |

A rig can be set on one player, or as a **global rig** that applies to every player without a rig of their own. Rigs are saved in the database and survive restarts.

## Lucky wheel

For a player you can also pick the prize their next lucky wheel spin lands on.

## How it works

When a rigged round is played, the casino rolls up to `Config.Rig.Tries` alternative outcomes to find one that matches the rig. Every steered outcome shows up in the live feed, which remembers the last `Config.Rig.Feed` entries.

Every rig that is set or cleared is written to the audit log and sent to the `rig` log category.

## Pool protection

Separate from rigs, the house quietly steers some outcomes when a win would hurt the pool. See [House pool](../configuration/economy.md#house-pool).
