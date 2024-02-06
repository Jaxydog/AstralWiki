[Currency System](index.md)

Units are items that hold a value, and as such are the heart of the system.
These items *are* exchanged, and have the option of providing randomly generated reward items whilst exchanging.

File path: `<namespace>:currency/units.json`

???+ WARNING
    Unit recursion is unchecked, so it's possible to create items that automatically exchange into each other.
    It's highly recommended to avoid creating units that have equal values, as this could cause the items to swap every tick.

### Format

#### File

| Field            | Type          | Default | Description                                                                                                                        |
| ---------------- | ------------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `namespace:path` | [Unit](#unit) |         | A unit entry. The field name must be a unique [Identifier](https://origins.readthedocs.io/en/1.10.0/types/data_types/identifier/). |

#### Unit

| Field       | Type                                                                                | Default    | Description                                                              |
| ----------- | ----------------------------------------------------------------------------------- | ---------- | ------------------------------------------------------------------------ |
| `item`      | [Identifier](https://origins.readthedocs.io/en/1.10.0/types/data_types/identifier/) |            | The unit's associated item.                                              |
| `value`     | [Integer](https://origins.readthedocs.io/en/1.10.0/types/data_types/integer/)       |            | The unit's value.                                                        |
| `drops`     | [Boolean](https://origins.readthedocs.io/en/1.10.0/types/data_types/boolean/)       | `false`    | Whether this unit drops rewards.                                         |
| `exchanges` | [Object](https://origins.readthedocs.io/en/1.10.0/types/data_types/object/)         | *optional* | Controls cross-exchange rates for currency systems from other datapacks. |

#### Exchanges

| Field       | Type                                                                          | Default | Description                                                                                      |
| ----------- | ----------------------------------------------------------------------------- | ------- | ------------------------------------------------------------------------------------------------ |
| `namespace` | [Integer](https://origins.readthedocs.io/en/1.10.0/types/data_types/integer/) |         | The unit's value in the system defined by a datapack whose namespace is equal to the field name. |

### Examples

```json
{
    "astral:stick": {
        "item": "minecraft:stick",
        "value": 1
    },
    "astral:wood": {
        "item": "minecraft:oak_planks",
        "value": 4
    },
    "astral:log": {
        "item": "minecraft:oak_log",
        "value": 16,
        "drops": true
    }
}
```

A currency system that uses sticks, planks, and logs as its items. Rewards will be dropped when exchanging into logs.

---

Added: v1.2.0, Last Updated: v1.7.0