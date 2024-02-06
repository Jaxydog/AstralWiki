[Entity Condition Type](https://origins.readthedocs.io/en/1.10.0/types/entity_condition_types/)

Checks whether there are a specified number of blocks that both fulfill the specified block condition *and* are
unobstructed by any other blocks within a provided radius relative to the entity's feet.

Type ID: `astral:unobstructed_block_in_radius`

???+ WARNING
    Setting the `step_size` field to very small values (i.e. `0.0001`) may cause performance issues, especially if this condition is checked every tick.

### Fields

| Field             | Type                                                                                          | Default  | Description                                                                                                          |
| ----------------- | --------------------------------------------------------------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------- |
| `block_condition` | [Block Condition Type](https://origins.readthedocs.io/en/1.10.0/types/block_condition_types/) |          | The block condition to check for.                                                                                    |
| `radius`          | [Integer](https://origins.readthedocs.io/en/1.10.0/types/data_types/integer/)                 |          | The radius in which to check for possible blocks.                                                                    |
| `shape`           | [String](https://origins.readthedocs.io/en/1.10.0/types/data_types/string/)                   | `"cube"` | Determines the shape of the radius. Accepts `"cube"`, `"star"`, or `"sphere"`.                                       |
| `comparison`      | [Comparison](https://origins.readthedocs.io/en/1.10.0/types/data_types/comparison/)           | `">="`   | How the amount of blocks will be compared to the specified value.                                                    |
| `compare_to`      | [Integer](https://origins.readthedocs.io/en/1.10.0/types/data_types/integer/)                 | `1`      | The value to be compared against.                                                                                    |
| `step_size`       | [Float](https://origins.readthedocs.io/en/1.10.0/types/data_types/float/)                     | `0.125`  | The distance to move per-step of the obstruction checking raycast. Values less than or equal to `0` will be ignored. |

### Examples

```json
{
    "condition": {
        "type": "astral:unobstructed_block_in_radius",
        "radius": 5,
        "shape": "sphere",
        "block_condition": {
            "type": "origins:block",
            "block": "minecraft:glowstone"
        }
    }
}
```

Checks for a block of unobstructed glowstone within a 5-block sphere of the entity.

---

Added: v1.7.0, Last Updated: v1.7.0