# Random Settings Generator
This script will generate a patch file for The Legend of Zelda Ocarina of Time Randomizer with randomly selected randomizer settings.
This script allows its user to randomize every setting in the Randomizer, not just settings that are natively supported to be randomized.

## Instructions
1. Have Python 3.7 (or newer) installed. This is also a requirement of the randomizer.
2. Download the zip file of the source code from the release page and unzip anywhere: https://github.com/matthewkirby/plando-random-settings/releases
3. Place your Ocarina of Time 1.0 rom that you wish to use in this directory. It must have the `.z64` file extension.
4. If you are under linux make sure that `randomizer/Decompress/Decompress` or `randomizer/Decompress/DecompressARM64` are executable (run `chmod +x randomizer/Decompress/Decompress` or  `chmod +x randomizer/Decompress/DecompressARM64` if not)
5. Run the code by double clicking `RandomSettingsGenerator.py` or running `python3 RandomSettingsGenerator.py` (or however you run python files on your system) via the command line.
6. Your patch file will be saved in the `patches` directory.

## Rolling seeds with Weight Overrides
If you are playing a format besides an official Random Setting League race, you may wish to edit the weights. 

1. Put the weights you wish to change into a JSON file in the weights folder
2. Open `RandomSettingsGenerator.py` in a text editor and add the line `global_override_fname = "<override file name>.json"` where you replace `<overworld file name>` with the name of your weights file.

We simplify this process by providing some presets. To use these presets, open `RandomSettingsGenerator.py` in a text editor and remove the `# ` (including the space after the `#`) from...

- Line 10 for multiworld
- Line 11 for DDR
- Line 12 for Beginner
- Line 13 for Co-Op

## Command Line Interface Options
If you opt to run the script via the command line, you have several options available to you
- `--no_seed`: Generates a plando file in the `data` directory but does not generate a patch file
- `--override <path_to_weights_file>`: Provide a weights override file to be used on top of the default RSL weights. Random settings will be generated using the weights in the override file. Any settings not in the override file will get their weights from the RSL weights. The file is expected to be in the weights directory at the moment.
- `--worldcount <integer>`: The number of worlds to generate for generating multiworld patch files. If this is not given, the default is 1.

# FAQ
> It didn't work! What do I do?

The error message should be logged in `ERRORLOG.TXT` so take a look there. If you cannot figure out what went wrong, head over to the Ocarina of Time Randomizer discord channel (https://discord.gg/ootrandomizer) and ask for help in the #rsl-discussion text channel.


> Do I need to download the randomizer?

Not anymore! Since this code doesn't function without the randomizer and having the wrong version will crash the code, we now manage that for you! This code base is all you will need to get started! Once you have your patch file you can patch with any version of the randomizer you have downloaded, the one we download in the `randomizer` directory or the web generator at https://ootrandomizer.com/
