# Style

In this class its all about creating secret styles for your slime!
Please know that these methods may not function properly if you do not have Secret Styles purchased and installed.

### `CreateCosmetic(string podIDName, string podObject, string podParent, Vector3 podPosition, SlimeAppearance unlockableAppearance, SlimeDefinition unlockableDefinition, [Optional] Quaternion podRotation, bool keepOriginalName = true)`

This is a bit more advanced in some areas but its how you create your cosmetic pod then assign your `SlimeAppearance` and `SlimeDefinition` to it.
Here is an example below, it may be a bit harder to grasp though if you don't have much experience with `C#` which is definitely recommended you do.

*Note: don't put "whatever_position_here" put an actual position. Same for an actual style appearance with "secretStyleAppearance".*

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

Style.CreateCosmetic("TestSlimeCosmetic", "zoneREEF/cellReef_GordoIsland/Sector/Loot/treasurePodCosmetic", "zoneREEF/cellReef_GordoIsland/Sector/Loot/", whatever_position_here, secretStyleAppearance, Slime.GetSlimeDef(Enums.TEST_SLIME)); // Creates a cosmetic pod by cloning one, parenting it to a new area (or as you may would), positioning it, giving it an appearance & definition to work with. Look down below on how to create a style appearance
```

### `CreateStyleAppearance(Identifiable.Id slimePrefab, SlimeDefinition slimeDefinition, string styleName)`

This one is a bit shorter, its for creating the styled appearance! Why do this instead of just making a new SlimeAppearance? Because it does things for secret style appearances specifically! Lets start on this example.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;
SlimeAppearance secretStyleAppearance = Style.CreateStyleAppearance(Enums.TEST_SLIME, Slime.GetSlimeDef(Enums.TEST_SLIME), "Beta Slime")
```

And that's all for over here! Lets move on.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.