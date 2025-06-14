
![image](https://github.com/user-attachments/assets/bedb5003-56c8-4eb8-8e33-fa2e4cec5c24)
# Ion

This is a Northstar fork for Titanfall 2, which unlike Vanilla+ lets you play Northstar and Vanilla at the same time.

Also contains a kitchen sink of other things I like because this started out as just my personal little thing to play on, so it's very opinionated.

I don't know what the usage of this is, but if you want to get in touch you can message me on discord @sonny.tel or join the [R1Delta discord](https://discord.gg/r1delta).

If you have any bugs please open an issue at [https://github.com/sonny-tel/Ion](https://github.com/sonny-tel/Ion)

## Instructions

Installation is basically the same as regular Northstar, just follow their manual install instructions [here](https://docs.northstar.tf/Wiki/installing-northstar/manual-installation/#installing-northstar). If you have an existing Northstar install, you might want to backup/delete any files in R2Northstar/mods, as there's a good chance there might be problems.

#### Recommended: Add -northstar launch argument
If you own the game via steam, right click on Titanfall 2, then hit "Properties" and add `-northstar` to the "Launch Options" field
For EA App users, click on Titanfall 2 on the left side, then hit the "Manage" button, then "View properties" and add `-northstar` to the "Advanced launch options" box

## Extras
* EMM inspired menu with cool stuff.
* Cooler rich presence with game invites
* Rudamentary demo playback UI
* Loading progress
* Considerably less crashes than Northstar (also turned off script errors on client I have no idea why they don't do this)
* Some UI changes
* Lots of HUD gimmicks
* Match settings fixes
* I honestly don't know someone can tell me

Most of these are off by default you can just ignore them if you don't care

## What I want to add
* Drivable demo cam would be cool but lazy
* GMod script error popup please dogecore when you gangstalk my profile can you add it

## Modding
Parity is mostly in touch with Northstar, versioning and mod names are the same. Any existing mods using UI script stuff that do `#if VANILLA` probably won't work but that's about it.

In order to check for vanilla in script you should use `NSIsVanilla()` which returns a bool. You'll have to make a guard to check if the function exists for proper Northstar/Ion compatability, so good luck with that.

For mods making Keyvalue patches, special preprocessors have been added. You can use `///if VANILLA`, `///if NORTHSTAR` and `///endif` (no `///elif` yet sorry). Here's a provided example

```
// basically just ripped out of Northstar.Custom
WeaponData
{
///if NORTHSTAR
    Mods
    {
        sns
        {
            explosion_damage "50"
            damage_near_value "50"
            damage_far_value "50"
            ammo_clip_size "1"
            projectile_launch_speed "7500"
        }
    }
///endif
}
```

## Build
You'll want to use the branch repositories, the steps should be basically the same as for normally building Northstar:
* [Mods](https://github.com/VITALISED/NorthstarMods/tree/ion)
* [Launcher](https://github.com/VITALISED/NorthstarLauncher/tree/ion)
* [DiscordRPC](https://github.com/sonny-tel/NorthstarDiscordRPC/tree/ion)

## Credits
* Northstar for inspiring me to stick it to the man and waste my time on this terrible game still after how many years
* Knightfire-rdp for his pretty ok core banner indicator mod which I ~~stole~~ used for damage indicators.
* Ado_ for making all the cool cover art for this. They have a [SteamGrid](https://www.steamgriddb.com/profile/76561199101934933) profile which has stuff for this project which you can check out.
* Allusive for being weird and helping me reverse some stuff among other things
