[Power Type](https://origins.readthedocs.io/en/1.10.0/types/power_types/)

Executes an action when using any form of spray bottle on a block or entity.

Type ID: `astral:action_on_spray`

### Fields

| Field                | Type                                                                                                 | Default    | Description                                                                                                                                    |
| -------------------- | ---------------------------------------------------------------------------------------------------- | ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| `priority`           | [Integer](https://origins.readthedocs.io/en/1.10.0/types/data_types/integer/)                        | `0`        | Affects the order that other Action on Spray powers are executed.                                                                              |
| `charges`            | [Integer](https://origins.readthedocs.io/en/1.10.0/types/data_types/integer/)                        | `1`        | Determines the number of charges consumed when the power is triggered. If multiple powers trigger on the same tick, the highest value is used. |
| `item_action`        | [Item Action Type]((https://origins.readthedocs.io/en/1.10.0/types/item_action_types/))              | *optional* | Executes an action on the held item stack when triggered.                                                                                      |
| `item_condition`     | [Item Condition Type](https://origins.readthedocs.io/en/1.10.0/types/item_condition_types/)          | *optional* | If specified, the power will only trigger if the spray item meets this condition.                                                              |
| `bientity_action`    | [Bi-entity Action Type](https://origins.readthedocs.io/en/1.10.0/types/bientity_action_types/)       | *optional* | Executes a bi-entity action on the sprayed entity when triggered.                                                                              |
| `bientity_condition` | [Bi-entity Condition Type](https://origins.readthedocs.io/en/1.10.0/types/bientity_condition_types/) | *optional* | If specified, allows the player to spray any entity that meets this condition.                                                                 |
| `block_action`       | [Block Action Type]((https://origins.readthedocs.io/en/1.10.0/types/block_action_types/))            | *optional* | Executes a block action on the sprayed block when triggered.                                                                                   |
| `block_condition`    | [Block Condition Type](https://origins.readthedocs.io/en/1.10.0/types/block_condition_types/)        | *optional* | If specified, allows the player to spray any block that meets this condition.                                                                  |

### Examples

```json
{
    "type": "astral:action_on_spray",
    "charges": 2,
    "item_action": {
        "type": "origins:merge_nbt",
        "nbt": "{UsedPower:1b}"
    },
    "item_condition": {
        "type": "origins:nbt",
        "nbt": "{UsedPower:1b}",
        "inverted": true
    },
    "block_action": {
        "type": "origins:set_block",
        "block": "minecraft:mossy_cobblestone"
    },
    "block_condition": {
        "type": "origins:block",
        "block": "minecraft:cobblestone"
    }
}
```

Consumes two charges to convert cobblestone into mossy cobblestone once.

```json
{
    "type": "astral:action_on_spray",
    "charges": 8,
    "bientity_action": {
        "type": "origins:target_action",
        "action": {
            "type": "origins:if_else_list",
            "actions": [
                {
                    "condition": {
                        "type": "origins:nbt",
                        "nbt": "{Size:0}"
                    },
                    "action": {
                        "type": "origins:merge_nbt",
                        "nbt": "{Size:1}"
                    }
                },
                {
                    "condition": {
                        "type": "origins:nbt",
                        "nbt": "{Size:1}"
                    },
                    "action": {
                        "type": "origins:merge_nbt",
                        "nbt": "{Size:3}"
                    }
                }
            ]
        }
    },
    "bientity_condition": {
        "type": "origins:entity_type",
        "entity_type": "minecraft:slime"
    }
}
```

Consumes 8 charges to grow a slime to the next size up.

---

Added: v1.6.0, , Last Updated: v1.7.0