# Sizes

The Presets Namespace is simply just a namespace that has preset things. There are preset-sizes, preset-cells and maybe some random generating.

Here is the list of variables provided in the `Sizes` class within the Presets Namespace.

```cs
public static readonly Vector3 DEFAULT_SIZE = new Vector3(1f, 1f, 1f);

public static readonly Vector3 POGOFRUIT_SIZE = new Vector3(0.25f, 0.25f, 0.25f);

public static readonly Vector3 CARROT_SIZE = new Vector3(2.0f, 2.0f, 2.0f);

public static readonly Vacuumable.Size VAC_N = Vacuumable.Size.NORMAL;

public static readonly Vacuumable.Size VAC_L = Vacuumable.Size.LARGE;

public static readonly Vacuumable.Size VAC_G = Vacuumable.Size.GIANT;
```

This is indeed how the code looks like from within the library, but why not give you the insides of it? See what its returning.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.