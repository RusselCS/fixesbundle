v6c-MiscFixes
mod for MM8BDM-v6b
by Russel

"Issues like this shouldn't have to wait for core to fully turn over."

This wad is meant to serve as an "interim hotfix patch" for specific issues with
MM8BDM v6b. This does the following:

Fix for the "soft crash" related to ACS Damagers.
- Root cause: Edge cases in the Hazard frag credit system caused infinite recursion.
- Fix: Don't process hazard credit under circumstances where it can happen infinitely.
- Systems changed:
			BasicACSDamager now hits instantly, within the same tick as the call.
			ACTRUTIL.acs now forces the BasicACSDamager into its damaging state.
			HZRDCRED.acs now has some additional safety checks.
- Fix by Jax.

Fix for Rush Marine appearing in maps without water when randomizer enabled.
- Root cause: Rush Marine's map validity flag was always true with core defs enabled.
- Fix: Check for "MM8BDM_Water" actors before marking the item as map valid.
- Systems changed: COREITEM.acs now checks for water before setting Rush Marine map valid.
- Fix by Russel.

Fix for missing MENUDEF options from MM8BDM-v6b.
- Root cause: Zandronum testing version updated.
- Fix: Integrated the MENUDEF changes from v6b_menudef_3.2-240405-2229a.pk3
- Fix by Celebi

Fix for Voice Chat icons missing from MM8BDM-v6b.
- Root cause: Zandronum testing version updated.
- Fix: Integrated some voice chat icons, based on Bari III.
- Fix by Russel, animated icons for the 3.2 alpha dated October 2024 by Binary.

Fix for bots becoming ghosts in MM8BDM-v6b.
- Root cause: core_healscript was not checking if the recipient was dead before giving health.
- Fix: Make sure the recipient's health is >0 before giving them health.
- Fix by Russel

Fix for "Ready To Go" icon no longer being 8-bit in the 3.2 alpha dated October 2024
- Root cause: Zandronum testing version updated.
- Fix: Added "RDYTOGO.png" to the graphics folder.
- Fix by Russel.

Change for "core_radiusPull" to allow it to cause hazard fragging.
- Change by Russel.

Replaced Files
The following files have been replaced by this wad.
If your mod replaces them too, it will break.
Feel free to implement the fixes yourself. Unless otherwise noted, all changes are noted with a " // $MISC" comment within the file itself.
- actors/basicactors.txt     - Reason: Reduce response time from BasicACSDamager.
- acs/ACTRUTIL               - Reason: Reduce response time from BasicACSDamager, allow frags on core_radiusPull.
- acs/HZRDCRED               - Reason: Prevent Hazard credits from calling recursively.
- acs/COREITEM               - Reason: Prevent Rush Marine from being mapvalid when water is not present.
- acs/HPCHEC			     - Reason: Prevent dead players from healing.
- graphics/RDYTOGO.png       - Reason: MM8BDM-style graphic added.
- graphics/SPKRMINI1.png     - Reason: MM8BDM-style graphic added.
- graphics/SPKRMINI2.png     - Reason: MM8BDM-style graphic added.
- graphics/SPKRMINI3.png     - Reason: MM8BDM-style graphic added.
- graphics/SPKRA0.png        - Reason: MM8BDM-style graphic added.
- graphics/SPKRB0.png        - Reason: MM8BDM-style graphic added.
- graphics/SPKRC0.png        - Reason: MM8BDM-style graphic added.

MENUDEF runs on a module system where if you add a new file that contains the same module, the new replaces the old.
If your mod replaces any of the follow menus, consider updating.
- ./MENUDEF/8BDM_Multiplayer         - Reason: Added voice chat support.
- ./MENUDEF/ZA_ServerSetupMenu       - Reason: Added voice chat support and RCON Logout button.
- ./MENUDEF/CustomizeControls        - Reason: Added push-to-talk button, and buttons to scroll the scoreboard.
- ./MENUDEF/8BDM_AudioSettings       - Reason: Added voice chat support.
- ./MENUDEF/8BDM_UISettings          - Reason: Added Scoreboard Options menu.
- ./MENUDEF/8BDM_MultiplayerSettings - Reason: Added Spectator Mode toggle.