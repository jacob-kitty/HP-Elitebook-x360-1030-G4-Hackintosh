Fork of [elmaleek03's HP Elitebook x360 1030 G4 EFI](https://github.com/elmaleek03/HP-Elitebook-x360-1030-G4-Hackintosh). All the hardware notes and working/not-working lists are still in his repo, this is just my copy of it.

The only thing I changed is the Wi-Fi. Dropped AirportItlwmMonterey.kext and its entry in Kernel > Add, and swapped the Sonoma build of AirportItlwm for the Ventura 2.3.0 one, so there's a single Intel Wi-Fi kext that actually loads on Ventura. Its MinKernel is 22.0.0 now.

Everything else (ACPI, other kexts, quirks, SMBIOS, device properties) is untouched. I'm on the i5-8265U model, the original was an i7-8665U.
