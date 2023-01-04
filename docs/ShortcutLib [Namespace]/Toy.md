# Toy

To be honest, this class doesn't have much on creating toys. It can create basic ones but the rest may be up to you if anything.

So here you are the 2 methods this class has.

### `GetToyDef(Identifiable.Id toyId)`

Just gets a toy definition, they use special ones. Here is a code example.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

ToyDefinition someToyDef = Toy.GetToyDef(Identifiable.Id.BEACH_BALL_TOY); // Gets the Beach Ball Toy definition
```

### `CreateToy(Identifiable.Id toyPrefab, Identifiable.Id newToyID, string newToyName, Sprite newToyIcon, Material toyMaterial, int toyCost = 500, Vacuumable.Size vacSetting = Vacuumable.Size.LARGE, bool isUpgradableToy = true)`

This may be a bit more interesting, you can create toys with this. It may not be much but toys aren't much really, any other editing is done outside of the method.

*NOTE: Make sure to add an icon for your toy & material.*

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

GameObject newToyObject = Toy.CreateToy(Identifiable.Id.BEACH_BALL_TOY, Enums.NEW_TOY, "New Toy", newToyIcon, newToyMaterial, 100); // Creates a toy that cost 100 newbucks, also upgradable.
```

And that's all for here, have fun with that if you want.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.