# BaumHome

My Home Assistant designs: the things I customize for my own home, packaged so anyone (including future me) can install them.

## Catalog

| Design | Type | What it does | Get it |
|---|---|---|---|
| **Remote Comfort** | Integration | HVAC control built around remote days, office days, sleep, the weather forecast, and zone balancing on a shared HVAC unit. | [ha-remote-comfort](https://github.com/Bruiserbaum/ha-remote-comfort) · [design notes](designs/remote-comfort.md) |

## Layout

```
blueprints/
  automation/   Blueprints, importable straight from GitHub
  script/
designs/        One page per design: the problem, the approach, my setup
```

**Blueprints** live here. To import one, open it on GitHub, copy the URL, and use *Settings → Automations & scenes → Blueprints → Import blueprint*.

**Integrations** each get their own repo (`ha-<name>`). HACS only allows one integration per repository, and a separate repo gives each one its own releases and issues. They're listed in the catalog above.

## Rule of thumb: blueprint or integration?

- **Blueprint:** a single trigger leads to an action, the only configuration is a few inputs, and there's no memory between runs.
- **Integration:** it needs state, lists of things (rooms, zones), its own entities and dashboard controls, or logic that's worth unit testing.

## Adding a design

1. Write `designs/<name>.md` covering the problem, what it does, and the hardware it assumes.
2. Build it, either as a blueprint in `blueprints/` or as a new `ha-<name>` repo using the same layout as `ha-remote-comfort`.
3. Add a row to the catalog.
