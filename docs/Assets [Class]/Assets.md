# Loading Outside Assets

One of the very interesting things that ShortcutLib gives you is a way to load assets/images from outside your .dll file!
Its very simple to use, all you have to do is specify a path. It'll automatically link to the `Slime Rancher` game folder.

- **Code Example**
```cs
using ShortcutLib;
Assets.LoadAsset("ShortcutAssets\\images\\shortcutLibraryIcon.png");
```

The multiple `\` is important! Otherwise it may not work properly, besides using another way such as the `@`. Although I recommend `\\` as it is easy to manage.

This method is useful for mods that require assets to be modified from outside the .dll, excluding embedded resources or asset bundles. Although be careful with this as normal players can modify these files to their desire.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.