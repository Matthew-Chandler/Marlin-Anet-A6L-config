## A brief history of this repository, firmware, and the 3D-printing hobbyist world

Back in 2019, when Marlin was the most popular custom firmware distribution for personal 3D-printers, there was no public template configuration file for the Anet A6-L, a niche but still quite mainstream 3D-printer model. Anet A6-L owners typically either had to stick with the poor and sometimes dangerous stock firmware, which lacked built-in thermal runaway protection (yes, this actually used to be the norm for stock firmware), or flash the default Anet A6 Marlin configuration, giving up the A6-L's auto-levelling capability. I altered the marlin config for Marlin 1.1.9 and uploaded this code to Github at the time.

Since then, 3D printer firmware has advanced a long way, and **_this repo is essentially obsolete._** Marlin is now onto version 2.1, and with the emergence of Klipper, OctoPrint, and decent proprietary firmware becoming commonplace, Marlin isn't almost synonymous to owning a personal 3D-printer anymore.

Rarely does anyone buy Anet printers either now. The Anet A8, once loved for its ability to be endlessly modded, has since lost its crown for most popular hobbyist 3D-printer to the Creality Ender 3, due to its much better out-of-the-box capabilities and often better price. The COVID-19 pandemic had a profound impact on the hobbyist 3D-printing world, as the market was flooded by scores of 3D-printing beginners looking for a printer that was both cheap and reliably worked, the latter of which coud typically only be achieved from Anet printers after extensive maintenance and modding. 

Similar to how Windows eventually came to dominate other operating systems in the 1980s and 90s, it turns out that most people (very reasonably) would prefer something that "just works" -- no unintuitive errors, no fancy configurations required, and no extremely terse support.

## Documentation

Reminiscing aside, this code still does work for Marlin 1.1.9. Based on where the probe lies on your Anet A6-L relative to the nozzle, you may have to the change the following lines in Configuration.h:
```
//ANET A6 with BLTouch/3D-Touch mounted right to the nozzel
#define X_PROBE_OFFSET_FROM_EXTRUDER 39 // X offset: -left  +right  [of the nozzle]
#define Y_PROBE_OFFSET_FROM_EXTRUDER  0 // Y offset: -front +behind [the nozzle]
#define Z_PROBE_OFFSET_FROM_EXTRUDER  0 // Z offset: -below +above  [the nozzle]
```
The numbers refer to the distance in milimeters that the probe is offset releative to the nozzle. To think of a time when the most popular firmware in the world for 3D-printers could have typos in its comments.
