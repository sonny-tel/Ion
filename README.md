# Ion

Extended, vanilla compatible Northstar fork (that means you can play on Northstar and Vanilla if you're wondering, revolutionary)

It is also a cool kitchen sink of random things I like, they're mostly disabled by default but you can go check them out.

## Extras
* Sort of EMM inspired menu
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

The `VANILLA` const has been stripped, and has been replaced with `NSIsVanilla()`. This may be reimplemented in the future but only to Client and Server VMs for compat depending on demand.

For mod developers, an `ION_VER` const has been declared if you'd like parity across forks. You'll also want to replace `Remote_RegisterFunction` with `NSRemote_RegisterFunction` to prevent out-of-sync disconnects.

The B3, Wingman Eite and Softball, along with some other weapons will be extremely wonky on Northstar servers, nothing I can do about that unless the server you're on is also running Ion. SNS and some other modes probably wont work for Northstar players if you're hosting from Ion due to changes fixing this.

## Build
You'll want to use the branch repositories, build steps should be basically the same as normal Northstar:
* [Mods](https://github.com/VITALISED/NorthstarMods/tree/ion)
* [Launcher](https://github.com/VITALISED/NorthstarLauncher/tree/ion)

## Credits
Northstar for inspiring me to stick it to the man
Knightfire-rdp for his pretty ok core banner indicator mod which I used for damage indicators.
