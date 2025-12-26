
![image](https://github.com/user-attachments/assets/bedb5003-56c8-4eb8-8e33-fa2e4cec5c24)
<h1 align="center">Ion</h1>
<p align="center"><strong>
<a href="https://github.com/sonny-tel/Ion/releases/latest">Download</a> | <a href="https://thunderstore.io/c/northstar/p/r2ion/Ion/">Thunderstore</a> | <a href="https://discord.gg/UhPwruvSFH">Discord</a>
</strong></p>

This is a Northstar fork for Titanfall 2 which adds a variety of enhancements for Vanilla and Northstar.

Some of the notable features Ion includes are:

* **Vanilla/Northstar compatability at runtime** - you don't have to restart to switch between playing them, along with this Northstar client-server mods will work better on Vanilla and (hopefully) shouldn't have issues.
* **Peer-to-Peer** - Join your friends' Northstar matches locally without having to port-forward. This uses Epic Online Services and is optional.
* **Sonny Auto-Downloader** (SAD) (name subject to change) - an overlay mod downloader ontop of Northstar's existing mod downloader that allows clients to download unverified remote mods from servers
* **Full UI redesign of Northstar** - most menus have had a considerable facelift and some annoying UX issues such as the lack of smooth scrolling have been fixed up
* **Legacy Origin social features** - join your friends' parties without needing EA invites
* **Other fun miscellaneous things which are cool** - Loading progress bars, gimmicky mod settings to play with, demo playback helpers and other stuff which I honestly can't remember for you to go find.

If you find any bugs please open an issue at [https://github.com/sonny-tel/Ion](https://github.com/sonny-tel/Ion), or you can message me directly (@sonny.tel) on discord or in the [Official Discord Server](https://discord.gg/UhPwruvSFH)

## Instructions

You can grab a copy from the [releases](https://github.com/sonny-tel/Ion/releases/latest) page.

Installation is basically the same as regular Northstar, just follow their manual install instructions [here](https://docs.northstar.tf/Wiki/installing-northstar/manual-installation/#installing-northstar). If you have an existing Northstar install, you might want to backup and delete/move any files in R2Northstar/mods or R2Northstar/packages, as there's a chance there might be problems.

#### Recommended: Add -northstar launch argument
If you own the game via steam, right click on Titanfall 2, then hit "Properties" and add `-northstar` to the "Launch Options" field
For EA App users, click on Titanfall 2 on the left side, then hit the "Manage" button, then "View properties" and add `-northstar` to the "Advanced launch options" box

## Hosting
You can get the Ion docker image at: [ghcr.io/sonny-tel/northstar-dedicated](https://ghcr.io/sonny-tel/northstar-dedicated)

If you're not interested in using any of the features offered you can still benefit from using this image as opposed to the official one since it runs a much newer Alpine Linux image with Wine 10, which lets you run Northstar plugins.

Servers running Ion can send unverified mods to clients to download. Some notes on this:
* Northstar auto-downloads are preferred if the name and version match
* Sonny Auto-downloader will download all mods in the schema, even if they aren't sent to the master-server as a required mod (this can let you have optional client mods if you don't want a fully 100% ion playerbase server).

To create a schema, create a file called `servermodschema.json` in the root of your profile folder (e.g Titanfall2/R2Northstar)

Here's an example schema that will download Titanframework to your clients

### Option A: Direct URL
```json
{
    "Peepee.TitanFramework": {
        "Version": "2.4.3",
        "URL": "https://gcdn.thunderstore.io/live/repository/packages/The_Peepeepoopoo_man-Titanframework-2.4.3.zip",
        "Checksum": "6d075d2f7a5764627f949cc757e5e034c528fb4711777a364cb1f788b694ff3a"
    }
}
```

### Option B: Thunderstore dependency string resolution
```json
{
    "Peepee.TitanFramework": {
        "Version": "2.4.3",
        "Platform": "thunderstore",
        "DependencyString": "The_Peepeepoopoo_man-Titanframework-2.4.3",
        "Checksum": "6d075d2f7a5764627f949cc757e5e034c528fb4711777a364cb1f788b694ff3a"
    }
}
```

## Modding
If you find any mods that don't work you can open an [issue](https://github.com/sonny-tel/Ion/issues), please document any script errors in the console or logs I'll look into making compatability patches.

Parity is mostly in touch with Northstar, versioning and mod names are the same. Any existing mods using UI script stuff that do `#if VANILLA` probably won't work but that's about it.

In order to check for vanilla in script you should use `NSIsVanilla()`

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

## Hosting

### P2P

You can use P2P after accepting the EOS agreement, restarting your game and going into a private match. Send the address to your friends which they can use to connect from "Direct Connect" in the server browser.

### Dedicated

You can get the Ion docker image at: [ghcr.io/sonny-tel/northstar-dedicated](https://ghcr.io/sonny-tel/northstar-dedicated)

Servers running Ion can send unverified mods to clients to download. Some notes on this:
* Northstar auto-downloads are preferred if the name and version match
* Sonny Auto-downloader will download all mods in the schema, even if they aren't sent to the master-server as a required mod (this can let you have optional client mods if you don't want a fully 100% ion playerbase server).

To create a schema, create a file called `servermodschema.json` in the root of your profile folder (e.g Titanfall2/R2Northstar folder)

Here's an example schema that will download Titanframework to your clients

### Option A: Direct URL
```json
{
    "Peepee.TitanFramework": {
        "Version": "2.4.3",
        "URL": "https://gcdn.thunderstore.io/live/repository/packages/The_Peepeepoopoo_man-Titanframework-2.4.3.zip",
        "Checksum": "6d075d2f7a5764627f949cc757e5e034c528fb4711777a364cb1f788b694ff3a"
    }
}
```

### Option B: Thunderstore dependency string resolution
```json
{
    "Peepee.TitanFramework": {
        "Version": "2.4.3",
        "Platform": "thunderstore",
        "DependencyString": "The_Peepeepoopoo_man-Titanframework-2.4.3",
        "Checksum": "6d075d2f7a5764627f949cc757e5e034c528fb4711777a364cb1f788b694ff3a"
    }
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
* Hammer
* [dyslexi](https://github.com/Dys-lexi/) 👍
* british man

![bear](https://github.com/r1delta/r1delta/assets/37985788/41548f20-0878-4e1e-8538-e9be808fc363)
<img src="https://github.com/user-attachments/assets/121a9ec2-cba9-4fac-96e0-06472febeb52" align="left">

