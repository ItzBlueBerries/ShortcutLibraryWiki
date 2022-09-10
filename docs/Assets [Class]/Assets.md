# Assets

There seems to be only a few methods for this class, but can be useful.

### `LoadAsset(string imagePath)`

One of the very interesting things that ShortcutLib gives you is a way to load assets/images from outside your .dll file!
Its very simple to use, all you have to do is specify a path. It'll automatically link to the `Slime Rancher` game folder.

- **Code Example**
```cs
using ShortcutLib;
Assets.LoadAsset("ShortcutAssets\\images\\shortcutLibraryIcon.png");
```

The multiple `\` is important! Otherwise it may not work properly, besides using another way such as the `@`. Although I recommend `\\` as it is easy to manage.

This method is useful for mods that require assets to be modified from outside the .dll, excluding embedded resources or asset bundles. Although be careful with this as normal players can modify these files to their desire.

### `LoadBundle(string bundlePath)`

Similar to the `LoadAsset()` method, you can load Asset Bundles from outside your `.dll` file with this method. Might be useful in some cases!

- **Code Example**
```cs
using ShortcutLib;
Assets.LoadBundle("ShortcutAssets\\bundles\\shortcutBundle");
```

Pretty simple to use, just make sure an Asset Bundle exist in that directory! It also automatically links to the `Slime Rancher` game folder.

### `LoadResource<T>(string name)`

This method would search throughout the `Resources` folder of the game and load assets from there! Pretty cool right? Also probably less-file size consuming.

- **Code Example**
```cs
using ShortcutLib;
Assets.LoadResource<GameObject>("FX waterSplat");
```

Use it wisely, you don't wanna load something that might break your game.. really, there is no telling what's in there.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.