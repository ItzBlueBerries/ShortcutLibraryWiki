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

By the way, if you want to be able to load icons via your own mod DLL, I'll give you the code below but no examples.

```cs
public static Texture2D LoadImage(string filename)
{
    var a = Assembly.GetExecutingAssembly();
    var spriteData = a.GetManifestResourceStream(a.GetName().Name + "." + filename);
    var rawData = new byte[spriteData.Length];
    spriteData.Read(rawData, 0, rawData.Length);
    var tex = new Texture2D(1, 1);
    tex.LoadImage(rawData);
    tex.filterMode = FilterMode.Bilinear;
    return tex;
}

public static Sprite CreateSprite(Texture2D texture) => Sprite.Create(texture, new Rect(0, 0, texture.width, texture.height), new Vector2(0.5f, 0.5f), 1);
```

When loading sprites, use `CreateSprite(LoadImage())`. If not and just Texture2D, simply use `LoadImage()` only. Make sure to give your specified path.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.