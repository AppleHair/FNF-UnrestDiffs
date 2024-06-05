# Unrestricted Difficulties

The Unrestricted Difficulties framework is a softcoded FNF mod, which provides FNF modders with more control over difficulties and variations.

## Disclaimer
In order to implement some of this framework's features, I had to override some of the default scripts form the base game and even create templates for specific kinds of scripts (song and level script templates), which other mods will need to use in order to utilize some of this framework's most important features, such as adding custom variations to freeplay and story mode. To account for that, I added special attributes to some of the song scripts, which you can set using "scriptSet" on "onCountdownStart" through a module, as opposed to overriding the scripts, to customize the script's default behavior (which includes cutscenes and more song-spesific stuff). However, this still means mods which override any of the base game's song or level scripts is incompatible with this mod and I currently don't have any way to prevent this.

## Features

The framework includes the following features:
- Makes your custom song variations appear in freeplay (requires usage of the song script template) and story mode (requires usage of both the song and level script templates).
- Variation injection system (placeholder)
- Difficulty display name trimming (placeholder)
- Improved story mode menu, with the following key improvments:
  - Limits the range of difficulties you can choose from and changes the song list according to the songs and difficulties available in each level, as opposed to relaying on a constant and displaying only "easy", "normal" and "hard" (which means you can play base game levels on "erect" and "nightmare" difficulties form the story mode menu using this framework).
  - Adds custom story mode menu script events (`UD_STORY_ENTER`, `UD_STORY_SCROLL`, `UD_STORY_EXIT`, `UD_STORY_CONFIRM`), which get called on modules.
  - Lets you inject alternative data to a level for different variations\difficulties available in the level, meaning you can customize how a level looks in the story mode menu (and even add songs in certain conditions) when having specific difficulties selected (requires usage of the level script template).
- Support for custom difficulty sprites, which can also be animated (for freeplay, story mode and result screen)
- Implemented "rating" system, which orders difficulties in freeplay and story mode according to priority numbers from the metadata files' "playData.ratings" property.
- Added special attributes to some of the song scripts, which you can set using "scriptSet" on "onCountdownStart" through a module, as opposed to overriding the scripts, to customize the script's default behavior (which includes cutscenes and more song-spesific stuff)
