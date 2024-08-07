fvnknoots.Retouched
================================================================================

Vanilla balance, just less so.

Goals
--------------------------------------------------------------------------------

  1. Not a "perfect" rebalance.
  2. Nerfing the top weapons a little, but leaving weaker/harder guns be so that players can still show off with them.
  3. Buffing weakest ordnances and tacticals a little, while leaving the strongest alone (except A-Wall).
  4. ~~Minimal changes.~~ (failed)
  5. ~~Avoiding _scope creep_ which causes unnecessary changes to accumulate.~~ (failed)

Design constraints
--------------------------------------------------------------------------------

For now:

  1. Changing 1 value only per item (eg. damage for guns, pull time for gravity star, etc.).
  2. No primary gun changes on top of SMGs, R201/101, Flatline, EVA-8 and Spitfire.
  3. No titan changes.

Change summary
--------------------------------------------------------------------------------

### Primary weapons

  * BTK = bullets to kill

| Weapon     | Near damage           | Far damage             | Very far damage        |
|------------|-----------------------|------------------------|------------------------|
| CAR        | 25 -> 15 (4 -> 7 BTK) | 13 -> 10 (7 -> 10 BTK) | 10 -> 9 (10 -> 12 BTK) |
| Alternator | 35 -> 20 (3 -> 5 BTK) | 18 -> 13 (6 -> 8 BTK)  | 14 -> 10 (8 -> 10 BTK) |
| Volt       | 25 -> 17 (4 -> 6 BTK) | 15 -> 12 (7 -> 9 BTK)  | 12 -> 10 (9 -> 10 BTK) |
| R97        | 20 -> 13 (5 -> 8 BTK) | 12 -> 8 (9 -> 13 BTK)  | 10 -> 7 (10 -> 15 BTK) |
| R101       | 25 -> 17 (4 -> 6 BTK) | 17 (6 BTK) (_vanilla_) | 12 (9 BTK) (_vanilla_) |
| R201       | 25 -> 17 (4 -> 6 BTK) | 17 (6 BTK) (_vanilla_) | 12 (9 BTK) (_vanilla_) |
| Flatline   | 30 -> 20 (4 -> 5 BTK) | 20 (5 BTK) (_vanilla_) | 15 (7 BTK) (_vanilla_) |
| G2         | 40 -> 30 (3 -> 4 BTK) | 35 -> 30 (3 -> 4 BTK)  | -                      |
| DMR        | 55 -> 45 (2 -> 3 BTK) | 55 -> 45 (2 -> 3 BTK)  | -                      |
| Spitfire   | 35 -> 25 (3 -> 4 BTK) | 25 -> 20 (4 -> 5 BTK)  | 20 -> 17 (5 -> 6 BTK)  |
| L-STAR     | 25 -> 20 (4 -> 5 BTK) | 18 -> 16 (6 -> 7 BTK)  | -                      |
| Mastiff    | 20 -> 17 (5 -> 6 BTK) | 12 -> 10 (9 -> 10 BTK) | -                      |
| EVA-8      | 200 -> 150            | 10 (_vanilla_)         | -                      |
| RE-45      | 20 -> 15 (5 -> 7 BTK) | 13 -> 12 (7 -> 9  BTK) | 9  -> 8 (12 -> 13 BTK) |
| P2016      | 30 -> 20 (4 -> 5 BTK) | 20 -> 17 (5 -> 6  BTK) | 15 -> 13  (7 -> 8 BTK) |
| Melee      | 100 -> 70             | -                      | -                      |

#### Notes

  * SMGs and sidearms have decreased damage across all ranges.
  * G2 and DMR have increased headshot multipliers to compensate for damage nerfs
  * ARs have near range damage decreased, but vanilla far ranges.
  * Melee now needs to be used on a slightly damaged enemy.

### Tacticals

| Tactical     | Change                                     |
|--------------|--------------------------------------------|
|  A-Wall      | Shield health reduced by 50% (1000 -> 500) |
|  Pulse blade | 50% faster recharge (8 -> 12)              |
|  Cloak       | 50% faster recharge (10 -> 15)             |
|  Holo pilot  | 100% faster recharge (8 -> 16)             |

#### Notes

  * A-Wall can still tank a Kraber bullet, but not much more - lower HP should force the shield to be used more tactically, instead of being a camping tool. Lower HP also makes it so that the electric smoke is a convenient counter to it.
  * Pulse blade, cloak and holo pilot cooldowns have been reduced to encourage more usage

### Ordnances

| Ordnance       | Change(s)                                                                                                            |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| Gravity star   | Pull time reduced by 50% (2.0s -> 1.0s)                                                                              |
| Electric smoke | Radius (both inner and outer) increased by 1 meter (50 -> 100, 210 -> 250), +33% faster recharge (18 -> 12 seconds)  |
| Arc grenade    | Radius (both inner and outer) increased by 1 meter (75 -> 125, 350 -> 400)                                           |
| Satchel        | Radius (both inner and outer) increased by 1 meter (120 -> 170, 250 -> 300)                                          |

#### Notes

  * Gravity star is still good if user aims more quickly, while being slightly less annoying for the victim.
  * Electric smoke and arc grenade have a slightly larger effect radius because their purpose is for area control, not direct damage. They could be higher, but increasing the size of the visual effect would require client mods.
  * Satchel has a radius buff as well to make it more like the bomb it's supposed to be

Development
--------------------------------------------------------------------------------

### Damage range to bullets needed for kill

Make changes based on how many bullets are needed for kill,
because that's most noticeable for the player.

| Damage range | Bullets to kill |
|--------------|-----------------|
| 100+         | 1               |
| 50 - 99      | 2               |
| 34 - 49      | 3               |
| 25 - 33      | 4               |
| 20 - 24      | 5               |
| 17 - 19      | 6               |
| 15 - 16      | 7               |
| 13 - 14      | 8               |
| 12           | 9               |
| 10 - 11      | 10              |
| 9            | 12              |
| 8            | 13              |
| 7            | 15              |
| 6            | 17              |
| 5            | 20              |
| 4            | 25              |
| 3            | 34              |
| 2            | 50              |
| 1            | 100             |


### Weapon code names

[Link](https://r2northstar.gitbook.io/r2northstar-wiki/hosting-a-server-with-northstar/dedicated-server#weapons)

### Harmony VPK tool

[Link](https://github.com/harmonytf/HarmonyVPKTool/releases/tag/1.2.0)

  1. Open `vpk/englishclient_mp_common.bsp.pak000_dir.vpk` in your Titanfall 2 install directory
  2. In the VPK, open:
     - `RootDir/scripts/weapons` for keyvalue files
     - `RootDir/scripts/vscripts/weapons` for Squirrel scripts
  3. Unpack the file somewhere on your PC
  4. Copy the file under `reference/` and:
     - `keyvalues/scripts/weapons`, if it's a keyvalue file
     - `mod/scripts/vscripts/weapons`, if it's a Squirrel script
  5. Leave the file under `reference/` as is, changes are made in `keyvalues/scripts/weapons` or `mod/scripts/vscripts/weapons`

### Change tracking

Use `./diffs.sh` or `./changes.sh` to track changes. You can also search for a single file
by passing a substring, eg.:

    $ ./changes.sh car

Make sure `./diffs.sh` includes only actual changes, not anything else (like whitespace changes and such).

### Editing

_Always_ keep `README.md` and [retouched.nut](./mod/scripts/vscripts/retouched.nut)
up-to-date with changes.

When editing a file under `keyvalues/scripts/weapons`, put a comment after the line explaining
the change like this:

  * `CHANGE/NERF: old value -> new value (explanation)`, if it's a nerf
  * `CHANGE/BUFF: old value -> new value (explanation)`, if it's a buff

Example:

```
"damage_near_value"     "14" // CHANGE/NERF: 25 -> 14 (4 -> 7 bullets)
"damage_far_value"      "10" // CHANGE/NERF: 13 -> 10 (7 -> 10 bullets)
"damage_very_far_value" "8"  // CHANGE/NERF: 10 -> 8 (10 -> 12 bullets)
```
