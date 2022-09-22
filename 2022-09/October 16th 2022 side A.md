# Flipper Zero developer Q&A
### October 16th 2022 (Side A)

Audio: []()  
Recorded and transcripted by [`djsime1`](https://dj.je).  
**NOTE:** The transcription of questions and answers may contain errors, take it all with a grain of salt.

### Week in review:
> - FAP (SD card) app loading has been merged into the firmware!
> - Build tool updated to support compilation of apps.
> - Automated API versioning system added to guarentee app compatibility.

### When will Canada get a restock?
> October.

### Is there documentation for the SD card filesystem structure?
> Generally speaking all apps work in the folder with the same name, and inside of those the assets folder typically holds settings.

### When I plug in the WiFi dev board, the LED turns red. What’s going wrong?
> This is intentional. The dev board ships with debugging firmware, and the red lights indicates it’s ready to start a debugging session. If you want to use the WiFi dev board for other purposes, check out community resources.

### What was inspriation for Flipper Zero?
> Why carry many devices in your backpack when you can just carry one?

### Whats the manufacturing cost of the device?
> Depends on scale, more costs less. Can’t expose exact numbers.
> - 1/3rd is hardware cost, remaining 2/3rds goes elsewhere.

### In the future, are you planning to bring out a second revision?
> There’s plans for a Flipper Zero Rev 2, Flipper One, and Flipper Nano.
> - Nano will be announced in Winter, but didn’t I just announce it here now?

### Is it worth waiting for the second revision of the Flipper Zero?
> Mk.2 is still under development and won’t be ready for around a year and a half.

### Is there a visible roadmap anywhere for future releases?
> Yes, it’s located in the main firmware repository. Additionally, there’s numerous Miro boards that visualize future plans.

### WIll the PayPal interruptions affect shipping?
> No.

### At any point in the near future, is the Flipper Team interested in social media promotors?
> Yes.
> - i.e. testimonials of good use, like returning a lost tagged pet to its owner.

### Will qFlipper allow updates via update packages instead of DFU?
> It’s possible.

### Will it be possible to write apps in different languages? (Such as Rust)
> If you can get it working, then yes. However, it won’t be officially supported.

### What will be included in future API’s?
> All of FURI, some FreeRTOS primatives (such as streams), and basically all libraries/services.

### Will I be able to write NFC in the future?
> Yes, most types of NFC tags (Except DESFire and EMV) will be able to be written by Flipper.

### If I get someone’s Tesla card, can I unlock their car?
> No, the cards can not be cloned since they are EMV-based.
> - Universal remote for AC is on the way

### Would it be possible to have the Flipper Zero act as a USB NFC scanner?
> For the forseeable future, no this won’t be possible.
> - ArduBoy games might be able to be loaded on Flipper

### Would it be possible to use the Flipper as a Thumbdrive via the USB? Is this on the roadmap?
> Since the SD card is accessed in SPI mode, transfer speeds are painfully slow in USB use cases. The idea has been long abandoned.

### Is there a limit to how many times you can flash the flipper firmware? Will the flash chip wear out at some point?
> Chip spec guarentees 10k write operations, however nobody (even heavy developers who flash constantly) have experienced any issues. A stress test of ~40k cycles has been conducted without issue as well.
> - SD card app loading means you’ll have to flash much less.

### Why do some NFC cards start a dictionary attack?
> This occurs when reading a Mifare Classic. Just leave the device on the card and it will eventually complete.
> - Potentially add a warning before dict. attack starts to inform user why its taking so long?

### What is diff between R01 R02 and R03? Is it firmware or hardware or software?
> They used to be relavant before the new provisioning system was added, but now it’s all obselete.

### How do I read a chipped pet’s tag?
> RFID App, extra actions, read ASK.

### Is it possible to brick a NFC implant while running a dictionary attack?
> Not if it’s NFC, potentially if it’s RFID.

### Can the sending device be determined from a SubGHz or IR signal?
> No.

### Is it possible to interact with FM/AM radio?
> No, hardware only supports digital signals.
> - Flipper one will be SDR
