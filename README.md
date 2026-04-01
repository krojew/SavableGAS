# SaveableGAS

SaveableGAS provides a UAbilitySystemComponent subclass that can snapshot active duration Gameplay Effects (including periodic timing state) into a portable struct and restore them later. Intended to work with any save game system.

Supports saving attributes and gameplay effects, including eliminating possible double application. Only `Has Duration` effects (including those with infinite duration) are saved, because instant and infinite are assumed to be applied by the game logic.

## Usage

1. Replace `UAbilitySystemComponent` you use with `USaveableAbilitySystemComponent`.
2. In order to save whole state call `SaveState()` which populates a `FAbilitySystemSaveData` struct.
3. Save this struct in a save game system of your chosing.
4. To restore, pass it to the `RestoreState()` method.
