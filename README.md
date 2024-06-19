# Unrestricted Difficulties

The Unrestricted Difficulties framework is a softcoded FNF mod, which provides FNF modders with more control over difficulties and variations.

## Features

The framework includes the following features:
- Makes your custom song variations appear in freeplay (was relevant before 0.4.0, but now it's already implemented in the base game) and story mode (still relevant).
- Adds a variation injection system, which lets you inject your own variations into existing songs, without overriding their default metadata files.
- Adds a difficulty sorting system, which orders difficulties in freeplay and story mode according to priority numbers.
- Support for custom difficulty sprites in result screen (was relevant before 0.4.0, but now it's already implemented in the base game), which can also be animated (still relevant).
- Adds difficulty display name trimming to the pause menu (and hopefully to the discord RPC too when it gets added to FNF), which will trim a difficulty's variation name from the difficulty's display name if its name starts with the variation name (this doesn't apply to difficulty names that are the same as the variation name).
- Improved story mode menu, with the following key improvements:
  - Limits the range of difficulties you can choose from and changes the song list according to the songs and difficulties available in each level, as opposed to relying on a constant and displaying only "easy", "normal" and "hard" (which means you can play base game levels on "erect" and "nightmare" difficulties from the story mode menu using this framework).
  - Adds custom story mode menu script events (`UD_STORY_ENTER`, `UD_STORY_SCROLL`, `UD_STORY_EXIT`, `UD_STORY_CONFIRM`), which get called on modules.
  - Lets you inject alternative data to a level for different variations\difficulties available in the level, meaning you can customize how a level looks in the story mode menu (and even add songs in certain conditions) when having specific difficulties selected.
- Added special attributes to some of the song scripts, which you can set using `scriptSet` on `onCountdownStart` through a module, as opposed to overriding the scripts, to customize the script's default behavior (which includes cutscenes and more song-specific stuff) (to be deprecated in favor of a per-variation song scripts system).
