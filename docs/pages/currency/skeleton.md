[Currency System](index.md)

Skeletons, named after the initial concept for the currency system, simply act as trophies.
They hold no value, and *are not* exchanged. Their sole purpose is as feedback for using the system.

File path: `<namespace>:currency/skeletons.json`

### Format

#### File

| Field            | Type                  | Default | Description                                                                                                                            |
| ---------------- | --------------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| `namespace:path` | [Skeleton](#skeleton) |         | A skeleton entry. The field name must be a unique [Identifier](https://origins.readthedocs.io/en/1.10.0/types/data_types/identifier/). |

#### Skeleton

| Field  | Type                                                                                                                                                                   | Default | Description                                                                                                          |
| ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- | -------------------------------------------------------------------------------------------------------------------- |
| `item` | [Identifier](https://origins.readthedocs.io/en/1.10.0/types/data_types/identifier/)                                                                                    |         | The skeleton's associated item.                                                                                      |
| `cost` | [Array](https://origins.readthedocs.io/en/1.10.0/types/data_types/identifier/) of [Identifiers](https://origins.readthedocs.io/en/1.10.0/types/data_types/identifier/) |         | The skeleton's reward cost, used for exchanging. Each identifier should be a valid defined [Reward](reward.md) item. |

### Examples

```json
{
    "astral:stone": {
        "item": "minecraft:stone",
        "cost": [
            "astral:cobblestone",
            "astral:cobblestone",
            "astral:cobblestone",
            "astral:cobblestone"
        ]
    },
    "astral:stone_bricks": {
        "item": "minecraft:stone_bricks",
        "cost": [
            "astral:cobblestone",
            "astral:cobblestone",
            "astral:mossy_cobblestone",
            "astral:mossy_cobblestone"
        ]
    },
    "astral:mossy_stone_bricks": {
        "item": "minecraft:mossy_stone_bricks",
        "cost": [
            "astral:mossy_cobblestone",
            "astral:mossy_cobblestone",
            "astral:mossy_cobblestone",
            "astral:mossy_cobblestone"
        ]
    }
}
```

A skeleton system that uses cobblestone and mossy cobblestone to craft stone, stone bricks, and mossy stone bricks.

---

Added: v1.2.0, Last Updated: v1.7.0