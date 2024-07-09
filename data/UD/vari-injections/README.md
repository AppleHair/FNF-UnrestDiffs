# Variation Injection

Instead of replacing existing songs' default metadata and chart files, this framework allows you to inject your variation into existing songs using polymod's append logic. This way, you can add your variation to an existing song without replacing its files, and multiple mods can add their variations to the same song without conflicting with yours.

To inject your variation into existing songs, you'll need to put an empty `.txt` file in this folder, with its name as your variation's name, and then add another `.txt` file with the same name to the same place, but through the `_append` folder, and fill that file with the song ids you want to inject your variation to separated by new lines. This method utlizes polymod's append logic, which means every variation injection file you make will be appendable by other mods.

> [!NOTE]
> You need to have the variation chart and metadata files placed in the songs folder for this to work (NOT through the `_append` folder). However, just remember not to replace the default ones, because this is the action variation injection was meant to replace.

## Examples

This will be located at `mods/[mod's name]/_append/data/UD/vari-injections/[variation name].txt`:
```txt
bopeebo
fresh
dadbattle
```

This will be located at `mods/[mod's name]/data/UD/vari-injections/[variation name].txt`:
```txt
// Empty file
// and yes, you can actually put comments in here, but only at the start of the line
// You can also have empty lines, like this one:

// You see, empty lines are allowed and are ignored.
```

The final file will look like this:
```txt
// Empty file
// and yes, you can actually put comments in here, but only at the start of the line
// You can also have empty lines, like this one:

// You see, empty lines are allowed and are ignored.
bopeebo
fresh
dadbattle
```

Then, another mod could do this again with a different variation name, but with the same songs, and both variations will appear in the game. Another mod might also do this with the same variation and different songs. For example:

This will be located at `mods/[mod's name]/_append/data/UD/vari-injections/[variation name].txt`:
```txt
spookeez
south
monster
```

This will be located at `mods/[mod's name]/data/UD/vari-injections/[variation name].txt`:
```txt
// Empty file
// It doesn't matter if you put different comments here
// Just don't put anything important in here, because it might get replaced
```

Now, the final file will look like this:
```txt
// Empty file
// It doesn't matter if you put different comments here
// Just don't put anything important in here, because it might get replaced
bopeebo
fresh
dadbattle
spookeez
south
monster
```

As you can see, the empty file's only purpose should be to form a base for polymod to append to, and that's why only append logic should be used to make the actual list of songs to inject the variation to.