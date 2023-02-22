# Structure

This is a bit more fun! May be a bit more complicated as well but it involves the structures of slimes and attaching more to their basic model.

### `AddStructure(SlimeDefinition additionalSlimeDefinition, int structureNum)`

This simply adds an existing structure to a slime, simple to use really.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

randomSlimeAppearance.Structures = new SlimeAppearanceStructure[]
{
    new SlimeAppearanceStructure(randomSlimeAppearance.Structures[0]),
    Structure.AddStructure(Slime.GetSlimeDef(Identifiable.Id.ROCK_SLIME), 1)
}; // Gets the slime definition of Rock Slime & adds its structure. (The rock spines / spikes)
// Also yes, all this additional stuff is needed otherwise you wouldn't be adding it properly. You can add more along the list though.
```

### `ColorRadStructure(Identifiable.Id slimePrefab, Identifiable.Id slimeMaterial, Color middleColor, Color edgeColor, [Optional] Vector3 auraSize, int materialStructureNum, int structureNum)`

This would color a rad slime aura if you were to add it to your slime! You can even change the size if you so please.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

Structure.ColorRadStructure(Enums.TEST_SLIME, Identifiable.Id.RAD_SLIME, Color.yellow, Color.magenta, materialStructureNum: 1, structureNum: 1); // Colors it Yellow & Magenta. The structure numbers are the ones for RAD_SLIME.
```

### `ColorGlitchStructure(Identifiable.Id slimePrefab, Identifiable.Id slimeMaterial, Color bottomColor, int materialStructureNum, int structureNum, [Optional] Vector3 trailSize)`

Similar to `ColorRadStructure` but instead it colors the glitch trail if you add it to your slime! The size can also be changed.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

Structure.ColorGlitchStructure(Enums.TEST_SLIME, Identifiable.Id.GLITCH_SLIME, Color.white, 1, 1); // Colors it White. The structure numbers are the ones for GLITCH_SLIME.
```

### `ColorStructure(Identifiable.Id slimePrefab, Identifiable.Id slimeMaterial, Color topColor, Color middleColor, Color bottomColor, [Optional] Color specColor, int materialStructureNum, int structureNum, [Optional] Vector3 structureSize)`

Similar to the 2 other methods above but instead this will color any regular structure. Using `_TopColor, _MiddleColor and _BottomColor` anything with those values should be colored.

If you so please you can also change its size at the end of the method.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

Structure.ColorStructure(Enums.TEST_SLIME, Identifiable.Id.PUDDLE_SLIME, Color.yellow, Color.magenta, Color.white, Color.black, 1, 1);
```

### `CreateBasicStructure(AssetBundle assetBundle, string bundledAsset, string objectName, SlimeAppearance.SlimeBone rootBone, SlimeAppearance.SlimeBone parentBone, SlimeAppearance.SlimeBone[] attachedBones, RubberBoneEffect.RubberType rubberType, bool rubberBoneEffect = true, bool usesMeshRenderer = false)`

Now for one of the fun methods but also Asset Bundles. Creating custom slime structures! There is of course more after this for finishing the process but this is for pretty much creating it entirely, lets go on to the code example.

*NOTE: Make sure to have your own AssetBundle and know the name of the bundled asset you will be using before using this method!*

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

SlimeAppearance.SlimeBone[] attachedBones = new SlimeAppearance.SlimeBone[]
{
    SlimeAppearance.SlimeBone.JiggleBack,
    SlimeAppearance.SlimeBone.JiggleBottom,
    SlimeAppearance.SlimeBone.JiggleFront,
    SlimeAppearance.SlimeBone.JiggleLeft,
    SlimeAppearance.SlimeBone.JiggleRight,
    SlimeAppearance.SlimeBone.JiggleTop
}; // You'll need these for all the structures you create probably

(GameObject, SlimeAppearanceObject, SlimeAppearance.SlimeBone[]) customStructure = Structure.CreateBasicStructure(testAssetBundle, "testStoredMesh", "test_mesh", SlimeAppearance.SlimeBone.JiggleTop, SlimeAppearance.SlimeBone.NONE, attachedBones, RubberBoneEffect.RubberType.Slime);
customStructure.Item2.IgnoreLODIndex = true;

/* 
Okay so like, the bones can change depending on what kind of structure you're adding. Parent bone is usually none though unless its a wing.
RubberType should probably never change unless there is a good reason, it can make them act weird if its not set to "Slime".
IgnoreLODIndex is if you have no LODs and don't know how to add them, I don't so I usually set this otherwise they will disappear if you get far away.
If you do know how and have LODs, go ahead and add those whatever way you can.
And finally, the optional parameters. The rubberBoneEffect makes it rubber or something, idk if it actually does anything but yeah and usesMeshRenderer..
Well that makes it into a SkinnedMeshRenderer instead of a MeshRenderer. Its usually set to false to make it move with your slime but if not, set it to MeshRenderer to make it more of a static look.
MeshRenderer is required for things like spinning by adding the "vp_Spin" component to your structure. It will not move if its a SkinnedMeshRenderer moving along with the slime.
*/
```

### `SetStructureElement(string elementName, SlimeAppearance slimeAppearance, SlimeAppearanceObject[] objectPrefabs, int structureNum, bool addToArray = true, bool supportFaces = false)`

You usually always do this after creating a structure with `CreateBasicStructure`, make sure to do it otherwise it may not work properly. Just sets the element with a prefab and all.

By the way, addToArray basically adds it. Don't do this is you're replacing something like the body or whatever. supportFaces.. I'm not too sure about that one. Whenever you need it I guess but it puts a face on the structure, like your slimes face or whatever. Might be creepy might not be.

- **Code Example**
```cs
using static ShorcutLib.Shortcut;

Structure.SetStructureElement("testMesh", randomSlimeAppearance, new SlimeAppearanceObject[] { customStructure.Item2 }, 1); // Sets the element with your custom structure SlimeAppearanceObject, putting the slime appearance attaches it to your appearance I think.
```

### `SetStructurePrefab(SlimeAppearance slimeAppearance, SlimeAppearanceObject objectPrefab, int structureNum, int prefabsNum, bool addToArray = false)`

The last method here as of now, `SetStructurePrefab` just changes the prefab of a method. By the way `addToArray` might be something I messed up, whatever. This library doesn't really get updates anymore. Maybe just don't do that, why add it to the array anyways if it doesn't- yeah forget it, onto the code example.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

Structure.SetStructurePrefab(randomSlimeAppearance, someSlimeAppearanceObject, 1, 0); // Just sets the prefab of the new object to structure 1. (0 is default / the first one if you didn't know)
```

And that's all for structures, pretty fun right? You may be using it a lot if you get into that custom structure stuff.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.