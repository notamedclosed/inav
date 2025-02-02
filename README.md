
# INAV DJI RADAR

This fork is specifically dealing with implementing iNav Radar for use with the DJI FPV system.

If you are not familiar iNav Radar please check out the following RCGroups thread.
[RCGroups](https://www.rcgroups.com/forums/showthread.php?3304673-iNav-Radar-ESP32-LoRa-modems)

Radar was designed around analog. It currently does not work on stock iNav for the DJI FPV system.  For DJI we have to do things a little different, with this fork you get something that looks like this:
![RADAR](https://imgur.com/s4t1Z3Bl.jpg)

## HOW TO READ

The red circle was the aircraft we were following, the circle was added after.  Since DJI doesn't capture the OSD it is hard to show this process.

The DJI craft name will output something like the following string:

"A ↗ D11 A15"

A is the craft ID.  iNav Radar goes A-D based on start time.  First craft gets slot A, then B, etc.

↗ is the pointer to the target aircraft

D is the distance in 10's of your selected unit.  So Feet or Meters.  IE this shows 110 Feet.

A15 is the relative height (not working correctly).  No sign means above you, - is below you.  Then the relative height in your selected units.  So this is 15 feet.

Oliver_C is the original developer of iNav Radar.  He has nicely hosted some builds of 3.0.2 with the DJI fork available here.

[Dropbox](https://www.dropbox.com/sh/ib3ffejdk5hf90k/AAA7W8h9KnwxPtlQtectK-PGa?dl=0)

You can build iNav from this repository as well.  Refer to the developer documentation.

Once I've got 4.0.0 RC integrated and tested I'll put some builds up for 4.0.

Use at your own risk.  Code changes are available here, but have not been vetted or extensively tested.

Altitude is unreliable at this point.

## Installation steps

* Install the custom iNav build from the link above or build yourself (Don't do it on planes you aren't willing to risk)
* Setup iNav radar as per the RCGroups thread
* * Add ESP32 LORA module
* * Enable MSP on Lora port and speed of 115200
* * Important CLI steps to not miss:
* * set osd_hud_radar_disp = 3
* * set osd_hud_radar_range_min = 1
* Enable DJI craft name hack (3.0.2) and add "R".  So it looks like ":WR".  Adding more elements is not recommended as it takes too long to cycle.
* Fly with friends and have fun
* Report back if you have any problems or suggestions.

# - INAV DEFAULT TEXT AFTER THIS

# INAV - navigation capable flight controller

![INAV](http://static.rcgroups.net/forums/attachments/6/1/0/3/7/6/a9088858-102-inav.png)

# INAV Community

* [INAV Discord Server](https://discord.gg/peg2hhbYwN)
* [INAV Official on Facebook](https://www.facebook.com/groups/INAVOfficial)
* [RC Groups Support](https://www.rcgroups.com/forums/showthread.php?2495732-Cleanflight-iNav-(navigation-rewrite)-project)
* [INAV Official on Telegram](https://t.me/INAVFlight)

## Features

* Runs on the most popular F4 and F7 flight controllers
* Outstanding performance out of the box
* Position Hold, Altitude Hold, Return To Home and Missions
* Excellent support for fixed wing UAVs: airplanes, flying wings 
* Fully configurable mixer that allows to run any hardware you want: multirotor, fixed wing, rovers, boats and other experimental devices
* Multiple sensor support: GPS, Pitot tube, sonar, lidar, temperature, ESC with BlHeli_32 telemetry
* SmartAudio and IRC Tramp VTX support
* Blackbox flight recorder logging
* On Screen Display (OSD) - both character and pixel style
* DJI OSD integration: all elements, system messages and warnings
* Telemetry: SmartPort, FPort, MAVlink, LTM
* Multi-color RGB LED Strip support
* Advanced gyro filtering: Matrix Filter and RPM filter
* Logic Conditions, Global Functions and Global Variables: you can program INAV with a GUI
* And many more!

For a list of features, changes and some discussion please review consult the releases [page](https://github.com/iNavFlight/inav/releases) and the documentation.

## Tools

### INAV Configurator

Official tool for INAV can be downloaded [here](https://github.com/iNavFlight/inav-configurator/releases). It can be run on Windows, MacOS and Linux machines and standalone application.  

### INAV Blackbox Explorer

Tool for Blackbox logs analysis is available [here](https://github.com/iNavFlight/blackbox-log-viewer/releases)

### Telemetry screen for OpenTX

Users of OpenTX radios (Taranis, Horus, Jumper, Radiomaster, Nirvana) can use INAV OpenTX Telemetry Widget screen. Software and installation instruction are available here: [https://github.com/iNavFlight/OpenTX-Telemetry-Widget](https://github.com/iNavFlight/OpenTX-Telemetry-Widget)

## Installation

See: https://github.com/iNavFlight/inav/blob/master/docs/Installation.md

## Documentation, support and learning resources
* [Fixed Wing Guide](docs/INAV_Fixed_Wing_Setup_Guide.pdf)
* [Autolaunch Guide](docs/INAV_Autolaunch.pdf)
* [Modes Guide](docs/INAV_Modes.pdf)
* [Wing Tuning Masterclass](docs/INAV_Wing_Tuning_Masterclass.pdf)
* [Official documentation](https://github.com/iNavFlight/inav/tree/master/docs)
* [Official Wiki](https://github.com/iNavFlight/inav/wiki)
* [Video series by Painless360](https://www.youtube.com/playlist?list=PLYsWjANuAm4qdXEGFSeUhOZ10-H8YTSnH)
* [Video series by Paweł Spychalski](https://www.youtube.com/playlist?list=PLOUQ8o2_nCLloACrA6f1_daCjhqY2x0fB)

## Contributing

Contributions are welcome and encouraged.  You can contribute in many ways:

* Documentation updates and corrections.
* How-To guides - received help?  help others!
* Bug fixes.
* New features.
* Telling us your ideas and suggestions.
* Buying your hardware from this [link](https://inavflight.com/shop/u/bg/)

A good place to start is Telegram channel or Facebook group. Drop in, say hi.

Github issue tracker is a good place to search for existing issues or report a new bug/feature request:

https://github.com/iNavFlight/inav/issues

https://github.com/iNavFlight/inav-configurator/issues

Before creating new issues please check to see if there is an existing one, search first otherwise you waste peoples time when they could be coding instead!

## Developers

Please refer to the development section in the [docs/development](https://github.com/iNavFlight/inav/tree/master/docs/development) folder.


## INAV Releases
https://github.com/iNavFlight/inav/releases
