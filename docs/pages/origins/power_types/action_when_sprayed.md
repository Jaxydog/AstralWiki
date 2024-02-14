[Power Type](https://origins.readthedocs.io/en/1.10.0/types/power_types/)

Executes an action when sprayed by another entity.

This is the inverse of [Action on Spray](action_on_spray.md).

Type ID: `astral:action_on_spray`

???+ NOTE
    In this bi-entity context, the 'actor' is the entity holding the bottle, and the 'target' is the entity with the power.

### Fields

| Field                | Type                                                                                                 | Default    | Description                                                                                                                                    |
| -------------------- | ---------------------------------------------------------------------------------------------------- | ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| `priority`           | [Integer](https://origins.readthedocs.io/en/1.10.0/types/data_types/integer/)                        | `0`        | Affects the order that other Action on Spray powers are executed.                                                                              |
| `charges`            | [Integer](https://origins.readthedocs.io/en/1.10.0/types/data_types/integer/)                        | `1`        | Determines the number of charges consumed when the power is triggered. If multiple powers trigger on the same tick, the highest value is used. |
| `bientity_action`    | [Bi-entity Action Type](https://origins.readthedocs.io/en/1.10.0/types/bientity_action_types/)       |            | Executes a bi-entity action on the spraying entity when triggered.                                                                             |
| `bientity_condition` | [Bi-entity Condition Type](https://origins.readthedocs.io/en/1.10.0/types/bientity_condition_types/) | *optional* | If specified, the power will only trigger if the actor and target meet this condition.                                                         |
| `item_action`        | [Item Action Type]((https://origins.readthedocs.io/en/1.10.0/types/item_action_types/))              | *optional* | Executes an action on the held item stack when triggered.                                                                                      |
| `item_condition`     | [Item Condition Type](https://origins.readthedocs.io/en/1.10.0/types/item_condition_types/)          | *optional* | If specified, the power will only trigger if the spray item meets this condition.                                                              |

### Examples

```json
{
    "type": "astral:action_when_sprayed",
    "charges": 2,
    "bientity_action": {
        "type": "origins:add_velocity",
        "y": 0.125,
        "z": 0.5,
        "set": true
    },
    "bientity_condition": {
        "type": "origins:actor_condition",
        "condition": {
            "type": "origins:moving",
            "inverted": true
        }
    }
}
```

Consumes two charges from the bottle to knock the entity away from whatever is spraying it.

---

Added: v1.7.0, Last Updated: v1.7.0