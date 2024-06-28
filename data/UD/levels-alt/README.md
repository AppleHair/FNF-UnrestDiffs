# Alternative Level Data

This framework allows you to add alternative data to levels, which will change a way a level is displayed in story mode for a specific variation/difficulty. This can be used to change the background, change the props, change the title text and title sprite, change visibility and even add songs (song addition in alt level data has some requirements, see below). All you need to do is add a folder to one of the existing folders in this directory (UD/levels-alt/difficulties or UD/levels-alt/variations) named with the ID of your difficulty/variation and to that folder, add the level datas named with the IDs of the levels you want to change. For example, if I want to change the level data of week 1 for the "pico" variation, I can put a modified `week1.json` in `UD/levels-alt/variations/pico`.

# Specific Requirements for Song Addition

The songs list in your alt level data must have all of the songs from the original level data, plus the songs you want to add. Your songs will be ordered relative to the other song that are already included in the original week. For example, here's a song list for week 2 alt data for the "d-sides" variation: `["spookeez", "south", "ghastly", "monster"]`. The song "ghastly" will be added after the "south" song and before the "monster" song.

Note that it's your responsibility to make sure the songs appear only in the variations/difficulties you want them to appear in, because added songs will appear for all the difficulties they have, regardless of the variation or difficulty associated with the alt level data which added them. This is especially important if you don't want your song to appear in the default variation, because the game forces you to have a default variation, but you can still remove it's difficulties from your song script.

In order to make sure your song doesn't appear in the default variation, you can add only the "normal" difficulty to the default metadata's `playData.difficulties` array, and then create a song script for the song with the following code:

```haxe
import funkin.play.song.Song;

class GhastlySong extends Song {

    public function new() {
        super("ghastly");
    }

    override function populateDifficulties():Void {
        super.populateDifficulties();
        // So now every time the game will try to load the all
        // of the difficulties, it will remove the "normal" difficulty,
        // so we don't even need to create chart data for it.
        this.difficulties.remove("normal");
    }
}
```

If this doesn't work for you or it triggers an error, please [submit an issue](https://github.com/AppleHair/FNF-UnrestDiffs/issues), describe the problem and screenshot the error.