# Flipper Zero developer Q&A
### September 9th 2022 (Side A)

Audio: [https://archive.org/details/flipperzero-qa-09092022-a](https://archive.org/details/flipperzero-qa-09092022-a)  
Recorded and transcripted by [`djsime1`](https://dj.je).  
**NOTE:** The transcription of questions and answers may contain errors, take it all with a grain of salt.

### Week in review
> - SD card app loading delayed until next release.
> - RFID app has been converted to C.
> - API's may change frequently until version 1.0.
> - External libraries can be linked in apps.
> - RFAL is being phased out in favor of FURI HAL.

### How is Mifare Classic emulation being worked on?
> Due to NXP's closed ecosystem, the NFC chip doesn't have native hardware support for Mifare Classic emulation. Instead, all the emulation has to take place via software in Flipper's firmware.
> - Flipper is doing the best it can to emulate.
> - Typically emulation issues are due to the reader being off-timing.
> - If emulation isn't working, consider sending your debug logs/pcap file to one of the NFC developers.

### Is it possible to fully and save and emulate a credit/debit card in any way, shape, or form?
> No. What you see when scanning one is the extent of what Flipper is able to read from it.
> - Technically speaking, those cards are micro-sized computers. They only talk to payment terminals.

### News on September restocks?
> Every month brings 2 store restocks, production is running 24/7. Next restock is close to the end of September.
> - Flippers are coming to Amazon soon™

### Can AirDrop's be sent from Flipper?
> No, for many reasons that are too complicated to explain here.
> - Long story short: The reason it doesn't work on Android is the same reason it's not possible on Flipper.

### What is PicoPass?
> It's a type of NFC tag produced by HID for their iCLASS readers. A separate plugin was made to read and write the tags.

### Are there any plans for official firmware to support saving rolling codes?
> The official firmware can actually recognize rolling codes, however allowing users to save them presents a lot of issues.
> - Besides the potential legal misuse, you'd probably desync your original keyfob.

### Could your turn off the motion sensor inside a Ring doorbell with Flipper?
> Simply isn't possible.
> - You might be able to break the lens glass if you throw your Flipper at it hard enough! (This is obviously a joke.)

### When is the Flipper One coming?
> It's still in the prototyping stage, currently researching SDR options.

### State of SD card app loading?
> Mostly working and ready, will be in release candidate very soon.

### Is support for other keyboard layouts coming to BadUSB?
> There's a few pull requests that address this, but they're on pause until SD app loading is finished.
> - It's not possible to auto-detect what layout a computer is using.

### Is RPC over hardware UART coming?
> Can't be easily done, but it would be useful for future hardware modules.

### Have you seen any integration into an OBD2 port from Flipper?
> Not possible using just Flipper, but a external module could implement the communication protocol.

### Why can't I access files located outside their intended folders from the mobile app?
> This is a known bug, it will be fixed in some future release.
> - Alternatively, use the mobile app's "File Browser" menu to manually browse Flipper's filesystem.

### On Flipper One and future hardwares, can we get mounting points for external modules?
> The GPIO soldered joint is pretty strong, but this question will be taken into mind.

### What can the CLI do?
> If you connect to Flipper over serial, you can access a command-line interface. It's also where logs can be found.
> - It's not Bash or any other typical shell, it's Flipper-specific.

### Can I buy individual replacement parts/components for Flipper Zero?
> Plans are in the works, could be ready in a few months.
> - It will probably be sold through a site like iFixit.
> - If your device is currently broken, contact support for replacements.

### Why aren't pull request getting merged?
> They're mostly delayed until SD app loading is merged.

### How will SD apps be distributed?
> The most important apps (like PicoPass) will be merged into official firmware distributions, while an official app repository will be opened for everything else.
> - It will integrate with the mobile apps.

### If I have a radio license, can I unlock transmission on extra frequencies?
> Officially, not yet. Flipper was designed to follow regulations first.
> - The introductions of provisioning files might allow this in the future.
> - Work is being done on allowing more transmission frequencies by default in some countries.
