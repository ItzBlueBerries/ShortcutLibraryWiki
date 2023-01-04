# EatMap

Now this is a place you can get your slimes to eat whatever and produce whatever, fun right?
Maybe even transform..

### `CreateBecomeMap(Identifiable.Id slimePrefab, Identifiable.Id toBecome, Identifiable.Id whatItEats, float minDrive = 1f, float extraDrive = 0f, SlimeEmotions.Emotion slimeDriver = SlimeEmotions.Emotion.AGITATION)`

Here you can make an EatMap that transforms a Slime into something else when it eats the specified item. Much easier than a harmony patch.

- **Code Example**
```cs
using static ShortcutLib.Shortcut;

EatMap.CreateBecomeMap(Enums.TEST_SLIME, Identifiable.Id.PINK_SLIME, Identifiable.Id.PINK_PLORT); // When test slime eats pink plort it becomes pink slime.
```

### `CreateProduceMap(Identifiable.Id slimePrefab, Identifiable.Id toProduce, Identifiable.Id whatItEats, float minDrive = 1f, float extraDrive = 0f, bool isFavorite = false, int favProduceCount = 2, SlimeEmotions.Emotion slimeDriver = SlimeEmotions.Emotion.AGITATION)`

About the same thing but instead if it eats the specified item, it'd instead produce something else!

- **Code Example**
```cs
using static ShorcutLib.Shortcut;

EatMap.CreateProduceMap(Enums.TEST_SLIME, Identifiable.Id.PINK_PLORT, Identifiable.Id.PINK_SLIME, isFavorite: true) // When test slime eats pink slime it produces pink plort. (Also is favorite so it'll produce twice)
```

And that's everything for over here! Play around with this if you want, it's a pretty fun feature.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.