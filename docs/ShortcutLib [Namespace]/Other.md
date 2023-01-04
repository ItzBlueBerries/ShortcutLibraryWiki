# Other

Oh this is gonna be a bit of a longer one, it has things for creating fountains, loading assets, etc.

### `LoadAsset(Type assetType, AssetBundle assetBundle, string assetName)`

This is simply for loading assets from an existing asset bundle, as seen in the example.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;
Other.LoadAsset(typeof(Mesh), testAssetBundle, "testMesh"); // Loading a mesh that is stored in the testAssetBundle
```

### `LoadHex(string hexCode)`

All this does is transform a hex code into an actual color, you still need the `#` in front.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;
Color whiteColor = Other.LoadHex("#FFFFFF"); // Loads the white hex code
```

