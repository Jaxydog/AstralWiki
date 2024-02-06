[Power Type](https://origins.readthedocs.io/en/1.10.0/types/power_types/)

Modifies the scale(s) of an entity using Pehkui.

Type ID: `astral:scale`

???+ DANGER
    This power type is being deprecated and will be removed in a future version.


### Fields

| Field           | Type                                                                          | Default            | Description                                                                                        |
| --------------- | ----------------------------------------------------------------------------- | ------------------ | -------------------------------------------------------------------------------------------------- |
| `width`         | [Float](https://origins.readthedocs.io/en/1.10.0/types/data_types/float/)     | `1.0`              | The entity's model width scale.                                                                    |
| `height`        | [Float](https://origins.readthedocs.io/en/1.10.0/types/data_types/float/)     | `1.0`              | The entity's model height scale.                                                                   |
| `reach`         | [Float](https://origins.readthedocs.io/en/1.10.0/types/data_types/float/)     | `1.0`              | The entity's reach scale.                                                                          |
| `motion`        | [Float](https://origins.readthedocs.io/en/1.10.0/types/data_types/float/)     | `1.0`              | The entity's motion scale.                                                                         |
| `jump`          | [Float](https://origins.readthedocs.io/en/1.10.0/types/data_types/float/)     | `1.0`              | The entity's jump scale.                                                                           |
| `reset_on_lost` | [Boolean](https://origins.readthedocs.io/en/1.10.0/types/data_types/boolean/) | `false`            | Whether to reset all modified scales back to `0.0` when the power is "lost" (removed or disabled). |
| `operation`     | [Scale Operation](../data_types/scale_operation.md)                           | `"multiplicative"` | The operation with which to scale.                                                                 |

### Examples

```json
{
    "type": "astral:scale",
    "width": 1.5,
    "height": 1.5,
    "reach": 1.25
}
```

Sets the entity's width and height to 1.5x their initial value, and their reach to 1.25x the initial value. For players,
they will be 3 blocks tall and will be able to reach up to around 4.5 blocks away.

```json
{
    "type": "astral:scale",
    "reach": -0.5,
    "operation": "additive",
    "reset_on_lost": true,
    "condition": {
        "type": "origins:sneaking"
    }
}
```

Decreases the entity's reach by 50% while they are sneaking, resetting back to default when the condition is false.
