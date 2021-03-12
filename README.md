# Dell XPS 8940 - OpenCore

OpenCore 0.6.7 - macOS Big Sur 11.2.2

_***Should work with Dell G5 5090 Gaming Desktop (Comet Lake) as well!**_ (let me know!)

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

BIOS
  - disable all SGX, security features
  - do not touch Sleep States, Performance states, SpeedShift etc. Leave them at defaults
