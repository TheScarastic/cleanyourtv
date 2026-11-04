# My MiTV-AXSO1 setup

Personal choices for my own TV, kept apart from anything meant for upstream. Nothing here is a recommendation.

- `launcher/app/src/main/res/values/config.xml`: compiled defaults, with BetterNVR first in the dock, five columns.
- `launcher-config/config.json`: runtime settings on top of those, with no launcher rebuild.
- `debloat-axso1.txt`: the packages I chose to disable on this TV.

BetterNVR's own code lives in its own repository, not here.

Apply the runtime settings, then the list, from the repository root:

```powershell
.\tools\theme.ps1 -TvHost <tv ip>:5555 -Theme "$PWD\personal\mitv-axso1\launcher-config"
.\tools\disable.ps1 -TvHost <tv ip>:5555 personal\mitv-axso1\debloat-axso1.txt
```

A theme push resets saved appearance and layout choices. Undo the list with `tools\restore.ps1` and the same arguments.
