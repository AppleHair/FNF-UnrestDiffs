# Difficulty Definitions

Inside the data/UD folder there's a file called "difficulties.txt". You can append difficulty definitions to this file using polymod's append logic, which contain the difficulty's ID/name, its priority number (optional) and its display name (optional). The priority number is used for difficulty sorting in the menus and the display name is used for changing the name the difficulty appears with in the pause menu.

> [!TIP]
> The default difficulties' priority numbers are as follows:
> - easy: 1
> - normal: 3
> - hard: 5
> - erect: 7
> - nightmare: 9
> So be aware of that if you want to position your custom difficulties between the default ones.

In order to use the append logic, you need to create a new folder called "_append" in the root of your mod's folder (mods/[mod name]/_append). Now, if you use this folder like your root folder, every file you put in there will be appended to the original file with the same name in the root folder. This way, you can append difficulty definitions to the difficulties.txt file without having to modify the original file.

Now for the format of the difficulty definitions:
- The difficulty's ID/name, priority number and display name are separated by a colon.
- If you don't specify a priority number, your difficulty will just get appended to the end of the difficulty list in menus.
- If you don't specify a display name, the difficulty's ID/name will be used instead and difficulty name trimming (trims the variation name from the start of the difficulty name) might effect the way your difficulty is displayed on the pause menu.
- every new difficulty definition should be on a new line.
- Empty lines are ignored, and lines starting with a "//" are treated as comments and are also ignored.

## Examples

Here's an example of definitions of the B-Side difficulties:
```txt
easier,1
standard,3
flip,5
```
In this case, the final order of the difficulties in the menu would be:
easy, easier, normal, standard, hard, flip, erect, nightmare

Alternatively, you can just append the difficulty name without a priority number, like so:
```txt
easier
standard
flip
```
In this case, the final order of the difficulties in the menu would be:
easy, normal, hard, erect, nightmare, easier, standard, flip

If you want to change the display names of difficulties and have more specific difficulty IDs, you can do so like this:
```txt
b-side-easier,1,easier
b-side-standard,3,standard
b-side-flip,5,flip
```

You can also choose not to have priority numbers and only change the display names of the difficulties, like this:
```txt
b-side-easier,,easier
b-side-standard,,standard
b-side-flip,,flip
```