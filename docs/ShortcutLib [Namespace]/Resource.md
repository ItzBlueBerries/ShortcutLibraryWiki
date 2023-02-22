# Resource

You may think "what is related to something named resources" well.. Gadgets! Foods! Gardens! All of that stuff!

### `GetGadgetDef(Gadget.Id gadgetId)`

Just gets a gadget definition since they use special ones. `GadgetDefinition` to be specific.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;
GadgetDefinition gadgetDef = Resource.GetGadgetDef(Gadget.Id.EXTRACTOR_DRILL_NOVICE); // Gets the Novice Extractor Drill definition.
```

### `CreateMeat(Identifiable.Id meatPrefab, Identifiable.Id meatID, string meatName, Color vacColor, Sprite icon, string meatAnimator, Texture2D rampGreen, Texture2D rampRed, Texture2D rampBlue, Texture2D rampBlack, float transformChance = 5f, bool isChick = false, bool isElder = false)`

This is purely for creating meat such as chicks, hens / roostros or elder hens / roostros. Sounds nice right? Thing is, they don't take your usual material with colors.. unless you choose to do it that way.

Let me explain before we get to the code example. They take materials but their default materials use ramps. Ramps are images that have colors on them and they color certain areas of the actor. This is where you would `LoadImage()` all of these as they are Texture2D and not a Sprite. You of course need to have your own ramps though otherwise this may not work properly. The code example will show me using placeholder variables for these.

Oh yeah and another thing. `meatAnimator` is very specific, this is something you have to figure out yourself by inspecting your game with Unity Explorer or something and looking for it within the actor you are trying to create using a copy of its prefab. Otherwise, `transformChance` indicates when a Hen / Roostro can turn into an Elder or well its chance of happening. Well that's all I think.

*lol, the animators is basically the name + `/mesh_body1` after it*

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

GameObject newMeat = Resource.CreateMeat(Identifiable.Id.HEN, Enums.NEW_MEAT, "New Meat", Color.gray, whatever_icon, "Hen Hen/mesh_body1", greenRamp, redRamp, blueRamp, blackRamp);
// Creates a copy of a Hen named "New Meat", the animator is "Hen Hen/mesh_body1"
```

