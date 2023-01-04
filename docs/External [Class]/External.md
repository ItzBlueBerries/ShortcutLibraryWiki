# External

Some methods here have been used in Customizable Slime, interesting right?

### `StringToByte(string stringToParse)`

This method would convert a string to a byte. For example, stringed numbers.. to actual numbers?
Keep in mind that it separates them all with a `,` into an array.

- **Code Example**
```cs
using ShortcutLib;
External.StringToByte("255, 255, 255"); // White RGB
```

### `StringToFloat(string stringToParse)`

Same thing as the above method but instead it uses floats!

- **Code Example**
```cs
using ShortcutLib;
External.StringToFloat("255, 255, 255"); // White RGB but float? May not work on Color32.
```

Have fun with this one! Could be used in various ways, user & dev side.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.