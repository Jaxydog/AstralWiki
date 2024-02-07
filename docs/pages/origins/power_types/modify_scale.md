[Power Type](https://origins.readthedocs.io/en/1.10.0/types/power_types/)

Applies modifiers to an entity's scaling using Pehkui.

Type ID: `astral:modify_scale`

### Fields

| Field           | Type                                                                                                                                                                             | Default    | Description                                                                                               |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------------------------------------------------------------------------------------------------- |
| `scale_types`   | [Array](https://origins.readthedocs.io/en/1.10.0/types/data_types/array/) of [Identifiers](https://origins.readthedocs.io/en/1.10.0/types/data_types/identifier/)                |            | A list of identifiers that determine what values to scale. These should be valid, registered scale types. |
| `transition`    | [Integer](https://origins.readthedocs.io/en/1.10.0/types/data_types/integer/)                                                                                                    | `0`        | The duration in ticks that it takes to transition between scales.                                         |
| `tick_rate`     | [Integer](https://origins.readthedocs.io/en/1.10.0/types/data_types/integer/)                                                                                                    | `1`        | The interval in ticks between condition updates.                                                          |
| `reset_on_loss` | [Boolean](https://origins.readthedocs.io/en/1.10.0/types/data_types/boolean/)                                                                                                    | `true`     | Whether to reset all modified scales back to `1.0` when the power is removed or disabled.                 |
| `modifier`      | [Attribute Modifier](https://origins.readthedocs.io/en/1.10.0/types/data_types/attribute_modifier/)                                                                              | *optional* | A scale modifier.                                                                                         |
| `modifiers`     | [Array](https://origins.readthedocs.io/en/1.10.0/types/data_types/array/) of [Attribute Modifier](https://origins.readthedocs.io/en/1.10.0/types/data_types/attribute_modifier/) | *optional* | A list of scale modifiers.                                                                                |

### Examples

```json
{
    "type": "astral:modify_scale",
    "scale_types": [ "pehkui:width", "pehkui:height" ],
    "modifier": {
        "operation": "multiply_total",
        "value": -0.5
    }
}
```

Halves the entity's width and height scales.

```json
{
    "type": "origins:multiple",
    "squash": {
        "type": "astral:modify_scale",
        "scale_types": [ "pehkui:width", "pehkui:height", "pehkui:reach" ],
        "transition": 5,
        "reset_on_loss": false,
        "modifier": {
            "operation": "multiply_total",
            "value": -0.5
        },
        "condition": {
            "type": "origins:sneaking"
        }
    },
    "stretch": {
        "type": "astral:modify_scale",
        "scale_types": [ "pehkui:width", "pehkui:height", "pehkui:reach" ],
        "transition": 5,
        "reset_on_loss": false,
        "modifier": {
            "operation": "multiply_total",
            "value": 0.5
        },
        "condition": {
            "type": "origins:sneaking",
            "inverted": true
        }
    }
}

```

Decreases the entity's width, height, and reach by 50% while they are sneaking, and increases it by 50% while not sneaking.

---

Added: v1.7.0, Last Updated: v1.7.0
