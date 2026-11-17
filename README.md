Fork of [elmaleek03's HP Elitebook x360 1030 G4 EFI](https://github.com/elmaleek03/HP-Elitebook-x360-1030-G4-Hackintosh). All the hardware notes and working/not-working lists are still in his repo, this is just my copy of it.

Wi-Fi: I dropped AirportItlwmMonterey.kext and its entry in Kernel > Add, and put the Ventura 2.3.0 build of AirportItlwm in place of the Sonoma one, so it's a single Intel kext that actually loads on Ventura (MinKernel 22.0.0).

The rest is updated to current versions: OpenCore 1.0.8 (BOOTx64.efi, OpenCore.efi, drivers, tools, and the config brought up to the 1.0.8 schema), Lilu 1.7.2, VirtualSMC 1.3.8, WhateverGreen 1.7.1, AppleALC 1.9.8, VoodooI2C 2.9.1, VoodooPS2Controller 2.3.7, IntelBluetoothFirmware 2.4.0, BlueToolFixup 2.7.2, HibernationFixup 1.5.4, ECEnabler 1.0.6, USBToolBox 1.2.0, CPUFriend 1.3.0. AirportItlwm, YogaSMC and RTCMemoryFixup were already the newest, so those are untouched, and UTBMap is still my own USB map.

ACPI files, quirks, SMBIOS and device properties are left alone apart from turning on SSDT-PLUG (it was disabled, so nothing was injecting plugin-type and X86PlatformPlugin never attached) and the three keys 1.0.8 added. CPUFriend and its data provider stay off so it uses the stock curves. I'm on the i5-8265U model, the original was an i7-8665U.

Read this before touching CPUFriend: the provider shipped in here is frequency/voltage data taken from the i7-8665U, and that stuff is chip specific. Enabling it on an i5 doesn't give a boost, it gives you wrong P-states, best case it gets clamped and does nothing, worst case it crashes or hangs on boot. If you want custom curves, generate a provider for your own chip with CPUFriendFriend on the hackintosh itself.
