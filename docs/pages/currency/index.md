Astral provides a data-driven currency system that rewards players for interaction.

### Implementation

Items within the system are separated into three categories: [Units](#units), [Rewards](#rewards), and [Skeletons](#skeletons).

#### Units

Units are items that hold a value, and as such are the heart of the system.
These items *are* exchanged, and have the option of providing randomly generated reward items whilst exchanging.

#### Rewards

Rewards are items given out as a result of players interacting with the currency system.
They hold no intrinsic value, yet they *are* exchanged as they can be combined into [Skeletons](#skeletons).

#### Skeletons

Skeletons, named after the initial concept for the currency system, simply act as trophies.
They hold no value, and *are not* exchanged. Their sole purpose is as feedback for using the system.

### Exchanging

The most notable feature of the currency system is that items are automatically combined into their higher-value counterparts.
Items of lesser value will attempt to combine into items of greater value, with the following conditions:

- The item must not have been used within a crafting recipe. This was added to prevent abuse of the reward system, and means that it's generally a bad idea to use items that aren't modded within your setup as this is tracked via NBT.
- The greater value must be an exact multiple of the lesser value. A conversion of two 4-cost items into one 6-cost item would not be possible.
- As of v1.7.0, units must either be within the same namespace, or provide an exchange mapping to convert into another namespace.

### Data Formats

- [Units](unit.md)
- [Rewards](reward.md)
- [Skeletons](skeleton.md)

### Internals

Whether an item may be exchanged is controlled via the `Exchange` NBT key.
If this flag is set to `0b`, items are not allowed to be exchanged.

Whilst exchanging units, the next unit will always be of the least possible value while still increasing and being an exact multiple.

If a value's associated item has not been registered, the value will be ignored.

???+ WARNING
    While it is possible for multiple items to have the same currency representation, doing so will cause conflicts between systems where the exchanging system will only ever choose one of the definitions.

    To avoid this, you are encouraged to use custom modded items instead of relying on vanilla content.

???+ BUG
    Currently, there is no check for empty lists within reward exchanging.
    If a skeleton's cost list is empty, it will cause an infinite loop and cause the game to hang.

    This issue will be fixed in v1.7.0.

???+ BUG
    Currently, currency values are exchanged regardless of namespace.
    This will cause issues when multiple sources define units of equal or conflicting value.

    This issue will be fixed in v1.7.0 when the `exchanges` field is introduced.
