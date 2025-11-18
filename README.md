# READ PRIOR TO USE
This program is very new and largely untested. In fact, it has not been directly tested on all targeted games (as I do not own all of them.) **I highly recommend backing up saves prior to use.** I am not liable for any data loss/corruption resulting from use of this program.

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
- Shininess (for Pokémon originating in Sword/Shield via SID manipulation and for Pokémon originating in the other supported games via PID manipulation)
- IVs
- EVs
- HT Profile
- PID
- EC
- OT
- TID
- SID

Pokéswitch also supports (bulk) moving, cloning, exporting, and releasing Pokémon. It can import PKM files of the appropriate type (e.g. PK8 for Sword/Shield) and import/export saves.

Note that shinifying a Pokémon you caught in Sword/Shield will result in you no longer being recognized as their original trainer due to modification of the Pokémon's SID. This method is used for Pokémon originating in Sword/Shield because most PIDs generated therein are correlated with several other properties and thus cannot be arbitrarily modified (while maintaining legality).

# Usage
Copy `Pokeswitch.nro` to `/switch` (or wherever else) on your microSD card and launch it via HBL. Select the "Information" option from the main menu to view controls. (Note that the main menu will not be available if no supported savedata is present on the system.)

# Images
![main_menu](https://github.com/user-attachments/assets/a86d6f1a-c212-4794-9645-eca2f39067b1)

![box](https://github.com/user-attachments/assets/1523becd-1a67-4818-9300-88a570f79abc)


# FAQs

## Do I need a hacked Switch to use this?
Yes, see the [NH Switch Guide](https://switch.hacks.guide/) for information regarding system exploitability.

## Can I use this to transfer Pokémon between the supported series?
No. If you need to transfer Pokémon, I would recommend using Pokémon Home, as it generates tracking data server-side. Replicating this is not possible, and transferring a Pokémon between series without a valid Home tracker would render it illegal.

## Why didn't you make this ~6 years ago?
I thought someone would make something like this but no one ever did

# Acknowledgements
The UI was created with (a slightly modified version of) [Plutonium](https://github.com/XorTroll/Plutonium) by [XorTroll](https://github.com/XorTroll).

The Nintendo Switch development platform, [libnx](https://github.com/switchbrew/libnx), was provided by [Switchbrew](https://switchbrew.org/wiki/Main_Page).
