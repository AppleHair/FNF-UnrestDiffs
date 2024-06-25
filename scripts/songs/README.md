# Song Script Customization (Special Attributes)

The song scripts in this folder contain special attributes which let you customize the script's default behavior without replacing it. This is used for preventing conflicts between multible mods that modify the same song script. The attributes should be set using a module on `onCountdownStart` callback. For example, Here's a module that replaces senpai's conversation when the current variation is "b-side":

```haxe
import funkin.play.PlayState;
import funkin.modding.module.Module;

class senpaiBSideHandler extends Module {
	function new() {
		super('senpai-b-side-handler');
	}

    public override function onCountdownStart():Void {
        if (PlayState.instance.currentVariation != "b-side") {return;}

        switch (PlayState.instance.currentSong.id) {
        case "senpai":
            PlayState.instance.currentSong.scriptSet("conversationId", "senpai-B-sides");
        }
    }
}
```

To learn how to customize other song scripts, you should go look inside the scripts and see what they do and how they use each
attribute. Attributes which are meant to be modified on `onCountdownStart` are using the public access modifier and are present in the highest part of the class block.

## Disclaimer

This system will likely be deprecated in favor of a variation-specific song scripts system in the next update. This is just a temporary solution to prevent conflicts between mods that modify the same song script and it will also be kept as a seperate mod in the future for backwards compatibility with mods that use it, and as a template for new vatiation-specific song scripts.