# Permissions

The admin panel has four parts:

| Permission | Gives access to |
| ---------- | --------------- |
| `view` | Viewing the dashboard, games, players and audit log |
| `rig` | Rigging players and the lucky wheel |
| `economy` | The house pool, car fund and protection, giving or taking chips, resetting a wheel cooldown, and casino bans |
| `settings` | Opening and closing games, the wheel cooldown and table limits |

Access is given by ACE or by framework group.

## ACE

Everything:

```
add_ace group.admin casino.admin allow
```

One part only:

```
add_ace group.mod casino.admin.view allow
```

The base name `casino.admin` is set by `Config.Admin.Ace`.

## Framework groups

`Config.Admin.Groups` lists framework groups and the parts of the panel they get without any ACE:

```lua
Groups = {
    god = { 'view', 'rig', 'economy', 'settings' },
    superadmin = { 'view', 'rig', 'economy', 'settings' },
    admin = { 'view', 'rig', 'economy', 'settings' },
},
```

{% hint style="info" %}
On qbx, ox, nd and standalone a group is an ACE group, so `admin` means `group.admin`.
{% endhint %}

The server console always has every permission.
