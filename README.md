# Ion

Extended and Vanilla compatible Titanfall 2 Northstar fork, which unlike Vanilla+ actually lets you play Northstar and Vanilla at the same time, and without a completely scuffed experience.

If you're a Vanilla+ user, this is also an upgrade since this fixes match settings, pretty baller. If you don't want the full experience you should still use the provided Northstar.dll, although this is not recommended by itself and probably has some security holes if run on it's own.

This is also a cool kitchen sink of random things I like, because this project started out as a personal quality of life project, they're mostly disabled by default but you can go check them out.

## Extras
* Sort of EMM inspired menu with extra stuff
* Some rudamentary Demo playback UI
* Loading progress
* Some less crashes in places maybe
* Vanilla compat whilst maintaining security hooks
* Spruced up UI because it is very ugly (not done yet)
* Lots of HUD things.

## Parity and Some Issues Worth Note
Going forward, this project will keep versioning mostly in check with upstream Northstar, mods will still be named Northstar.* so you can host
with Northstar players (Northstar.Custom being required and that).

The `VANILLA` const has been deprecated, and has been replaced with `NSIsVanilla()`. The const is still somewhat implemented but only really practical in Client and Server VMs, and is NOT recommended to use at all in UI script except maybe to detect if Ion is installed (see below).

For mod developers, an `ION_VER` const has been declared although this probably won't be too helpful, so you can also use `VANILLA` which is 2 instead of 1 if you want to use that instead (`#if VANILLA == 2` *should* work). I'm not entirely sure how this would work in theory so please reach out if this is a stupid approach. You'll also want to replace `Remote_RegisterFunction` with `NSRemote_RegisterFunction` to prevent out-of-sync disconnects since ideally all custom server scripts can be compiled at once and be vanilla compatible.

The B3, Wingman Eite and Softball, along with some other weapons maybe depending on what they do in the future will be extremely wonky on Northstar servers, nothing I can do about that unless the server you're on is also running Ion. SNS and some other modes probably wont work for Northstar players if you're hosting from Ion, due to changes fixing this between Northstar and Vanilla. Personally, I hope in the future Northstar will be like wow this project is awesome and move all their weapon stuff to new files that don't add keyvalue stuff to the vanilla ones, please do that.

## Build
You'll want to use the branch repositories, the steps should be basically the same as for normally building Northstar:
* [Mods](https://github.com/VITALISED/NorthstarMods/tree/ion)
* [Launcher](https://github.com/VITALISED/NorthstarLauncher/tree/ion)

## Credits
* Northstar for inspiring me to stick it to the man and waste my time on this terrible game still after how many years
* Knightfire-rdp for his pretty ok core banner indicator mod which I ~~stole~~ used for damage indicators.
