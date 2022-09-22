# Flipper Zero developer Q&A
### August 26th 2022 (Side B)

Audio: []()  
Recorded and transcripted by [`djsime1`](https://dj.je).  
**NOTE:** The transcription of questions and answers may contain errors, take it all with a grain of salt.

### Are there any plans of releasing replacement parts on iFixit or similar sources?
> In the future replacement parts will be sold via an online shop, but currently replacement parts can be purchased by opening a support ticket

### i think this was asked before, but as far as i remember there should be a Flipper Zero MK2 in future – how much of a hardware difference would be between MK1 and MK2?
> It’s going to be the hardware equiilent of a bugfix. Functionality and firmware wise, nothing should change.

### Is ELF loading the same as SD card apps?
> Yes, ELF is the technial name.

### is there any talks of updating the iButton app to support other models of Dallas iButttons like the DS1994?
> Currently nobody is working on the iButton application. If enough people request more protocols, then some work might be done. Alternatively, a pull request could be opened.

### The newest firmware supports raw rfid read. Can you tell a bit on how to look into the generated files?
> It’s a passive system that was intended to help the developers implimen support for reading more tag types.
> - It’s a binary format with special packet integers, support to view such files are coming soon.

### I saw some playground with JavaScript. Will this be supported in the FW?
> Yes, it will probably be the new BadUSB language.
> - JS was chosen because a tiny interperter was avilable.

### What can we expect from the “Speedup SD card & enlarge your RAM” change?
> The Pull Request makes more efficient use of memory between the CPU’s Cores. As for the SD card, reads will be cached as blocks to make future retrival quicker. Currently no write cache.

### Are bluetooth/wifi attacks that potentially use the ESP expansion board out of scope for the main firmware?
> (Insert limitations of Bluetooth stack and having to write your own ESP firmware here)

### What exactly goes over the subghz external debug pin and why did you add it?
> Sometimes when working on new tools, internal tools might not be enough. Thus, this was added to allow for external tools to analyze signals.

### Could someone explain the pins on the flipper.  They are pogo pins yes?   Are they soldered? Or sit in place?
> They’re soldered pogo pins, and can be replaced if needed.

### What’s the AMAP process that was recently added to GH Actions?
> AMAP is a static analysis tool that tracks how much space is allocated to code. PVS Studio anlyzes potentially dangerous code.
> - Currently all reported issues by both tools are being worked out. Once done, PR’s will have mandatory checks under these toos.

### Is there any project of integrating a magnetic strip reader on the next flipper ?
> During last year’s hackathon, someone actually made one. However, putting it into a portable external module was difficult.
> - Magstrip emulation is unofficially possible with RFID coil.
> - Python protobuf bindings are being worked on, this means you’ll be able to control Flipper via a Python library.

### Any plans on clear case?
> It’s coming, but no specific date yet.

### Since you said JS would probably be used for scripting. What can be scripted? Could I for example send various sub files after each other with it?
> Most likely yes, since it will have FFI bindings.

### with dynamic app loading, do you think it may be possible to reduce the size of the fw enough to have space for the the bluetooth+zigbee radio stack?
> Unfortuneately no. Zigbee by itself is really big (300 kb) and full bluetooth stack takes 200 kb. Since the firmware already takes up 600 kb, it’s nearly impossible to include both.

### other question about dynamic loading: (except for background services) will it be possible in theory to have all apps offloaded to SD? or are some features/API calls requiring some app code to be in the fw?
> Currently some apps are coupled to firmware libraries and can’t easily be put to SD card, while others can.

### would it be illegal to break this core 2 protection?
> (Go back and listen to recording)

### Many STM controllers have a FMC interface that lets you map external devices into your memory map. Does the current MCU support that maybe so you could add an external flash on further iterations?
> Flipper’s CPU has this capability, however there’s no free GPIO pins to map for this purpose.

### Ever thought about a mini version in a smartwatch form factor?
> Without huge comprimises, this isn’t possible.

### What are the purpose of the new files on internal flash?
> The internal flash stores mainly settings files, but also your Flipper's reigon-provisioned file (Necessary for Sub-GHz transmission)

### Now that reigon file is in internal flash, are you going to prevent external apps to prevent writing to it?
> There’s not going to be any documentation on the file format.