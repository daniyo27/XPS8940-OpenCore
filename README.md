# Dell XPS 8940 - OpenCore

OpenCore 0.6.9 - macOS Big Sur 11.3.1 - BIOS version 2.0.11

_**UPDATED ON 05/13/2021**_ 




Confirmed working with G5 5090 and i5 variant of XPS 8940 -- _thanks @inkpool_

**Shutdown/Reboot/Sleep works without any issue.**

**GENERATE YOUR OWN SMBIOS deets (SN/MLB/UUID/ROM) -- they are EMPTY right now!**

(use genSMBIOS with iMac20,1 https://github.com/corpnewt/GenSMBIOS)




**Dell XPS 8940**

CPU: Intel i7-10700

RAM: 2x8GB DDR4-2933

SSD: WD SN750 NVMe

GPU: MSI GTX 770 2GB

iGPU: UHD 630 (enabled with platform-id 0x3E9B0007!)

AirPort/WiFi: BCM94352Z (Lenovo)

Audio: ALC3861 (actually ALC899)

~~Uses VoodooHDA for the time being to mitigate audio issue.~~

**NATIVE AppleALC patch with layout-id 1 working! Needed to add IRQ conflict fixes.**

--

USB Mapped for all front USB ports + all USB3.0 ports on the back (no USB2.0 ports due to port limit (15))


--

BIOS v2.0.11
  - change to AHCI instead of RAID
  - disable all SGX, security features
  - do not touch Sleep States, Performance states, SpeedShift etc. Leave them at defaults

**UPDATE 04/09/2021 for CFG-LOCK**
- it is only advisable to DISABLE CFG-LOCK, IF YOU HAVE an AFTERMARKET CPU COOLER!
- disabling CFG-LOCK with the stock non-K variant Dell heatsink will cause Kernel Panics randomly due to overheating

**CFG-LOCK disable -- Do this ONLY after your installation is complete**
- Follow the steps here: https://www.reddit.com/r/hackintosh/comments/hz2rtm/cfg_lockunlocking_alternative_method/
- The cfg-lock offset is 0x3E for BIOS 2.0.11
- You must use boot to ru.efi directly and not from OpenCore. modGRUB will not work!
- You must perform this step everytime you reset the BIOS configuration/update the bios.
- Once you have verified CFG-LOCK is disabled with VerifyMSRE2.efi in OpenCore, disable in config Kernel -> Quirks -> AppleCpuPmCfgLock and Kernel -> Quirks -> AppleXcpmCfgLock
