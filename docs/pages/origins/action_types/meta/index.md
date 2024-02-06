[Meta Action Types](https://origins.readthedocs.io/en/1.10.0/types/meta_action_types/) are used to modify other, more specific [Action Types](https://origins.readthedocs.io/en/1.10.0/types/action_types/).
While they can be used anywhere, the original (intended) action type *is* preserved and is required to match.

For example, if you have a field which requires an [Entity Action Type](https://origins.readthedocs.io/en/1.10.0/types/entity_action_types/) and you instead provide an [And](https://origins.readthedocs.io/en/1.10.0/types/meta_action_types/and/) meta action,
all actions included within the `actions` array must either be another [Meta Action Type](https://origins.readthedocs.io/en/1.10.0/types/meta_action_types/), or the intended [Entity Action Type](https://origins.readthedocs.io/en/1.10.0/types/entity_action_types/).

### Astral

- [Repeat](repeat.md)