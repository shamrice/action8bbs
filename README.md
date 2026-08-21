# Action 8 BBS

Atari 8bit ATASCII BBS written in Action! for the Fujinet or an XM301 modem.

## Connecting to live BBS
BBS is live on weekends (and some times during the week). It runs on my stock 800XL.

**Connect info:**
actbbs.ddns.net:6502

## Setting up
* Action! Cartridge
* Sources on D1 with DOS files copied over.
* Blank data disk in D2
* Compile and run SETUPBBS to initialize all necessary data files
* Complie and run ACTBBS to start the BBS

**Note 1:** Drive numbers are currently hard code to sources in D1 and data in D2. If you want to use different drive numbers, you'll need to edit the source code.

**Note 2:** You can also compile the setup and main BBS program to a binary executable and run that way instead of running from inside of Action. As of Run #6, adding SYS.ACT causes the standalone compile to error out due to lack of symbol space. (Will attempt to address at a later date...)

**Alternate Setup**
* Mount the source files on D1
* Mount a blank formatted disk in D2
* Mount Action disk on D3

## Dial Up Modem Mode or Fujinet Mode

You can switch listening connection types between wifi on the Fujinet and a dial up modem by swapping between the NETFUJI.ACT and NETMODEM.ACT include files at the top of the ACTBBS.ACT source file. You *cannot* compile with both of these modules at the same time.

NETMODEM was written for the Atari XM301 modem that connects via the SIO port. It also requires that you load the modem handler via DOS before running. I usually copy the handler to AUTORUN.SYS so that it is loaded automatically at start up.

Running in Fujinet mode does not require any external handler to be set up before starting the BBS.

## Running

After the BBS is started, there's no really anything to do on the local computer. It will sit there waiting for connections and handle them as they come in (one call at a time). The local computer output is only currently used for debug data. The BBS cannot currently be interacted with via the local computer and must be interacted by calling into it.

If a crash happens, the BBS can be recompiled and restarted from within Action. If it is a bad enough crash, it may require that the computer is power cycled to restart.

BBS is started by default on port 6502 at your Fujinet's IP address. This can be changed if needed in the NETFUJI.ACT source file.

## Work in progress!

This is **very much** a work in progress and this repo will most likely not contain the latest code (it's a manual process to get it over to GitHub). I'll try to keep it up to date as possible with each release. Expect bugs, oddities, crashes, bad code, etc for the time being! :)


## How to connect

You will need a terminal program capible of viewing/connecting to an ATASCII BBS. If you're using real hardware, BobTerm or any other terminal program should work fine. If you're on modern hardware, here are a few options:
* ATC - AtConnect 3 - Windows only : https://www.southernamis.com/atconnect
* MuffinTerm - Mac only : https://muffinterm.app/
* SyncTerm - Windows/Linux/Mac : https://syncterm.bbsdev.net/

## Additional Credits

The basics of the NETFUJI.ACT library is based on the NIO.ACT library created by Thom Cherryhomes. The original library can be found here: https://github.com/FujiNetWIFI/fujinet-apps/blob/master/netcat-action/NIO.ACT

## Additional Notes

The source files are currently uploaded after each version is released using the Fujinet printer to ASCII. This causes some ATASCII chars or inverted text in the original strings to be removed. The .ATA screens are printed using the 'raw' option so they should *hopefully* be true to the originals (untested).
