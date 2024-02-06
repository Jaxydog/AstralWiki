[Meta Condition Types](https://origins.readthedocs.io/en/1.10.0/types/meta_condition_types/) are used to modify other, more specific [Condition Types](https://origins.readthedocs.io/en/1.10.0/types/condition_types/).
While they can be used anywhere, the original (intended) condition type *is* preserved and is required to match.

For example, if you have a field which requires an [Entity Condition Type](https://origins.readthedocs.io/en/1.10.0/types/entity_condition_types/) and you instead provide an [And](https://origins.readthedocs.io/en/1.10.0/types/meta_condition_types/and/) meta condition,
all conditions included within the `conditions` array must either be another [Meta Condition Type](https://origins.readthedocs.io/en/1.10.0/types/meta_condition_types/), or the intended [Entity Condition Type](https://origins.readthedocs.io/en/1.10.0/types/entity_condition_types/).

### Astral

*Nothing yet*