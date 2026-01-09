v6b WeapFixes
Patch by Russel

A simple fix for some weapons in the game that apply properties.
For any weapons that use the "core_[property]player" scripts, they now use
ACS_NamedExecuteWithResult. This applies/revokes the properties instantly, as
opposed to waiting until the end of the tick, resolving some strange interactions.

This file was separated out from v6b-miscfixes to avoid breaking any mods that 
want the other file's under-the-hood system fixes, but also replace weapons to add
their own functionality to them.

REPLACED FILES:
All replaced files have a comment labeled "// $WeapFixes" to show the changed lines.
- actors/inventory/assists/utility/beatcall.txt
- actors/inventory/mm2/timestopper.txt
- actors/inventory/mm6/centaurflash.txt
- actors/inventory/mm8/astrocrush.txt
- actors/inventory/mmb/lightningbolt.txt
- actors/inventory/mmb/tengublade.txt
- actors/inventory/mmk/dawnbreaker.txt
- actors/inventory/mmv/breakdash.txt
- actors/inventory/mmv/sparkchaser.txt
