Power Types are what grant functionality to your origins.
Each power has a type, specified with a `type` field in its JSON file. The power's type defines its supported and / or required fields.

Unless stated otherwise, each power type supports a `condition` field that can check for [Entity Condition Types](https://origins.readthedocs.io/en/1.10.0/types/entity_condition_types/).
See [Power JSON](https://origins.readthedocs.io/en/1.10.0/json/power/) for more details.

## Astral

### Regular Types

- [Ticking Cooldown](ticking_cooldown.md)

### Action Related

- [Action on Key](action_on_key.md)
- [Action on Spray](action_on_spray.md)
- [Action when Sprayed](action_when_sprayed.md)

### Modifying Types

- [Modify Scale](modify_scale.md)

### Preventing Types

*Nothing yet*

## Deprecated

???+ DANGER
    These types are deprecated and may be removed in future versions.
    It's recommended to not use any of the following entries unless absolutely necessary.

- [Scale](scale.md) (As of v1.7.0)
    - Succeeded by [Modify Scale](modify_scale.md)
