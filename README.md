# Hills Network public assets

Public hosting for the Hills Network resource pack. Everything committed here is
world readable, so never put credentials, private config or unreleased content in
this repo.

## Contents

| File | Purpose |
|------|---------|
| `hills-texture-pack.zip` | The Hills Network resource pack |

## Client version support

`pack.mcmeta` carries a `supported_formats` range, which is what lets a single
pack load across many Minecraft versions:

```json
{
  "pack": {
    "pack_format": 0,
    "supported_formats": [0, 99],
    "description": ["", { "text": "Hills Network Pack", "color": "#e4890f" }]
  }
}
```

Clients on 1.20 and 1.20.1 came before `supported_formats` existed and read
`pack_format` on its own, so they still load the pack but label it as built for
a different version. Setting `pack_format` to `15` clears that warning on those
two versions, while the range keeps newer clients happy.
