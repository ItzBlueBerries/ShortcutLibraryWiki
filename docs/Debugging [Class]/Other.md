# Other Debugging

Continuing off of **[Logs](https://itzblueberries.github.io/ShortcutLibraryWiki/Debugging%20%5BClass%5D/Logs/)**, some other debugging methods!

### `Parent(GameObject obj, GameObject parent, bool worldPosition = true)`

This simply just parents an object, that's it. I'm not too sure what worldPosition does, maybe don't mess around with it but might do nothing!

- **Code Example**
```cs
using ShortcutLib;
Debugging.Parent(randomPrefab2, randomPrefab1); // Parenting randomPrefab2 to randomPrefab1
```

### `Position(GameObject obj, Vector3 position)`

This simply just positions an object, that's it. Yep. Use it if you'd like.

- **Code Example**
```cs
using ShortcutLib;
Debugging.Position(randomPrefab, new Vector3(0, 0, 0)); // Positioning randomPrefab at "0, 0, 0" using Vector3
```

Just some additional things that may or may not be useful sometimes.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.