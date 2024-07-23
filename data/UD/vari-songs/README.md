# Variation-specific song scripts

This directory should contain scripts for existing songs, which will replace the original song scripts when the variation is selected. This can help you replace the default behaviors defined in song scripts with new ones for your own variations of any song without replacing the song scripts themselves.

You don't have to put these scripts here (like all the other scripts, you can technically put these anywhere in your mod's folder), but it's a good practice to keep them in a separate directory to avoid confusion. It's also a great excuse for me to make a README file that explains how this works.

## Template

So here's a template for a variation-specific song script with some additional instructions:

```haxe
import funkin.play.song.Song;

class UDMySongMyVariation extends Song {

    function new() {
        // Here we give the song's real ID to the super constructor
        // so that the object will be constructed properly as a copy
        // of the original song.
        super("my-song");
        // However, after the super constructor finishes, we
        // need to change the ID to something else to make sure
        // the `SongRegistry` doesn't overwrite the original song
        // with this variation.

        // Make sure you always use this format for the final ID,
        // because the framework relies on it to identify your script.
        this.id = "UD::my-song::my-variation";
    }

    // You can override any functions you want to change here
    // or add new functions and variables to this class.

    // Just keep in mind that this is a completely separate script
    // from the original song script, so you can't rely on any of
    // the original song's functionality unless you copy it over.
}
```