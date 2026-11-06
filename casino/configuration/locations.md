# Locations

File: `config/locations.lua`

The defaults are for the GTA Online casino interior. Table positions are set in each game's own file under `config/games/`.

```lua
Config.Locations = {
    Cashiers = {
        vec4(976.21, 37.26, 74.88, 90.44),
        vec4(1014.95, 62.46, 72.88, 226.40),
    },
    CashierModel = 'u_f_m_casinocash_01',
    CashierScenario = 'WORLD_HUMAN_STAND_IMPATIENT',

    Center = vec3(971.52, 39.12, 74.87),
    Range = 150.0,

    Zone = {
        vec2(1056.08, 78.57),
        vec2(985.16, -37.66),
        vec2(905.07, 11.08),
        vec2(1000.46, 114.65),
    },
    MinZ = 65.85,
    MaxZ = 81.09,
    Grace = 10,
}
```

| Key | Description |
| --- | ----------- |
| `Cashiers` | `vec4(x, y, z, heading)` of each cashier ped behind the counter. |
| `CashierModel` / `CashierScenario` | The ped model and the scenario it plays. |
| `Center` / `Range` | The middle of the casino. Nothing loads further away than `Range` metres from it. |
| `Zone` | The casino floor as an outline of `vec2(x, y)` points between `MinZ` and `MaxZ`. Tables, screens and sound only run inside it. Leave it empty to use the interior the tables stand in. |
| `Grace` | Seconds after leaving the zone that things stay loaded. |

{% hint style="info" %}
If you use an MLO or another casino interior, move the cashiers, the zone and every table, and check `Center` and `Radius` in `config/games/slots.lua` and `config/games/track.lua`.
{% endhint %}
