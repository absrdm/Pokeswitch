# READ PRIOR TO USE
This program is very new and largely untested. In fact, it has not been directly tested on all targeted games (as I do not own all of them.) **I highly recommend backing up saves prior to use.** I am not liable for any data loss/corruption nor bans/suspensions resulting from use of this program.

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
- Poké Ball
- Form (for most Pokémon with persistent alternate forms)
- Dynamax Level (for Sword/Shield)
- Gigantamax Factor (for Sword/Shield)
- Original Tera Type (for Scarlet/Violet)
- Effective Tera Type (for Scarlet/Violet)
- Height (for Sword/Shield, Brilliant Diamond/Shining Pearl, and Scarlet/Violet)
- Weight (for Sword/Shield, Brilliant Diamond/Shining Pearl, and Scarlet/Violet)
- Scale (for Scarlet/Violet and Z-A)
- Alpha Condition (for Z-A)
- PID
- EC
- OT
- TID
- SID

Pokéswitch also supports (bulk) moving, cloning, exporting, and releasing Pokémon. It can import PKM files of the appropriate type (e.g. PK8 for Sword/Shield) and import/export saves.

Pokéswitch features Pokémon Home-like functionality in the hyperboxes. **Note that Pokémon transferred to a different series via the hyperboxes will generally be rendered illegal due to absence of a valid Pokémon Home tracker. Online interaction of these Pokémon, particularly with Pokémon Home, can result in bans/suspensions.**

Additional information can be found in the [GBAtemp thread](https://gbatemp.net/threads/pokeswitch-simple-pokemon-save-editor-for-switch.677289/).

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

## HIDs

If a Pokémon transferred to the hyperboxes is recognized to already exist therein, the version in the hyperboxes will be updated with the version being transferred. This allows for a Pokémon's data to be aggregated across series.

Within the hyperboxes, Pokémon are identified by a value (HID) consisting of the PID and a derivate of the name. (This means that modifying a Pokémon's PID or name will generally result in the Pokémon not being recognized as the original.) The HID is partially derived from the name to obviate any necessity to modify PIDs (which can result in legality issues) when attempting to transfer e.g. multiple modified clones of a Pokémon to the hyperboxes as distinct entities.

HIDs are processed per-hyperbox file, so importing a hyperbox file can affect whether a Pokémon is recognized to exist within the hyperboxes.

## Hyperbox Minutiae

- When a Pokémon in a hyperbox is updated, most properties thereof are overwritten (provided that they exist in the version being transferred.) Exceptions include (but are not necessarily limited to) met data and some OT data.
- Releasing a Pokémon from the hyperboxes will result in the deletion of all of the Pokémon's data from the hyperboxes. (If transferred back to the hyperboxes thereafter, the Pokémon will be processed as a new transfer.)
- Hold items are stored per-series. When transferred to a series for the first time, a Pokémon's hold item will default to that of the series from which the Pokémon was originally transferred (unless this is not a valid hold item in the destination series.)
- Moves and relearn moves are stored per-series. When transferred to a series for the first time, a Pokémon's moves and relearn moves will default to those of the series from which the Pokémon was originally transferred (unless these e.g. do not exist in the destination series.) If none of a Pokémon's moves can be transferred to the destination series, Pokéswitch will attempt to default them to moves in the Pokémon's learnset.
- Since Sword/Shield do not support some Poké Balls at all, these will be defaulted to normal Poké Balls when transferring Pokémon to the aforementioned. Transferring Pokémon from Sword/Shield to the hyperboxes will not result in these Poké Balls being overwritten as long as the Pokémon being transferred are still in normal Poké Balls at the time of transfer.
- Since Pokémon from Z-A are not officially transferable to other series, some met data is defaulted to compatibility values upon doing so.

# FAQs

## Do I need a hacked Switch to use this?
Yes, see the [NH Switch Guide](https://switch.hacks.guide/) for information regarding system exploitability.

## Can I use this to transfer Pokémon between the supported series?
Yes, via the hyperboxes. However, I would recommend using Pokémon Home for this purpose if possible, as it generates tracking data server-side. Replicating this is not possible, and transferring a Pokémon between series without a valid Home tracker generally renders the Pokémon illegal.

## How do I import a PKM file?
In Select Mode (blue cursor), press A on any empty box slot, then select the PKM file to import.

## A service initialization error is returned upon launch. Is there a fix for this?
This might be resolved by launching via HBL title override (HBL opened by holding the R button while launching a game, rather than the Album). If it is not, feel free to post the specific issue on the [GBAtemp thread](https://gbatemp.net/threads/pokeswitch-simple-pokemon-save-editor-for-switch.677289/).

## Can I use more than 1000 hyperboxes?
This may be achieved by swapping between multiple hyperbox files as necessary, but it is recommended to read the notes regarding HIDs before doing so.

## Why didn't you make this ~6 years ago?
I thought someone would make something like this but no one ever did

# Acknowledgements
The UI was created with (a slightly modified version of) [Plutonium](https://github.com/XorTroll/Plutonium) by [XorTroll](https://github.com/XorTroll).

The Nintendo Switch development platform, [libnx](https://github.com/switchbrew/libnx), was provided by [Switchbrew](https://switchbrew.org/wiki/Main_Page).

The hyperboxes were warped from vacuum by my friend. (You might see them somewhere.)