# Alternative Level Data

This framework allows you to add alternative data to levels, which will change a way a level is displayed in story mode for a specific variation/difficulty. This can be used to change the background, change the props, change the title text and title sprite, change visibility and even add songs (song addition in alt level data has some requirements, see below). All you need to do is add a folder to one of the existing folders in this directory (UD/levels-alt/difficulties or UD/levels-alt/variations) named with the ID of your difficulty/variation and to that folder, add the level datas named with the IDs of the levels you want to change. For example, if I want to change the level data of week 1 for the "pico" variation, I can put a modified `week1.json` in `UD/levels-alt/variations/pico`.

# Specific Requirements for Song Addition

The songs list in your alt level data must have all of the songs from the original level data, plus the songs you want to add. Your songs will be ordered relative to the other song that are already included in the original week. For example, here's a song list for week 2 alt data for the "d-sides" variation: `["spookeez", "south", "ghastly", "monster"]`. The song "ghastly" will be added after the "south" song and before the "monster" song.

> [!WARNING]
> it's your responsibility to make sure the songs appear only in the difficulties you want them to appear in, because added songs will appear for all the difficulties they have, regardless of the variation or difficulty associated with the alt level data which added them.
> 
> So for example, if I want the song `ghastly` to only appear in the `d-side` difficulty, I'll need to make sure I use it's default variation only with the `d-side` difficulty. However, this can be problematic when other songs in the level don't use the default variation, but an injected variation, and rely on difficulty display name trimming (which trims the **variation name** from the start of the difficulty name in menus) for difficulties like `d-sidehard` or `d-sidenormal`, because this means the difficulty will display as `hard` or `normal` for the songs which use the injected variations and will stay as `d-sidehard` or `d-sidenormal` for songs like `ghastly`, which use the default variation. We can fix this by pre-defining the display names instead of relying on display name trimming. In our case, the definision lines might look something like this:
> ```txt
> d-sideeasy,,easy
> d-sidenormal,,normal
> d-sidehard,,hard
> ```