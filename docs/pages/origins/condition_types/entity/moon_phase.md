[Entity Condition Type](https://origins.readthedocs.io/en/1.10.0/types/entity_condition_types/)

Checks for the world's current moon phase.

Type ID: `astral:moon_phase`

### Fields

| Field    | Type                                                                                                                    | Default    | Description                          |
| -------- | ----------------------------------------------------------------------------------------------------------------------- | ---------- | ------------------------------------ |
| `phase`  | [Moon Phase](../data_types/moon_phase.md)                                                                               | *optional* | If set, the moon phase to test for.  |
| `phases` | [Array](https://origins.readthedocs.io/en/1.10.0/types/data_types/array/) of [Moon Phases](../data_types/moon_phase.md) | *optional* | If set, the moon phases to test for. |

### Examples

```json
{
    "entity_condition": {
        "type": "astral:moon_phase",
        "phase": "waxing_gibbous"
    }
}
```

Checks whether the current moon phase is a waxing gibbous.

```json
{
    "entity_condition": {
        "type": "astral:moon_phase",
        "phases": [ "full_moon", "new_moon" ],
        "inverted": true
    }
}
```

Checks whether the current moon phase is *not* a full moon or new moon.
