# Flipper Zero developer Q&A
### August 6th 2022

Audio: [https://archive.org/details/flipperzero-qa-08062022-a](https://archive.org/details/flipperzero-qa-08062022-a)   
Recorded and transcripted by [`djsime1`](https://dj.je).  
**NOTE:** The transcription of questions and answers may contain errors, take it all with a grain of salt.

### What's the official warranty?
> 1yr, all factory defects replaced.

### What was the biggest setback during Flipper Zero's development? And the biggest unexpected win
> Setback: Not having enough developers at the beginning. Win: Being able to update firmware directly on the device

### Will Flipper and accessories be sold on Amazon?
> Likely through authorized re-shippers Q3 or Q4

### Is there anyway through a hardware “expansion” module to over come a lot of the current limitations?
> Potentially, though GPIO may not have all needed MCU blocks available.

### When is SD card apps coming?
> Next couple sprints for beta version and finalized at Version 1.0.0, ETA is Q3-Q4

### When will I be able to write cards?
> It's being worked on and will be release in the near future

### How can SD-Card apps be distributed?
> - There will be an official "gallery" for apps
> - You provide source code (no closed-source) and the apps are automatically compiled
> - Likely coming to mobile apps
> - There will be no paid apps.

### Status of file transfers over Bluetooth?
> There are some physical limitations: slow speed and big delay. It may be uncomfortable to transfer some files.

### Will qFlipper (PC app) support Bluetooth communication instead of USB?
> A lot of the supporting behind-the-scenes code exists, it is theoretically possible to implement, but potentially very problematic because of unstable OS level BLE support.

### Will docs be updated?
> Yes, as for developers documentation it will be vastly improved before firmware 1.0, but currently it's hard to keep up with the constant beta firmware changes. Also we do update and improve user documentation.

### Can the community contribute to official docs?
> Currently not directly. User-focused docs are the main focus now, while developer docs will come later.

### Why has the NFC redesign broke support for reading certain cards?
> It was done in order to heavily improve user experience. This extra functionality will be brought back eventually in a separate menu within the NFC app.
> - Felica and NFC-V are being looked into

### Where can I get a textured 3D model of the Flipper?
> While not textured, there are exact models available on GitHub: https://github.com/flipperdevices/flipperzero-3d-models

### Is it possible to copy-protect a RFID or NFC card?
> It majorly depends on the type of card, among many other factors. Generally speaking: 125khz RFID no, NFC yes.

### Is it bad/not recommended to use SD cards over 32GB?
> They will work fine, but you'll have a lot of wasted space.

### Are there websites, articles, documentations would you recommend to someone trying to start, understand and grasp NFC, RFID, etc.?
> A good place to start is https://blog.flipperzero.one/rfid/. Beyond there, look up "Intro to NFC" on YouTube.
> - https://blog.flipperzero.one/tag/classroom/
> - https://learn.adafruit.com/adafruit-pn532-rfid-nfc/mifare

### Would it be possible to scan for BLE devices from Flipper Zero? If yes, would it be possible to send commands to a BLE device from Flipper Zero?
> Officially, no. The firmware comes with a lightweight radio driver that doesn't support BLE scanning. A full radio stack exists, however it takes up a lot more (internal) storage, meaning certain applications would have to be removed and others rewritten to support the different API's.

### What is the point of having the "detect reader" feature in the NFC menu?
> It's still being worked on and will eventually be used in "online" attacks where the reader is present.

### Roughly how many core devs are there? wondering like what the dev split looks like from 'official flipper devs' working in sprints and all vs open source contributors
> Approximately 6-7 working on firmware, others work on mobile apps, testing, docs, etc. Teams work in 2-week sprints.

### What kind of hardware modules would the team be most excited to see?
> If we talking about modules in general: any. If you want to mass produce and sell it throw official shop then marketable.

### Is flipper suffering from chip shortage?
> No, it has been resolved.

### How is device region provisioning changing?
> - Previously there were 3 models of Flippers being produced, one per region.
> - The goal is to have one where location info is provisioned before shipping.

### What's the focus of development right now?
> - Region provisioning
> - Apps SDK and loading from SD
> - RPC API is coming for applications, making it easier to control the device with mobile companion apps.
> - It's summer for the Flipper team, and some of the members are on vacation. PR's will be merged when they're back.

### Is it possible to only record RAW Sub-GHz above a certain RSSI?
> Yes and no. Flipper is not SDR, and part of the transmission would get cut off if it only started recording after a certain RSSI is reached.
> - Use https://my.flipp.dev plotter. Eventually it will be able to split and save segments

### Flipper was left in 88* weather, and the screen broke. How long is the RMA process to get a new screen?
> It depends on the provider and shipper.
> - Flipper's screen is produced exclusively for the device

### Will there be some official way to read or edit files in text form directly inside flipper?
> It's possible, but editing the file directly on the Flipper can be challenging given the limited screen space. Ideally this would be done by the mobile companion apps.

### Will replacement parts be sold on the Flipper website?
> Yes, eventually.

### What capabilities will plugins (SD card apps) have?
> Currently it only supports adding complete applications, not tapping into existing apps. (Eg. Adding a new Sub-GHz protocol)
> - There's no technical limitations preventing the ability to extend existing apps, but lack of dev interest means it isn't being worked on. Alternatively you could recompile the entire apps
> - External apps are linked in a special way meaning not all app-specific API's will be accessible

### Can you share details about how the new region provisioning will work?
> Flipper will not be able to TX until you apply a firmware update* for the first time. Then, your region info will be sent to Flipper servers and a profile will be generated on your device. This profile is also stored on the flipper and dictates which frequencies can be TX on.

### Would it be possible to implement some way to mount the flipper as a mass storage device, for editing files on the as card?
> Flipper interfaces with MicroSD via SPI, which is much slower but more power efficient than normal SD. While it's possible, proofs of concept have shown transfer speeds are extremely slow and thus won't be implemented.

### Is there a way to remove the frequency regional "block"
> Due to legal regulations, this can not be done by the Flipper team.

### Will RFID be able to write to more chips besides the T5577?
> Yes, it's being worked on right now.

### What's the status of the Flipper One?
> It's being prototyped to improve upon everything Flipper Zero has. It's still being decided whether or not it will use commonly available hardware (Such as NXP/Qualcomm/Mediatek) or more custom hardware (Zynq/AD to enable features like an SDR).

### I found a tutorial for custom firmware, but it's using docker. I heard it's deprecated. Can you please forward me to updated one if it exists? 
> Docker still works, however FBT is preferred. https://github.com/flipperdevices/flipperzero-firmware/blob/dev/documentation/fbt.md

### Are there maybe going to be new revisions of the flipper zero? I saw e.g. PR for different radio chips than the cc1101?.
> We do prototyping, of different block. Some of them may be included in Fipper Zero mk2 or Flipper One.

### is flipper-one going to be on Kickstarter as well?
> Yes, it's great for determining demand levels.
> - It will be launched with working prototypes

### Will we be able to emulate a bank card for Apple/Google pay?
> It's not possible. Card chips are very secure, and the private keys required to authorize transactions never leave the card.
> - Even if it was possible, Flipper team is not interested in implementing it.

### I guess there won‘t be a way to update to the mk2 other than buying a second flipper one?
> Yes, you'll need to buy a new device.

### what choices lead to have the saved as ascii instead of raw bytes/words?
> Binary files can be difficult to interface with for humans. Most flipper files are meant to be human readable.

### Is there a timeline for doing more work on the wiki and maybe introducing a streamlined way for the community to add to the wiki?
> There's a dedicated documentation writer on the Flipper team currently working on the wiki. Feedback can be given via GitHub issues, and the ability for users to contribute is being worked on.

### How hard is it actually to replace the display cover of the current flipper zero?
> The plastic screen is bound to the casing, thus this is impossible to do without destroying the casing as well.

### small question, are we going to get a search function in flipper?
> It's very difficult to do this on the device due to limited resources, however it will be added to mobile companion apps eventually.

### Is there a timeframe for writing to NFC being added back?
> Yes, it will be worked on within the next couple of sprints.

### Can the WiFi dev board pull passwords from SSID?
> It's not that straightforward, but there are third party firmwares compatible with the dev board that can do this to a degree.

### What's the Bluetooth chip and would it be possible to get Ubertooth-like functionality? (sniff, send arbitrary packets, listen for beacons, spoof beacons…) 
> Possible to some degree with alternative radio stacks.

### Will there be an encryption for files on SD card available?
> While there are hardware-accelerated encryption API's on Flipper, full disk encryption will not be implemented due to high computational resource requirements.

### is it possible to set auto-password-lock for Flipper when in standby?
> Auto lock with PIN is something that will be added.

### Should I transfer files via companion apps/qFlipper or via swapping the SD card?
> Swapping SD cards is much faster for large files, but both should work without error.

### would it be possible to have a bootloader to load different firmwares from the SD card. or is this already possible?
> It's already here, check updater target in source code. Though your firmware is loaded into ram and limited with 196kb RAM. Loading code directly from SD is impossible.

### There are various simple OOK protocols, based on length of symbols, preamble and so on. The rc-switch project can find some of them automatically with the cc1101. Will there be a protocol that can identify them and/or create them in .sub file?
> It should be possible.

### Will be dumb mode available at V1.0?
> Yes, definitely.

### is/will it be possible to use the CLI through BLE?
> It's theoretically possible, but there's a delay that can cause issues for certain use cases.

### will it be possible to use the Sub-GHz chat function through the companion app?
> There's a possibility it will be added, but it's not top priority.

### will it be possible to access RPC (specifically App subsystem) over GPIO for hardware modules to interact with apps?
> Yes, a GPIO API is accessible to apps.

### how painful it will be to implement own rendering of the UI/screen drawing?
> Without using the existing API, it will be difficult.
> - Separate API may be added to directly communicate with screen
> - Max FPS without ghosting is 15-20.

### What decision do you regret the most and which one are you happiest about?
> Choice of chipset (Specifically `STM WB*`) has caused a lot of pain. On the other hand, everything else was great.

### Will there be any further development on the Tamagotchi aspect of the flipper zero? 
> The Flipper Team is looking for help from the community with this. Meanwhile we do plan to add new animations.

### Will there be a function to replay all Sub-GHz files in one folder? (kinda brute with all files out there in the map)
> This would have to be implemented in a third-party app.

### is it possible for Flipper One to have an upgraded USB version (2.x, 3.x), compared to the one that is currently used in Flipper Zero (1.x, i believe)?
> Yes

### another question related to mass storage -- would it be possible to use Flipper One for hosting .iso images of live Linux distros (or would it be functionally impossible and/or not worth it)?
> Yes, it should be possible.

### Will Flipper One use an ePaper display?
> No, it will use an LCD.

### What does LITE next to radio FW mean?
> It relates to the capabilities of the BLE core. Lite excludes a bunch of uncommon functions

### will you sell the black case to change the white one to the black one?
> There WILL be a limited transparent series, however there's no word on black case production.

### I understand flipper can emulate HID’s but can it emulate Network / ethernet adapters?
> In theory it's possible, but flippers processor is pretty slow for this.

### is there a flipper GPIO documentation posted somewhere?
> https://miro.com/app/board/uXjVO_LaYYI=

### Is there are a reason why pins connected to the buttons are exposed_
> Button pins aren't exposed, marking are related to interrupt controller(EXTI) which got usage limitation.

### would Flipper One use SPI (like Flipper Zero does) or is there a chance for SDIO to be used instead?
> Flipper One will definitely use SDIO.

### What range of frequencies will Flipper One's SDR support?
> Probably 60 MHz to 6 GHz.

### Can we get an alarm clock in the clock app?
> This can be done with a third party application, the hardware has 2 RTC alarm clocks.

### so for more Tamagotchi features, are you open to merge community designed "fun features" like hunger/sleep etc.? & if yes, is there a possibility to communicate with the graphics department to better integrate them?
> Yes, though more planning is needed. If your idea is fully developed, you can reach out and the Flipper Team will help provide resources.

### If I let Flipper scan Sub-GHz for a whole day, does it damage the device?
> No, it won't damage the device. If reading raw, make sure your SD card is big enough/

### is there some documentation which lists all the hardware peripherals currently used by FURI HAL and services, 
> - and eventually which peripherals would be currently unused and free to directly be used from apps ?
> There's no complete documentation currently available, but apps will have certain hardware and subsystem APIs.
> - https://miro.com/app/board/o9J_l1XZfbw=/?share_link_id=606281650151

### once the SDK is released, would it be possible to run apps in the background?
> Yes

### Is there an emulator for development, where do I sign up to help out. Issue triage, UI development etc.
> There's no emulator, though it's planned after 1.0. Contributions can be made on GitHub

### Is there an estimate when BadUSB will support international keyboard layouts?
> Yes, there's a pull request currently waiting to be merged that will add support for alternative keyboard layouts.
> - Should arrive in next sprint or two
> - Person in charge of BadUSB is on vacation

### Any plans to appear on podcasts like Embedded.fm, TheAmpHour or UnnamedRE?
> If we get invited, why not?

### How the frick have you been able to manufacture during the chip shortage? Did you buy all the reels of parts some 2 years ago?
> A lot of hardware changes had to be made to prototypes as production was being planned.
> - STM WB series contract was secures long before shortage, while others simply disappeared one day.

### Are you planning on bringing (more) shortcuts/Siri shortcuts to the iOS app?
> Yes, additionally widgets are planned to be added.

### Is it recommended to format SD cards with Flipper or PC?
> Format it with Flipper for best results.
> - Flipper can not verify integrity of filesystem

### Should I format the SD card with exFAT or FAT32
> FAT32.