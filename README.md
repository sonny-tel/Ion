# Ion

Extended, vanilla compatible Northstar fork (that means you can play on Northstar and Vanilla if you're wondering, revolutionary)

It is also a cool kitchen sink of random things I like, they're mostly disabled by default but you can go check them out.

## Extras
* Sort of EMM inspired menu with extra stuff
* Some rudamentary Demo playback UI
* Loading progress
* Some less crashes in places maybe
* Vanilla compat whilst maintaining security hooks
* Spruced up UI because it is very ugly (not done yet)
* Lots of HUD things.

## Why
They won't merge my Vanilla compatability PR :(

If you're a Vanilla+ user, this is also an upgrade since this fixes match settings, pretty baller

## Parity
Going forward, this project will keep versioning mostly in check with upstream Northstar, mods will still be named Northstar.* so you can host
with Northstar players (Northstar.Custom being required and that).

The `VANILLA` const has been deprecated, and has been replaced with `NSIsVanilla()`. This is still somewhat implemented but only really practical in Client and Server VMs.

For mod developers, an `ION_VER` const has been declared although this probably won't be too helpful, so you can also use `VANILLA` which is 2 instead of 1 if you want to use that instead. You'll also want to replace `Remote_RegisterFunction` with `NSRemote_RegisterFunction` to prevent out-of-sync disconnects since ideally all scripts can be compiled at once.

The B3, Wingman Eite and Softball, along with some other weapons will be extremely wonky on Northstar servers, nothing I can do about that unless the server you're on is also running Ion. SNS and some other modes probably wont work for Northstar players if you're hosting from Ion due to changes fixing this between Northstar and Vanilla.

## Build
You'll want to use the branch repositories, build steps should be basically the same as normal Northstar:
* [Mods](https://github.com/VITALISED/NorthstarMods/tree/ion)
* [Launcher](https://github.com/VITALISED/NorthstarLauncher/tree/ion)

## Credits
* Northstar for inspiring me to stick it to the man
* Knightfire-rdp for his pretty ok core banner indicator mod which I ~~stole~~ used for damage indicators.
