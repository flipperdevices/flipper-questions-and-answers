# Flipper Zero developer Q&A
### August 26th 2022 (Side A)

Audio: [https://archive.org/details/flipperzero-qa-08262022-a](https://archive.org/details/flipperzero-qa-08262022-a)  
Recorded and transcribed by [`djsime1`](https://dj.je).  
**NOTE:** The transcription of questions and answers may contain errors, take it all with a grain of salt.

### Week in review:
> - Released 0.65.2 firmware (Includes new RFID protocols).
> - New provisioning system is being rolled out to factory.
> - ELF plugin loading is almost ready to release.

### Where is the company based out of?
> Head office: US DE, production office is in Shenzhen China, R&D in Europe and Asia.

### How is Flipper Zero programmed?
> Firmware is based on FreeRTOS and written in C. It's open source and can be found on GitHub.
> - Some bits are still C++, but it will be deprecated before version 1.0

### What can the WiFi board do?
> It's intended to act as a wireless debugger, as an alternative to an ST-Link.
> - You can also write your own firmware for the WiFi board to do other stuff

### Does this mean factory firmware is going to be upgraded? Have you considered shipping a minimal firmware that prompts the user to update via qFlipper or the mobile app?
> Yes, out-of-box firmware will be upgraded, such that Sub-GHz transmission won't be usable until the region is provisioned. A minimal firmware isn't required since you're already prompted to update upon first start.

### What is the Flipper team's near to mid-term roadmap for SubGhz and 125kHz modules?
> Adding protocols to NFC, RFID, and Sub-GHz has been made more streamlined. In the near future, RFID's C++ code will be rewritten in C.

### Has there been any progress on deciding new BadUSB language?
> A discovery was made that a tiny JavaScript interpreter can be packed in to the firmware. It's still in the research stage, but it seems like a promising path.

### Is there any reason I shouldn't replace (940)nm IR LED's with (850)nm IR LED's?
> It would decrease overall power output, but some devices prefer (850)nm LED's.

### if I get the Flipper Zero, how can I open a garage door without having the garage key?
> If you know the protocol of your garage, you can generate a new key on the Flipper and tell your garage to learn it.

### How common is it for Flipper to get damaged in shipping?
> Only ~10 out of 60,000 shipments have been damaged beyond the point of use so far. If your order is damaged, open a support ticket for replacement.

### Any updates on ELF (SD-card apps) loading?
> Yes, it will be rolled out in the next firmware release. After that, the API will be finalized and UI/UX work will be done.

### Can/will RAM be expanded?
> Hardware wise, no it's not possible. However, software measures are being taken to reduce overall RAM usage.

### Can the consumer replace the battery should it start having charging issues in the future? Or is it sealed in there?
> Yes, the device can be disassembled and the battery can be replaced. https://www.ifixit.com/Teardown/Flipper+Zero+Teardown/151455
> - Contact Flipper Support for exact replacement battery, however most of similar size and spec should work.
