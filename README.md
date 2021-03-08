# Dell XPS 8940 - OpenCore

OpenCore 0.6.7

**Working Shutdown/Reboot without any issue.**

Dell XPS 8940
CPU: Intel i7-10700
RAM: 2x8GB DDR4-1933
SSD: WD SN750 NVMe
GPU: MSI GTX 770 2GB
AirPort/WiFi: BCM4352
Audio: ALC3861

--
Uses VoodooHDA for the time being to mitigate audio issue. 
  - AppleALC needs to patch Vendor ID 0x8086, Device ID 0x06C8 (Comet Lake PCH cAVS) against ALC898 ID's (shows up as ALC898 in Windows)
  - Please submit a Issue or PR if you fix this!

--
USB Mapped for all front USB ports + all USB3.0 ports on the back (no USB2.0 ports due to port limit (15))


--
BIOS
  - disable all SGX, security features
  - do not touch Sleep States, Performance states, SpeedShift etc. Leave them at defaults
