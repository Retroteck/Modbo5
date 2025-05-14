Disclaimer: This is advanced and I am not responsible for any damage to consoles or modchips. Proceed at your own risk.

OriginalModboFirmware.bin - Default unchanged Modbo 5 firmware.
NoLogoOriginalModboFirmware - No Matrix Logo at PS2 Startup.
fhLogo.bin - Foxhound Logo placed in PS2 Startup.
FOX.bin - FOX (MGS3) Logo placed in PS2 Startup.


The flash memory used in the video is a Winbond W25Q40CLSNIG. 

The Matrix PS2 Disc boot image starts at offset 0xE000 and ends at 0xEFFF.

Things to keep in mind if you plan to insert a custom image:

The image is a BMP rendered upside down and then displayed. The image hex data must be from a monochrome BMP with transparency, within the size specifications, and flipped vertically.

BMP notes:
256 colors, 128x32 grayscale (0,0,0) to (255,255,255) with the first entry in the palette being fully trasparent.

Repairing a Bad Flash:

Obtain a Good Dump:

Get a good dump of the flash contents from another modchip. For Modbo 5 like in the video, you can use the provided dump.

Flash the Replacement Memory:
Use a programmer of your choice to flash the replacement memory with the good dump. (I use Flashcat Xport with SOIC-8 Narrow Adapter, and the flash memory is Winbond W25Q40CLSNIG.)

Replace the Faulty IC:
Remove the faulty IC and replace it with the new good IC, paying very close attention to pin 1. For Modbo 5.0D, pin 1 will face the edge of the PCB. Incorrect installation will fry the Flash IC, rendering it useless.
Done!

While I have repaired two modchips with this method, the sample size is admittedly small. It's possible that other issues can cause a black screen. This is simply how I’ve fixed some and what I learned in the process.

You cannot increase the size of the flash I.e Using an 8 Mbit Flash in place of the original 4Mbit, even if the read/write commands and pinout are the same.
