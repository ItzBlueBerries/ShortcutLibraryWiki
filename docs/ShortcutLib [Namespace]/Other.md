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

### `CreateMeshObject(string objectName, Mesh objectMesh, Type colliderType, [Optional] Material meshMaterial, [Optional] Vector3 meshSize, bool usesSkinnedRenderer = false, bool hasDelaunchTrigger = true)`

Here is a bit more advanced as well! Creating Mesh Objects, this can be used for various things.

In this example, I'll be using it to attach a model to a plort.

*Note: MAKE SURE TO PUT THE EXACT NAME THAT IS IN THE ASSET BUNDLE, THANK YOU.*

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

GameObject randomPlortAttachment = Other.CreateMeshObject("plort_attachment", (Mesh)Other.LoadAsset(typeof(Mesh), randomAssetBundle, "plortAttachment"), typeof(SphereCollider), randomPlortMaterial);
randomPlortAttachment.transform.parent = randomPlort.transform;

// Want to add a bit of spin?
randomPlortAttachment.AddComponent<vp_Spin>(); // this makes it spin like dervish rings, not required

// Sometimes you have to size them down / up a bit, play around with this if it doesn't work first try.
randomPlortAttachment.transform.localScale *= 0.4f;
```

### `CreateChroma(Sprite chromaIcon, RanchDirector.Palette newPaletteID, string newPaletteName, Color[] darkColors, Color[] lightColors, ProgressDirector.ProgressType progressType = ProgressDirector.ProgressType.NONE, int partnerLevel = 0, int progressCount = 0, int order = 0)`

Okay, this is gonna be a bit of a long one but its cool! The way this method works is in a pretty specific way otherwise it'll give you an error.

Make sure that when you do this, you **DON'T** forget to have 8 colors in both of your color arrays. Anyways this method creates Chroma Packs.

*Note: Icon is not included, just to make sure you know. Also make sure to make your enum for it. (RanchDirector.Palette)*

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

Color[] darkColors = new Color[]
{
    Color.black,
    Color.black,
    Color.black,
    Color.black,
    Color.black,
    Color.black,
    Color.black,
    Color.black,
}

Color[] lightColors = new Color[]
{
    Color.white,
    Color.white,
    Color.white,
    Color.white,
    Color.white,
    Color.white,
    Color.white,
    Color.white,
}

Other.CreateChroma(randomChromaIcon, Enums.RANDOM_CHROMA, "Random Chroma", darkColors, lightColors);
```


### `CreateLiquid(Identifiable.Id liquidPrefab, Identifiable.Id newLiquidID, string liquidName, Texture2D colorRamp, Color liquidColor, Color vacColor, Sprite liquidIcon)`

This one is a bit.. I don't know. This most of this stuff should be known to you by now I'll explain the `Texture2D colorRamp` parameter.

This parameter basically just indicates the color of your liquid, extract an existing ramp maybe and modify that or make your own. Either way it should probably apply correctly.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

(LiquidDefinition, GameObject, Material) newLiquid = Other.CreateLiquid(
    Identifiable.Id.WATER_LIQUID, 
    Enums.NEW_LIQUID, 
    "New Liquid", 
    newLiquidRamp, 
    Color.grey, 
    Color.grey, 
    newLiquidIcon
);

// Modify how long it lasts on land if you want?
newLiquid.Item2.GetComponent<DestroyOnTouching>().hoursOfContactAllowed = float.PositiveInfinity;
```

### `CreateFountain(Identifiable.Id liquidObject, string fountainObject, string parent, string fountainName, Vector3 position, string dictionaryName)`

Ready for the liquid to come out of a fountain? Here's the method for you, I will note though this does involve positioning, parenting, etc.

*NOTE: Make sure to have a parent, position and if you want, fountainObject ready to use this.*

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

GameObject newFountain = Other.CreateFountain(
    Enums.NEW_LIQUID, 
    "zoneREEF/cellReef_Intro/Sector/Resources/waterFountain01", 
    "zoneREEF/cellReef_Intro/Sector/Resources/", 
    "NewFountain", 
    whatever_position_here, 
    "NewFountainDict"
);
```

### `ColorFountain(GameObject fountainObject, Color mainColor, Color mistColor, Color hitColor, Color dripsColor, Color waveColor, Color rippleColor, Color tinyDripsColor, Color glowColor, Color sparklesColor)`

The past method may create the fountain but it surely doesn't color it. Here is where you can do that, its simple really.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

Other.ColorFountain(newFountain, Color.grey, Color.grey, Color.grey, Color.grey, Color.grey, Color.grey, Color.grey, Color.grey, Color.grey); // lol I just put all grey, you don't have to though, this shall color it
```

Well that's all for over here, pretty useful stuff if you ask me.

Lets move on though!

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.