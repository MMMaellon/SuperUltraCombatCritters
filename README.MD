# SuperUltraCombatCritters

A set of avatar prefabs that creates a little critter that follow you and fights other critters on other avatars.
The "Hop Follower" prefab is a lightweight version that doesn't include the combat system.
The Advanced version of the Hop Follower includes some extra functions which requires syncing a bit more data.
The full prefab with the combat system is unoptimized.

## How to Install the "Hop Follower" Prefab

Drag the "Hop Follower" prefab onto your avatar so that it's a direct child of your avatar's root object.
Make sure the gameobject that you just dragged in is named "S.U.C.C."
Then place the 3d model you want to be your pet under /S.U.C.C./worldAnchor/critter/model/
Set the FX layer on your avatar descriptor to "Hop Follower FX".
Then set your avatar descriptor's menu object to "Hop Follower Menu".
Then set your avatar descriptor's parameters object to "Hop Follower Params".
Alternatively, you can merge the menu and params with your existing menu and params.

## How to Install the full SUPER ULTRA COMBAT CRITTERS prefab

***Warning this prefab isn't optimized at all and will give your avatar a "Very Poor" rating. This is because there's a ton of colliders, particle systems, and mesh renderers**

This prefab includes the follower and the full combat system.
First pick a critter - there's a bear, duck, and dog. To see gameplay differences between the critters, visit the Gameplay section.
Drag the prefab for your critter onto your avatar so that it's a direct child to the root object of your avatar.
Make sure the gameobject that you just dragged in is named "S.U.C.C."
Set the FX layer on your avatar descriptor to "SUCC FX".
Then set your avatar's parameters object to the params that correllate to your critter.
Set the menu on your avatar descriptor to "SUCC menu"

*Optional* unpack the prefab and make the gameobject called "forward" a child of your avatar's head bone for better control of the targetting system when starting combat.
This allows you to aim the target by turning your head instead of your entire avatar.

## Gameplay

Each player starts with 10 HP and each attack they receive reduces their health.
When their health becomes zero, that player's critter "faints" and combat ends.
If both combatants "faint" on the same round, they both lose.
Winners earn a badge for their critter.
If you win multiple times in a row, you get multiple badges, up to 3 badges.

There are 3 critters, the bear, the duck, and the dog.
The bear does extra grass damage because bears live in the woods.
The duck does extra water damage because they're waterfowl.
The dog does extra fire damage because of the "This is fine" meme lol.

To begin combat, both combatants must hit the "Start Combat" options in their menus and aim their critters at each other.
Reticles will appear on the floor that the combatants need to aim directly over their opponent's critter.
Once the "SELECT MOVES" message appears, players can open the "Combat Controls" sub-menu in their avatar menu and begin fighting.
At the start of a round, each player chooses two moves.
When both players have chosen their moves, the critters will automatically execute the attacks.

There are 7 possible moves: Fire Attack, Water Attack, Grass Attack, Block Fire, Block Water, Block Grass, and Charge Super Ultra.
Players can choose any combination of these moves including two of the same move in one turn.
Blocks give immunity to all damage of a certain type. If an attacker performs two Fire Attacks, their opponent can block both attacks with one Fire Block.
Charging your Super Ultra adds a stack of Super Ultra to your Super Ultra bar.
Charging Super Ultra 3 times will fill up the Super Ultra bar and allow your critter to deal twice as much damage with each attack.
Once Super Ultra is active, each attack consumes a stack of Super Ultra, and the effect ends if all of it is used up.

Attacks damage your opponent and lower their health.
Each attack does 1 damage normally, and 2 damage if the Super Ultra is active.
Additionally, Dogs deal 1 extra point of fire damage, ducks 1 extra water damage, and bears 1 extra grass damage.
If a dog lands two fire attacks while their Super Ultra was up, they'd do 2 damage per attack + 2 points of extra damage for a total of 6 damage.

## Dev Notes

SUCCMove enum values:

0 - Null
1 - Charge
2 - AttackFire
3 - AttackWater
4 - AttackGrass
5 - DefendFire
6 - DefendWater
7 - DefendGrass

SUCC combat state enum values:

0 - Out of Combat
1 - Aiming / setting up positioning
2 - Choosing Actions
3 - Actions Locked in
4 - Playing Action Animations
5 - Dead

SUCC combat animation state enums

0 - Not playing animations
1 - reveal icons and turning on colliders
2 - fire animations
3 - fire2 animations
4 - fire hurt
5 - water animations
6 - water2 animations
7 - water hurt
8 - grass animations
9 - grass2 animations
10 - grass hurt
11 - charge animations
12 - death/win
