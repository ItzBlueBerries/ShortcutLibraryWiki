# Rands

Its similar to the other classes, but instead it has randomly generated variables/methods. Not exactly needed all the time, but may be useful at times.

```cs
public static readonly Identifiable.Id RAND_SLIME = Identifiable.SLIME_CLASS.GetRandom();
public static readonly Identifiable.Id RAND_LARGO = Identifiable.LARGO_CLASS.GetRandom();
public static readonly double RAND_DOUBLE = new System.Random().NextDouble();
```

That's just the variables, there is also a method in this class which generates a random `int`.

### `RAND_INT(int min = int.MinValue, int max = int.MaxValue)`

- **Code Example**
```cs
Debugging.Log(Rands.RAND_INT(0, 1));
```

That would log an int in-between `0` and `1`. There is also another method being used here. `Debugging.Log()` is from the [Debugging Class](https://itzblueberries.github.io/ShortcutLibraryWiki/Debugging%20%5BClass%5D/Logs/#logstring-tolog-bool-logtofile-true-bool-isinfo-true-bool-iserror-false-bool-issuccess-false). You can go check that out if you want.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.