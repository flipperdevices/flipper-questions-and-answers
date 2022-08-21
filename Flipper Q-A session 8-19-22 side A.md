# Flipper Zero developer Q&A
### August 19th 2022
Audio:  [https://archive.org/details/httpsarchive.orgdetailsflipperzero-qa-08192022-a](https://archive.org/details/httpsarchive.orgdetailsflipperzero-qa-08192022-a).
Recorded and transcripted by [`djsime1`](https://dj.je).  
**NOTE:** The transcription of questions and answers may contain errors, take it all with a grain of salt.

### Week in review:
> - Very successful week
> - Deployed region provisioning (More grannular than old 3 reigons)
> - RFID redesign finished (Now supports animal tags)
> - SD Card app loading is still being worked on (Released in a week?)

### How does this new reigon provisioning affect old Flippers?
> The old system will be overrided and will work like new devices.

### How do I change my device's reigon?
> Currently it is done during while upgrading the Firmware from qFlipper or mobile app.
> - When upgrading firmware from SD card, nothing is changed.
> - Factory reset will wipe reigon provisioning

### Do VPN's affect reigon provisioning?
> Yes and no. Data is acquired from multiple sources (SIM card reigon, IP geolocation, etc.)
> - Most VPNs will not be counted as a valid source.
> - Percise location is NOT used.

### Is there a getting started guide to control GPIO?
> Official documentation & SDK is coming after version 1.0.
> - In the mean time, [https://github.com/mfulz/Flipper-Plugin-Tutorial](https://github.com/mfulz/Flipper-Plugin-Tutorial) is a good guide on how to make an app.

### As someone coming from TikTok, what is the stance on people opening Tesla charging ports and similar things?
> It's not endorsed nor condoned, yet end users won't be stopped from doing it.

### Is Flipper illegal?
> No. The device has certifications and stock firmware is compliant with local regulations.
> - Think of it like a knife: You can use it properly to cut food, or illegally to stab someone.

### Will devices be shipped to South Australia?
> Yes. Australian Customs are causing delays.

### Is there a possibility of adding Rust as a supported language?
> In the beginning it was considered, but in the end C was chosen for being more efficient.
> - It should be possible to use in third party firmware/apps

### When will mfkey32v2 (Mifare Classic reader attack) be part of firmware/mobile app?
> It's scheduled for the next sprint (2 weeks) and should arrive some time after that.

### How does the companion app interface with the Flipper and what are the benefits of it?
> RPC (Remote Procedure Call) is used to send commands and responses between devices.
> - This API will be opened up to developers

### What kind of usage data is pulled from the app, and how specific is it?
> General anonymous metrics (what parts of the app are being used, what caused the app to crash) are sent.
> - Again, reigon provisioning doesn't send location data back to Flipper servers.

### Looking into new LF RFID system GUI and part of app still in C++, but recently Infrared app was rewritten in plain C. So is there a reason why it should stay in C++ or rewrite is planned for next time, after this PR merged and protocols got all testing?
> After the current pull request is merged, the app will be rewritten in C. (Update .66 or .67)

### How does Flipper to Flipper communication work?
> Currently, this is only done as part of Sub-GHz chat over CLI.
> - A system like the 3DS's StreetPass is slowly being worked on. 
> - Antenna isn't very powerful, 20-30 meters at best.
> - Flipper One status:
> - Baseboard is being designed
> - It will have an SDR radio, probably LoRA too.
> - Current challenge is managing power and dissapating heat.
> - More time will be spend after FZ 1.0 firmware is released.

### Can 8-byte NFC UID's be emulated?
> No, it's impossible. It's unsupported by (current) Flipper's NFC chip. 

### What about NFC-V?
> Should be possible to read and write, but not emulate.

### And Felica?
> Support is being looked in to.

### When it came to choosing SMT32 M4, what made it the chosen one? If the RP2040 was avilable in the begining, would you have chosen it?
> STM32 was chosen due to "madness." It was a bargan between new chips (and their blackbox radio stack) and L4 series chips. Overall, there were not many other good options besides WB series.
> - In hindsight, WB wasn't a good choice due to locked down radio stack firmware.

### Will duckyscript be updated to 3.0?
> Flipper was designed before DS 3.0 when there was no licensing policies to use DS 1.0. Internal communications are going on to either license DS 3.0 or fork 1.0 with Flipper's own changes.
> - Ideally, there will be one scripting system for the whole (Flipper) system. More to come after FZ Firmware 1.0
> - Several extensions have been added off-spec from DS 1.0 via community pull requests. It's becoming more usable, but less compatible with spec DS.

### Will the (Flipper's limited) parts eventually become available to buy so people can replace them if they break?
> Yes. Currently, there's not a storefront (there will be) but you can open a support ticket to order specific replacement parts instead.
> - Secure Enclave key is very difficult to replace
> - If you fuck up the option bytes, documentation is coming on how to fix them.
> - It's very hard to accidentally brick Flipper software wise, and theres slight voltage protection (up to 5V) on GPIO pins.

### Will there be a specific IDE for writing plugins?
> No. Everything needed is distributed alongside the firmware repository and can be compiled on multiple platforms.
> - There's a preset for VSCode that adds debugging configurations.
> - All tools to compile (besides git) are included as part of a toolkit bundle downloaded when building firmware. (x86 only)
> - Avoid using API's outside of FuriCore and FuriHAL! (Like libc)

### Is there going to be support for shared objects? (Multiple apps that use the same library)
> Probably not.

### Will there be support for loading background apps/services from SD card?
> Currently no, due to several technical limitations. Technically possible, but probably won't be added.
> - Main limitation is limited memory and trusting third party apps to manage it efficiently.

### Will there will be support for python for plugins/flipper applications. Or should I just bite the bullet and learn C
> Python is too large, compiled C is the most viable.
> - Flipper one will support other languages

### Are there plans for more “modules” like the wifi module to say add more memory or processing power and/or support for antennas. Related, any plans for a rudimentary SDR?
> It's not possible to directly extend Flipper's CPU power or RAM, but co-processors (like the WiFi board) could be used to extend some functionality. As for an SDR, it's not possible to extend Flipper's internal antennas. You would need to add an antenna to your own module board.

### Will you sell flipper "shells" (like the white and black) separately in diffrent colors?
> Besides a limited transparent shell, probably not, especially not black ones.

### Is there ever been questions of doing official support for companies who may be want to use flippers in their workplace such as a security company.
> Flipper isn't targeting enterprise, but they're open to discussion.

### How would you view it if someone published a whitepaper with the use of a Flipper as the source of much of the qualitative data in the research?
> No problem!

### With the advent of the Flipper one whenever that may be, is there going to be a another Kickstarter or are you simply going to go with what you currently have for funds selling the flipper zero.
> Yes, however this time production will start at the same time as the kickstarter campaign.

### What is the schedule of these Q&As?
> Every saturday, 1:00 AM and PM GMT.
> - Session hosts alternate between Flipper developers and commuity members every week.