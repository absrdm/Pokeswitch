# READ PRIOR TO USE
This program is very new and largely untested. In fact, it has not been directly tested on all targeted games (as I do not own all of them.) **I highly recommend backing up saves prior to use.** I am not liable for any data loss/corruption resulting from use of this program.

If you would like to confirm that Pokéswitch is working with your game/system, feel free to post the name of the game and/or your system configuration on the [GBAtemp thread](https://gbatemp.net/threads/pokeswitch-simple-pokemon-save-editor-for-switch.677289/).

# Description
Pokéswitch is a Pokémon save editor designed to run natively on the Nintendo Switch. It aims to support the following games:
- Pokémon Sword/Shield
- Pokémon Brilliant Diamond/Shining Pearl
- Pokémon Scarlet/Violet
- Pokémon Z-A

**Pokéswitch does not perform legality checking.** It implements some basic constraints but generally will not prevent illegal modifications (e.g. most species modifications). Some features, such as name editing, also do not fully support languages aside from English.

Modification of the following properties is supported:
- Name
- Species
- Level
- Gender
- Nature
- Stat Nature
- Ability
- Shininess (for Pokémon originating in Sword/Shield via legacy SID manipulation and for Pokémon originating in the other supported games via PID manipulation)
- Hold Item
- IVs
- EVs
- HT Profile
- Moves
- Maximum PP
- Relearn Moves
- TR Flags (for Sword/Shield)
- TM Flags (for Scarlet/Violet)
- Plus Moves (for Z-A)
- Form (for most Pokémon with persistent alternate forms)
- Original Tera Type (for Scarlet/Violet)
- Effective Tera Type (for Scarlet/Violet)
- PID
- EC
- OT
- TID
- SID

Pokéswitch also supports (bulk) moving, cloning, exporting, and releasing Pokémon. It can import PKM files of the appropriate type (e.g. PK8 for Sword/Shield) and import/export saves.

# Usage
Copy `Pokeswitch.nro` to `/switch` (or wherever else) on your microSD card and launch it via HBL title override (issues may occur in applet mode). Select the "Information" option from the main menu to view controls. (Note that the main menu will not be available if no supported savedata is present on the system.)

# Images
![main_menu](https://github.com/user-attachments/assets/ca0aa8e8-196b-4000-916e-ee5079d7bbb8)

![box](https://github.com/user-attachments/assets/1e3747f0-cc20-451c-a394-c50d7914836c)

# Notes

## Shinification in Sword/Shield
Shinifying a Pokémon you caught in Sword/Shield will result in you no longer being recognized as their original trainer due to modification of the Pokémon's legacy SID. This method is used for Pokémon originating in these games because most PIDs generated therein are correlated with several other properties and thus cannot be arbitrarily modified (while maintaining legality).

## Moving Multiple Pokémon (via Multiselect)
If all selected Pokémon are in the same box and the target slot is compatible, their positions relative to one another will be preserved. If not, the selection will be flattened in the order in which it was added to.

## Shiftable Fields
A selected move's maximum PP can be modified via the L/R buttons.

## TR/TM/Plus Move Handling
Some games store flags related to a Pokémon's moves. Of the supported games, these are Sword/Shield (for TRs), Scarlet/Violet (for TMs), and Z-A (for Plus Moves). When modifying species/form, Pokéswitch will attempt to configure these flags to legal values.

For Sword/Shield and Scarlet/Violet, Pokéswitch will also attempt to set the appropriate TR or TM flag, respectively, when setting a move which could only (aside from nonstandard means) be legally known at the current level via the aforementioned.

For Z-A, Pokéswitch will also attempt to configure natural Plus Move flags when modifying level.

These flags will be cleared during the aforementioned handling only if they are not recognized to be legal. They can also be modified manually in a Pokémon's summary.

# FAQs

## Do I need a hacked Switch to use this?
Yes, see the [NH Switch Guide](https://switch.hacks.guide/) for information regarding system exploitability.

## Can I use this to transfer Pokémon between the supported series?
No. If you need to transfer Pokémon, I would recommend using Pokémon Home, as it generates tracking data server-side. Replicating this is not possible, and transferring a Pokémon between series without a valid Home tracker would render it illegal.

## How do I import a PKM file?
In Select Mode (blue cursor), press A on any empty box slot, then select the PKM file to import.

## A service initialization error is returned upon launch. Is there a fix for this?
This might be resolved by launching via HBL title override (HBL opened by holding the R button while launching a game, rather than the Album). If it is not, feel free to post the specific issue on the [GBAtemp thread](https://gbatemp.net/threads/pokeswitch-simple-pokemon-save-editor-for-switch.677289/).

## Why didn't you make this ~6 years ago?
I thought someone would make something like this but no one ever did

# Acknowledgements
The UI was created with (a slightly modified version of) [Plutonium](https://github.com/XorTroll/Plutonium) by [XorTroll](https://github.com/XorTroll).


The Nintendo Switch development platform, [libnx](https://github.com/switchbrew/libnx), was provided by [Switchbrew](https://switchbrew.org/wiki/Main_Page).
