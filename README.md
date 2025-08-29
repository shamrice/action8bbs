# Action 8 BBS

Atari 8bit ATASCII BBS written in Action! for the Fujinet.

## Setting up
* Mount Action and DOS on D1
* Mount a blank formatted disk in D2
* Mount the source files on D3
* Compile and run SETUPBBS to initialize all necessary data files (todo: add ATASCII files to repo)
* Complie and run ACTBBS to start the BBS
  
**Note 1:** Drive numbers are currently hard code to sources in D3 and data in D2. If you want to use different drive numbers, you'll need to edit the source code.

**Note 2:** You can also compile the setup and main BBS program to a binary executable and run that way instead of running from inside of Action. (untested)

## Running

After the BBS is started, there's no really anything to do on the local computer. It will sit there waiting for connections and handle them as they come in (one call at a time). The local computer output is only currently used for debug data. The BBS cannot currently be interacted with via the local computer and must be interacted by calling into it.

If a crash happens, the BBS can be recompiled and restarted from within Action. If it is a bad enough crash, it may require that the computer is power cycled to restart.

BBS is started by default on port 6502 at your Fujinet's IP address. This can be changed if needed in the NETWORK.ACT source file.

## Work in progress!

This is **very much** a work in progress and this repo will most likely not contain the latest code (it's a manual process to get it over to GitHub). I'll try to keep it up to date as possible with each release. Expect bugs, oddities, crashes, bad code, etc for the time being! :)


## How to connect

You will need a terminal program capible of viewing/connecting to an ATASCII BBS. If you're using real hardware, BobTerm or any other terminal program should work fine. If you're on modern hardware, here are a few options:
* ATC - AtConnect 3 - Windows only : https://www.southernamis.com/atconnect
* MuffinTerm - Mac only : https://muffinterm.app/
* SyncTerm - Windows/Linux/Mac : https://syncterm.bbsdev.net/

## Additional Credits

The NETWORK.ACT library is a modified and expanded upon module based on the NIO.ACT library created by Thomas Cherryhomes. The original library can be found here: https://github.com/FujiNetWIFI/fujinet-apps/blob/master/netcat-action/NIO.ACT

