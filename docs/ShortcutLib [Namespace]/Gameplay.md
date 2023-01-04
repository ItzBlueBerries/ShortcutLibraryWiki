# Gameplay

What you've all been waiting for.. the Shortcut namespace! This is where most of the developing methods are from when using the library.

For the gameplay class, it mainly effects the gameplay in ways as in adding new corral upgrades, etc.

### `GetPlot(LandPlot.Id plotId)`

This would get a plot's prefab via this method. As you can't get it with `Prefab.GetPrefab()` that's for sure.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

GameObject corralPlot = Gameplay.GetPlot(LandPlot.Id.CORRAL); // This would grab the plot of the corral
```

### `CreatePlotUpgrade(string upgradeName, string upgradeDescription, LandPlot.Upgrade upgradeId, int upgradeCost, Sprite upgradeIcon, LandPlot.Upgrade unlockedUpgradeId = LandPlot.Upgrade.NONE, PediaDirector.Id landPlotPediaId = PediaDirector.Id.CORRAL, string landPlotName = "corral", string upgradeWarning = "This is a default warning!!", bool isAvailableEnabled = true, bool isUnlockedEnabled = false, bool holdToPurchase = false, bool shouldWarn = false)`

A little more exciting than the above method, creating a plot upgrade! This will be a bit longer but lets see if you can keep up and understand the example.

I will note that this creates the entry for it to be purchased, does not operate the upgrade. You will have to do that yourself in one or more components.

Getting your own sprite for the icon is also not done by the library. I also did not use the optional parameters.

*NOTE: MAKE SURE YOU HAVE A CUSTOM ENUM FOR THIS (LandPlot.Upgrade) Like almost everything needs a custom enum to belong to.*

- **Code Example**
```cs
using static ShortcutLib.Shortcut;
LandPlotUpgradeRegistry.UpgradeShopEntry upgradeEntry = Gameplay.CreatePlotUpgrade("Test Upgrade", "This is a complete test!", Enums.TEST_UPGRADE, 500, testUpgradeIcon)
```

That's all for this class! Nothing much besides a few methods, useful though.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.