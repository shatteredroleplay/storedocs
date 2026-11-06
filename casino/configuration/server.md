# Server settings and logs

File: `config/server.lua`

This file is only loaded on the server and never sent to players. Keep secrets here.

## Society account

```lua
ServerConfig.Society = {
    Account = 'casino',
}
```

Where the house income is paid when `Config.Bridge.Society` is set.

| Society | Account |
| ------- | ------- |
| `esx` | The addon account, usually `society_casino` |
| `qb`, `renewed`, `okok` | The job or society account name, usually `casino` |

See [House income](economy.md#house-income).

## Logs

Set `Config.Bridge.Logs` in `config/main.lua` to `discord`, `fivemanage`, `shattered` or `custom`.

```lua
ServerConfig.Logs = {
    Discord = {
        Default = '',
        Webhooks = {
            admin = '',
            rig = '',
            economy = '',
            bigwin = '',
        },
        Name = 'Casino',
        Color = 14070366,
    },
    Fivemanage = {
        Token = '',
        Dataset = 'casino',
    },
}
```

There are four log categories:

| Category | What is logged |
| -------- | -------------- |
| `admin` | Admin panel actions such as settings, bans and chip changes |
| `rig` | Rigs being set and cleared |
| `economy` | Pool, car fund and protection changes |
| `bigwin` | Wins of at least `Config.Stats.BigWin` |

Categories without their own webhook use `Default`.
