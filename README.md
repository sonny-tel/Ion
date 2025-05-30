
![image](https://github.com/user-attachments/assets/bedb5003-56c8-4eb8-8e33-fa2e4cec5c24)
# Ion

This is a Northstar fork for Titanfall 2, which unlike Vanilla+ lets you play Northstar and Vanilla at the same time.

Also contains a kitchen sink of other things I like because this started out as just my personal little thing to play on.

I don't know what the usage of this is, but if you want to get in touch you can message me on discord @sonny.tel or join the [r1delta discord](https://discord.gg/r1delta). 

## Instructions

#### 1. Make sure you've installed Northstar beforehand, this is a drop-in replacement

#### 2. Download the files
* DiscordRPC.dll 
* mods.7z 
* Northstar.dll
From the [Releases](https://github.com/sonny-tel/Ion/releases/latest) tab
(the 2 source code zip files are not needed)

#### 3. Go to your Titanfall 2 directory folder, 
If bought through EA APP, usually it's at "C:\Program Files\EA Games\Titanfall2"
If bought through Steam, either go to "C:\Program Files\Steam\steamapps\common\Titanfall2" 
OR go to Steam, right click the game in library, click on "Properties", click on "Installed Files" tab,
and then click on "Browse" on the right side, to get automatically thrown into the directory folder for the game

#### 4. Once in the Titanfall 2 directory folder 
Put the "Northstar.dll" file in the Titanfall 2 directory folder, and replace the existing one 
Put the "DiscordRPC.dll" file in the R2Northstar\Plugins folder, and replace the existing one

#### 5. Final Step for "mods.7z"
Go to R2Northstar/mods folder and remove the current folders from there if they are already present:
"Northstar.Client, Northstar.Coop, Northstar.Custom, Northstar.CustomServers"
Once the folders are removed, put extract the 4 folders from the "mods.7z" zip and place them in the same folder
that you removed the previous folders from, the R2Northstar/mods folder

#### 6. Add -northstar launch argument
If you own the game via steam, right click on Titanfall 2, then hit "Properties" and add `-northstar` to the "Launch Options" field
For EA App users, click on Titanfall 2 on the left side, then hit the "Manage" button, then "View properties" and add `-northstar` to the "Advanced launch options" box

#### 7. Everything is done
You can just launch the Vanilla game normally like before, this mod combines what is effectively Vanilla+ and Northstar,
so you can launch either modded Vanilla or Northstar from the main menu, enjoy

## Extras
* EMM inspired menu with cool stuff (taskinoz my goat).
* Cooler rich presence
* Rudamentary demo playback UI
* Loading progress
* Considerably less crashes than Northstar (also turned off script errors on client I have no idea why they don't do this)
* Some UI changes
* Lots of HUD gimmicks
* Match settings fixes

Most of these are off by default you can just ignore them if you don't care

## What I want to add
* Drivable demo cam would be cool but lazy
* GMod script error popup please dogecore when you gangstalk my profile can you add it from R1Delta
* migrateme and invite stuff since origin invites are gone
* Go through all the script/exploit-fix funcs with tracy and do some optimisations, perf seems a bit crap

## Parity and Some Issues Worth Note
Going forward, this project will keep versioning mostly in check with Northstar, mods will still be named Northstar.* so you can host
with Northstar players (Northstar.Custom being required and that).

Existing mods SHOULD work assuming they aren't anything that touch the UI, the VANILLA constant hopefully will behave on client and server script vms. If there are any issues please open an issue and I'll work on compatability patches.

The B3, Wingman Eite and Softball, along with some other weapons maybe depending on what they do in the future will be extremely wonky on Northstar servers, nothing I can do about that unless the server you're on is also running Ion. SNS and some other modes probably wont work for Northstar players if you're hosting from Ion, due to changes fixing this between Northstar and Vanilla. Personally, I hope in the future Northstar will be like wow this project is awesome and move all their weapon stuff to new files that don't add keyvalue stuff to the vanilla weapons, please do that.

## Build
You'll want to use the branch repositories, the steps should be basically the same as for normally building Northstar:
* [Mods](https://github.com/VITALISED/NorthstarMods/tree/ion)
* [Launcher](https://github.com/VITALISED/NorthstarLauncher/tree/ion)

## Credits
* Northstar for inspiring me to stick it to the man and waste my time on this terrible game still after how many years
* Knightfire-rdp for his pretty ok core banner indicator mod which I ~~stole~~ used for damage indicators.
* Also Knightfire-rdp for writing the installation instructions
* Ado_ for making all the cool cover art for this. They have a [SteamGrid](https://www.steamgriddb.com/profile/76561199101934933) profile which has stuff for this project which you can check out.
* Allusive for being weird
