DON'T LIKE THE BALANCE DECISIONS BY THE VANILLA DEVS??
neither do i and i made 90% of it

Gravity Hold got you down?
Mirror Buster killing you and your family while also serving as its own defense attourney?
Metal Blade eating your entire supply of cheese?
Time Stopper?

HERE'S HOW YOU BAN SHIT:
- Open the console. Type "banwep_weaponname true". Reset the map. It's gone! Goodbye!!
	- Example: "banwep_timestopperwep true".
	- Note: This relies on the weapon's ACTOR name. So you'll need to know that.
	- Buster upgrades are banned by UPGRADE name, not by weapon name.
- To unban, just type "banwep_weaponname false". Oh no... it's back...
- If you want to reset all bans, use the "resetwepbans" command.
- Also bans the weapon from vanilla's random LMS loadouts, and even Eddie!
- Don't like a certain item? Ban it! "banitem_item true" to stop the bullshit.
	- Example: "banitem_exitunititem true"
	- Works on basic pickups, too!
	- And PartyBall!
	- Once again, you need to know the actual actor name.
- Command to remove all item bans is "resetitembans".

Don't like empty space? HERE'S HOW YOU REPLACE SHIT:
- Open the console. Type "replacewep_weaponname replacement". Reset the map. Is that a new outfit? Wow!!
	- Example: "replacewep_metalbladewep needlecannonwep"
	- Note: Just like with banwep, you'll need to know the actor names for both things you're switching.
	- Also note: You can use ANY ACTOR NAME for this replacewep functionality. Put a prop there if you want.
- To remove the replacement, just do "replacewep_weaponname """. Back to normal!
- If you don't like any of the replacements and want them undone, use the "resetwepreplaces" command.
- Items too!! Replace shit you don't like with other stuff with "replaceitem_item replacement"!
	- Example: "replaceitem_etank bighealth"
	- Keep in mind, you need to know the actual actor names of the swaps!
- Command to revert item replacements is "resetitemreplaces"

All this works with CUSTOM STUFF TOO!
- Custom weapons and items can be banned or replaced with the same commands!
  Just make sure you have a "set" before them!
	- Examples: "set banwep_crystalhunterwep true"
				"set replacewep_pulsestopperwep frostylaserwepcm"
				"set banitem_item1nc true"
				"set replaceitem_crunchransnareitem rushbikeitem"
- Custom weapons and items DO NOT get reset by the built-in reset commands, 
  as scripts only have write access to CVars defined in CVARINFO.

None of this info saves to the ini, so you'll need to make sure they're set on every server run!
(They set under TSPG's "Additional Parameters")

Mod by RusselCS, A very competent vanilla dev :)
Proofreading by Trill.

Known Issues:
- Some pickups, specifically those that give a passive upgrade like Energy Balancer,
  cannot be easily tied back to their pickup, which makes it difficult or impossible
  to fully remove if a player spawns on top of them before the system can remove them.
  This happens at tic 0, where no script can possibly intervene.
  I'll look into options another time.
