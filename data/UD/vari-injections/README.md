# Variation Injection

Instead of replacing existing songs' default metadata and chart files, this framework allows you to inject your variation into existing songs. This way, you can have your variation in the game without replacing the default ones, and multiple mods can have their variations in the same song without conflicts.

To inject your variation into existing songs, you'll need to put an empty ".txt" file here, with its name as your variation's name, and then add another ".txt" file with the same name to the same place, but through the _append folder, and fill that file with the song ids you want to inject your variation to separated by new lines. This method utlizes polymod's append logic, which means every variation injection file you make will be appendable by other mods.

## Example

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

Another thing to note is that you need to have the song variation chart and metadata files placed in the songs folder for this to work (NOT through the _append folder). However, just remember not to replace the default ones, because this is the action variation injection was meant to replace.