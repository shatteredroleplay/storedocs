# Slots

Every GTA casino slot machine prop can be sat at and plays one of ten slot games. Players switch game on the machine itself.

File: `config/games/slots.lua`

## The games

| Game | Key | Type | RTP | Bonus |
| ---- | --- | ---- | --- | ----- |
| Valhalla | `holmgang` | 15 lines, duel wheels up to ×100 | 97% | The Raid |
| Wilderness | `vildmark` | 20 lines, bonus wheel with seven bonuses | 97% | The bonus wheel |
| U-Boat | `ubaten` | 576 ways, wild crates, nudging wilds and depth charges | 97% | Free spins |
| Midnight Munchies | `fyllekak` | Cluster pays, gold cells, rainbows and coins | 97% | Free spins |
| Pharaoh | `farao` | 10 lines, expanding symbols | 97% | The Tomb |
| Olympus | `olympen` | Pays anywhere, orbs up to ×500 | 95% | Wrath of the Gods |
| Duck Season | `andjakt` | Pays anywhere, multipliers up to ×16,384 | 97% | Duck Hunt |
| Ronin | `ronin` | Tile stacks, up to 100,000 ways | 97% | Stacked Spins |
| The Mine | `gruvan` | Endless reels, every win digs deeper | 97% | The Deep Shaft |
| Brass Knuckles | `jarnnave` | 14 lines, fists punch in multipliers up to ×200 | 96.3% | Brawl! |

Names, taglines and bonus texts are in the locales (`slots.<game>.*`). `Order` sets the order the games are listed in.

## Playing

* **← →** browse the games, **E** plays, **X** closes the menu. The mouse works too.
* **H** buys free spins and **G** turns on bonus hunt, on the games that have them.

## Settings

| Key | Default | Description |
| --- | ------- | ----------- |
| `Center` / `Radius` | `vec3(1000.0, 55.0, 72.0)` / `90.0` | Machines further than `Radius` from `Center` can't be played. |
| `Bets` | `{ 5, 10, 25, 50 }` | The bets a player scrolls through, in chips. |
| `MaxWin` | `5000` | A round stops paying once it has paid this many times the bet. |
| `Rig` | `0.05` | Chance a winning round is spun again. Pulls the real RTP a little under the games' own. |
| `Volume` | | Sound of your own machine, and of other machines within `Range` metres. |
| `Time` | | How long every animation plays, in milliseconds. The screen and the server use the same numbers. |
| `Watch` | `{ Max = 2, Scale = 0.4 }` | At most `Max` machines of other players are shown playing, at `Scale` of full size. |
| `Machines` | | The slot props that can be played and where their screen is. |
| `Games` | | The maths of every game. |

{% hint style="warning" %}
`rtp` in `Games` is what each game pays back over time. Only change weights and pays if you can re-check the RTP afterwards, or the games may pay far more or less than intended.
{% endhint %}
