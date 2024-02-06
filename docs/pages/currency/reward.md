[Currency System](index.md)

Rewards are items given out as a result of players interacting with the currency system.
They hold no intrinsic value, yet they *are* exchanged as they can be combined into [Skeletons](skeleton.md).

File path: `<namespace>:currency/rewards.json`

???+ WARNING
    Setting a reward's weight to `0` or lower will prevent it from dropping.

### Format

#### File

| Field            | Type              | Default | Description                                                                                                                          |
| ---------------- | ----------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `namespace:path` | [Reward](#reward) |         | A reward entry. The field name must be a unique [Identifier](https://origins.readthedocs.io/en/1.10.0/types/data_types/identifier/). |

#### Reward

| Field    | Type                                                                                | Default | Description                                             |
| -------- | ----------------------------------------------------------------------------------- | ------- | ------------------------------------------------------- |
| `item`   | [Identifier](https://origins.readthedocs.io/en/1.10.0/types/data_types/identifier/) |         | The reward's associated item.                           |
| `weight` | [Integer](https://origins.readthedocs.io/en/1.10.0/types/data_types/integer/)       |         | The reward's weight, used to determine its drop chance. |

### Examples

```json
{
    "astral:cobblestone": {
        "item": "minecraft:cobblestone",
        "weight": 4
    },
    "astral:mossy_cobblestone": {
        "item": "minecraft:mossy_cobblestone",
        "weight": 1
    }
}
```

A reward system that uses cobblestone and mossy cobblestone as its items.
Cobblestone is 80% more likely to drop than mossy cobblestone.

---

Added: v1.2.0, Last Updated: v1.7.0