# Flipper Zero developer Q&A
### September 23rd 2022 (Side A)

Audio: [https://archive.org/details/flipperzero-qa-09232022-a](https://archive.org/details/flipperzero-qa-09232022-a)  
Recorded and transcribed by [`djsime1`](https://dj.je).  
**NOTE:** The transcription of questions and answers may contain errors, take it all with a grain of salt.

### Week in review
> - SD card app loading finally released!
> - SDK currently supports C language, C++ is coming. Rust may or may not be supported in the future as well.
> - C++ has been completely removed from the main firmware.
> - Work on a universal AC remote has begun.
> - Certain NFC transit cards can have their balance read.
> - PicoPass app has been added to official firmware distribution.
> - Basic dummy mode has been added in a MVP state.
> - qFlipper has been natively ported to M1 Mac.
> - qFlipper can update with bundles in addition to DFU's.

### How do we know when Flipper accessories are in stock?
> Unfortunately, you'll just have to check the page frequently.
> - Stock notifications might be added to the Flipper Discord bot.
> - Sometimes stock might be posted in the #updates channel.

### Any plans on releasing a qFlipper Flatpak?
> Currently no, but you're welcome to open a request issue on the qFlipper repo.

### Any tips for compiling applications?
> Read the docs included in the official firmware repo: https://github.com/flipperdevices/flipperzero-firmware/blob/dev/documentation/AppsOnSDCard.md

### Any plans on making Flipper available in more countries?
> Main Flipper store restocks twice a month on average, but regional vendors are being partnered with to offer Flipper via other sites or even in stores.
> - Official reseller for Europe is Lab401.
> - Flipper Zero will be sold on Amazon once enough units are stocked up.

### Is Flipper region-locked to the country of purchase?
> This used to be the case, but now region provisioning occurs based on your current location whenever you update your firmware.

### Is there a web UI for Flipper?
> Yes! my.flipp.dev works on Chromium-based browsers (Google Chrome, Microsoft Edge, Opera/Opera GX, Brave, and Vivaldi)
> - If you also have qFlipper installed, make sure it's closed before opening the website.
> - Also try https://flippermaker.github.io, it's community-made and works on mobile.

### Are SD card apps updated alongside firmware?
> Yes, official apps are updated when you update the firmware. Of course, you can also update them manually.
> - Official 'app repo' will be coming soon.

### Any plans to add a frequency spectrum analyzer?
> It's a topic of interest, but low priority. Pull requests are welcome!
> - Existing apps miss some edge-cases.
> - Hardware limitation makes it difficult to scan ranges of frequencies.

### Does the flipper have a optimal frame rate for animation?
> Nothing specific, just keep in mind pixels can't switch on and off instantly.

### Any updates on JS BadUSB interpreter?
> Still in backlog.

### When will the next US shipment go out?
> Next week.

### Should precautions be taken with using Flipper in extreme heat?
> Same general precautions as any other device with a battery, don't leave it in the sun.
> - Battery circuit has over-current, under/over voltage protections in place.
> - Also direct sunlight can damage the screen.
> - Internal temperatures can be read via the CLI command `power info`

### How's the battery life?
> It can last between a few days and a week depending on usage.
> - Hardware low power mode is being looked in to, which could improve battery life up to 3x.

### Any plan to store BadUSB exfiltrations on the SD card? (Mass storage emulation)
> Flipper interfaces with MicroSD via SPI, which is much slower but more power efficient than normal SD. While it's possible, proofs of concept have shown transfer speeds are extremely slow and thus won't be implemented.
> - Alternatives: Plug in a flash drive alongside Flipper, or utilize cloud storage.

### Is it possible to make a Flipper key logger?
> No, it can only act as a USB client.
> - Just buy an OMG cable or something.
> - Might be possible with wireless keyboards and NRF24 module

### How far can various signals be transmitted?
> - For IR expect 1x to 2x the distance of your normal remote.
> - SubGHz averages 30-50m, max observed is 100m.
> - BLE is approx 50m.
> - NFC has to be within a few inches/centimeters.
> - RFID is similar to NFC, perhaps a bit further in a few cases.

### Can a Bluetooth keyboard be paired for CLI use?
> No, CLI takes place over USB serial protocol.

### Will there be more Tamogatchi features in the future?
> Currently, the more use use Flipper the more you level up. Each of the 3 levels unlocks new desktop animations.
> - Flipper isn't legally allowed to use names like Tamogatchi.

### Can the CLI be used over GPIO instead of USB?
> No, USB is the only way to access the CLI currently.

### Why is Ameebo misspelled in the NFC app?
> It isn't. The 'typo' is very intentional, because Ninendo are in deep love with copyright.