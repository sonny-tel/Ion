
![image](https://github.com/user-attachments/assets/bedb5003-56c8-4eb8-8e33-fa2e4cec5c24)
<h1 align="center">Ion</h1>
<p align="center"><strong>
<a href="https://github.com/sonny-tel/Ion/releases/latest">Download</a> | <a href="https://thunderstore.io/c/northstar/p/r2ion/Ion/">Thunderstore</a> | <a href="https://discord.gg/UhPwruvSFH">Discord</a>
</strong></p>

This is a Northstar fork for Titanfall 2, which unlike Vanilla+ lets you play Northstar and Vanilla at the same time. 

Along with this it attempts to provide a substitute for the Origin social features that allowed you to join your friends' parties and also somewhat attempts to polish up a variety of things I felt were kind of dated. Most fairly opinionated changes have modifiable things in mod settings, however if you're bothered by something and feel it should be customisable let me know.

If you find any bugs please open an issue at [https://github.com/sonny-tel/Ion](https://github.com/sonny-tel/Ion), or you can message me directly (@sonny.tel) on discord or in the [Official Discord Server](https://discord.gg/UhPwruvSFH)

## Instructions

You can grab a copy from the [releases](https://github.com/sonny-tel/Ion/releases/latest) page.

Installation is basically the same as regular Northstar, just follow their manual install instructions [here](https://docs.northstar.tf/Wiki/installing-northstar/manual-installation/#installing-northstar). If you have an existing Northstar install, you might want to backup and delete/move any files in R2Northstar/mods or R2Northstar/packages, as there's a chance there might be problems.

#### Recommended: Add -northstar launch argument
If you own the game via steam, right click on Titanfall 2, then hit "Properties" and add `-northstar` to the "Launch Options" field
For EA App users, click on Titanfall 2 on the left side, then hit the "Manage" button, then "View properties" and add `-northstar` to the "Advanced launch options" box

## Modding
If you find any mods that don't work you can open an [issue](https://github.com/sonny-tel/Ion/issues), please document any script errors in the console or logs I'll look into making compatability patches.

Parity is mostly in touch with Northstar, versioning and mod names are the same. Any existing mods using UI script stuff that do `#if VANILLA` probably won't work but that's about it.

In order to check for vanilla in script you should use `NSIsVanilla()` which returns a bool. You'll have to make a guard to check if the function exists for proper Northstar/Ion compatability, so good luck with that.

Ion also introduces a variety of extra script functions for handling demos and raw input. If anyone actually cares about this let me know and I'll document it somewhere.

For mods making Keyvalue patches, special preprocessors have been added. You can use `///if VANILLA`, `///if NORTHSTAR` and `///endif` (no `///elif` or `///else` yet sorry). Here's a provided example below

```
// example basically just ripped out of Northstar.Custom ( you can also use ///if VANILLA ) but there's no ///else or ///elif
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

* [Allusive](https://github.com/AllusiveWheat) for doing a lot of work especially with friend presence and CI, I would not have bothered otherwise, super cool stuff.
* Northstar for inspiring me to stick it to the man and waste my time on this terrible game still after how many years
* Ado_ for making all the cool cover art for this. They have a [SteamGrid](https://www.steamgriddb.com/profile/76561199101934933) profile which has stuff for this project which you can check out.

![bear](https://github.com/r1delta/r1delta/assets/37985788/41548f20-0878-4e1e-8538-e9be808fc363)
<img src="https://github.com/user-attachments/assets/121a9ec2-cba9-4fac-96e0-06472febeb52" align="left">

