# Logs

There are quite a few methods for logging/debugging things with ShortcutLib! Lets start with the logs, shall we?

`Note: All logs will appear as a log from ShortcutLib, not your mod.`

#### `LogComponents(GameObject objectPrefab, bool logToFile = true)`

This is for logging the components of a `GameObject`. It uses foreach loops in order to grab all of them and log them within the `SRML Console`.

- **Code Example**
```cs
using ShortcutLib;
using static ShortcutLib.Shortcut;
Debugging.LogComponents(Prefab.GetPrefab(Identifiable.Id.PINK_SLIME), false); // Gets the prefab of a PINK_SLIME, sets logging to the srml.log file false. Prefab (Class) is featured in the Shortcut Class.
```

Great for figuring out what components a slime or any other GameObject has without some special Unity Explorer or using the code that was used in the method.
The `Prefab` class is also featured in this code block, but is used in the **[Shortcut]()** class. It'll probably be commonly used for getting Slime Prefabs or anything else with a prefab, etc.

#### `LogChildren(GameObject objectPrefab, bool logToFile = true)`

This is for logging the children of a `GameObject`. It again uses foreach loops in order to get the children of the `GameObject` then log them to the `SRML Console`.

- **Code Example**
```cs
using ShortcutLib;
using static ShortcutLib.Shortcut;
Debugging.LogChildren(Prefab.GetPrefab(Identifiable.Id.ROOSTER), true); // Gets the prefab of a ROOSTER (Roostros), sets the logging to the srml.log file true. Prefab (Class) is featured in the Shortcut Class.
```

This would log the children of the `ROOSTER` prefab. This could log various things such as its meshes, transforms, etc.
Once more the `Prefab` class is featured in this code block, which probably will quite a few times within this page.

#### `LogClassContents(HashSet<Identifiable.Id> idenClass, bool logToFile = true)`

This is for logging the contents of a `HashSet`. This still uses foreach loops and will log to the `SRML Console`. Although you may not know what a class is. This will log classes that return `Identifiable.Id`, such as `Identifiable.CHICK_CLASS`. Logging the contents from this class would log all the chicks added to that class. You can simply add something to a class by doing `Identifiable.CLASS_NAME.Add()`.

- **Code Example**
```cs
using ShortcutLib;
Debugging.LogClassContents(Identifiable.SLIME_CLASS, false); // Gives the SLIME_CLASS in the 'idenClass' parameter, sets the logging to the srml.log file false.
```

This would log all the contents from this class, which would mean all the slimes added here. Largos have their own class called the `LARGO_CLASS`. So you may not find a largo in here, but most likely there. Gordos also use the `GORDO_CLASS`, so you should find the gordos there.

#### `Log(string toLog, bool logToFile = true, bool isInfo = true, bool isError = false, bool isSuccess = false)`

This would log whatever message you give it to log to the `SRML Console`! All these parameters may seem like much, but they aren't. They simply give you more options for how your log should be. `isInfo` will log it as an info log, `isError` will log it as an error log, `isSuccess` will log it as an successful log. You should know what `logToFile` does by this point in the page.

- **Code Example**
```cs
using ShortcutLib;
Debugging.Log("Hello World.", false, false, false, true); // Logs "Hello World" to the SRML Console as well as logging it to the srml.log file AND logging it as an successful message.
```

This would log the `string` given. Pretty simple to use, great for debugging things when needed. You could even just log to check if something is running or not! Same goes for some of the other logging methods.

#### `LogFile(string toLog, bool isInfo = true, bool isError = false, bool isWarning = false)`

This method is a little bit different, but about the same as the `Log` method. This time, it won't log to the `SRML Console` but only the `srml.log` file located in the games %AppData%.

- **Code Example**
```cs
using ShortcutLib;
Debugging.LogFile("Hello World", false, true, false); // Logs "Hello World" to the srml.log file AND logging it as an error message.
```

This would log the `string` given to the `srml.log` file. About the same as the previous method as mentioned earlier. If you would like to find out how to locate this file, here is a path: `C:\Users\YOUR_USERNAME\AppData\LocalLow\Monomi Park\Slime Rancher\SRML\srml.log`.

That should be it for logging methods! If you would like to continue, you can move onto **[Other Debugging](https://itzblueberries.github.io/ShortcutLibraryWiki/Debugging%20%5BClass%5D/Other/)** methods.

Return to **[Welcome](https://itzblueberries.github.io/ShortcutLibraryWiki/)**.