# HP-VICTUS-16 Hackintosh

 <h2 align="center"> OpenCore EFI For HP Victus 16 Ryzen 5 5600H & Radeon RX 5500M</h2>
 OpenCore Ver: 0.9.6</br>
 MacOS Supported Ver: BigSur, Monterey, Ventura, Sonomo</br>
 
![About mac](https://github.com/akhil838/HP-VICTUS-16_Hackintosh/assets/64255484/27ceea6a-c372-4011-941f-f1c12b2bf9be)

Check [Dortania's Guide](https://dortania.github.io/Anti-Hackintosh-Buyers-Guide/) for unsupported hardware like SSD and WLAN cards and replace them with supported ones

## Table of Contents

*   [Specifications](#specifications)
*   [What's Working](#whats-working)
*   [What's not Working](#whats-not-working)
*   [Kexts Used](#kexts-used)
*   [Screenshots](#screenshots)

## Specifications
|                 | ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ Laptop specifications‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎              |
| ----------------------- | :------------------------------------------------------------------------- |   
| CPU                     | AMD Ryzen™ 5 5600H with Radeon Graphics                                    |
| iGPU                    | Radeon Graphics (Vega 8)                                                   |
| dGPU                    | Radeon RX 5500M (Navi 14) [DISABLED]                                     |
| Memory                  | 24GB DDR4 3200MHz                                                          |
| Storage                 | 512GB NVMe SKHynix_HFS512GDE9X084N   [UNSUPPORTED] |
||512GB NVMe SAMSUNG MZVLB512HBJQ-000H1 (PM981)   [UNSUPPORTED]                                                           |
||512GB NVMe WD SN580 PCIe Gen4                                                          |
| Network                 | RTL8852AE 802.11ax PCIe Wireless Network Adapter [UNSUPPORTED]                         | 
|| RTL8111/8168/8411 PCI Express Gigabit Ethernet Controller|
| Audio|Realtek ALC245|
|LCD Panel| 16.1" FHD IPS 60Hz|

## What's Working

| Item | Status | Notes |
| --- | --- | --- |
| CPU | ✅ | AMD Vanilla Kernel Patches ([Modify according to yours Core Count](https://github.com/AMD-OSX/AMD_Vanilla)) |
| iGPU | ✅ | NootedRed |
| Brightness Control | ✅ | NootedRed |
| USB | ✅ | All ports working with [USBMap](https://github.com/corpnewt/USBMap "USBMap")|
| Keyboard | ✅ | Voodoops2controller.Kext |
| Audio | ✅ | AppleALC kext working with layout-id 11 |
| Mic | ✅ | Partially Working, Use the patch [AMDMicrophone](https://github.com/qhuyduong/AMDMicrophone) |
| Trackpad | ✅ | Synaptics Touchpad with AMD I2C Controller |
| Ethernet | ✅ | RealtekRTL8111.kext |
| Battery | ✅ | SMCBatteryManager.kext |
| iServices | ✅ | Message/Facetime tested and working |
| Shutdown/Reboot | ✅ | |
| Sleep/Wake | ✅ | |

## What's not Working

| Item | Status | Notes |
| --- | --- | --- |
| HDMI A/V out | ❌ | Connected to dGPU  |
| WIFI | ❌ | Unsupported Chipset |
| Bluetooth | ❌ | Unsupported Chipset |

## Kexts Used

| Kext | Description |
| --- | --- |
| [AMDRyzenCPUPowerManagement.kext](https://github.com/trulyspinach/SMCAMDProcessor) | Power management and monitoring of AMD processors |
| [AppleALC.kext](https://github.com/acidanthera/AppleALC) | Native macOS HD audio for not officially supported codecs |
| [AppleMCEReporterDisabler.kext](https://files.amd-osx.com/AppleMCEReporterDisabler.kext.zip) | Disables AppleIntelMCEReporter which causes panics on AMD CPUs |
| [AmdTscSync](https://github.com/naveenkrdy/AmdTscSync"AmdTscSync") | Synchronises the TimeStamp Counter (TSC). Generally only useful for AMD APUs (usually laptops) |
| [Lilu.kext](https://github.com/acidanthera/Lilu) | Platform for arbitrary kext, library, and program patching throughout the system |
| [NVMeFix.kext](https://github.com/acidanthera/NVMeFix) | Improve compatibility with non-Apple SSDs |
| [RealtekRTL8111.kext](https://github.com/Mieze/RTL8111_driver_for_OS_X) | Open source driver for the Realtek RTL8111/8168 family |
| [RestrictEvents.kext](https://github.com/acidanthera/RestrictEvents) | Blocking unwanted processes causing compatibility issues on different hardware and unlocking the support for certain features restricted to other hardware |
| [SMCAMDProcessor.kext](https://github.com/trulyspinach/SMCAMDProcessor) | Power management and monitoring of AMD processors |
| [SMCBatteryManager.kext](https://github.com/acidanthera/VirtualSMC) | Enables battery readings |
| [USBMap](https://github.com/corpnewt/USBMap "USBMap") | Python script for mapping USB ports in macOS and creating a custom injector kext |
| [VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC) | Advanced Apple SMC emulator in the kernel |
| [VoodooPS2Controller.kext](https://github.com/acidanthera/VoodooPS2) | Fixes keyboard |
|[BrightnessKeys.kext](https://github.com/acidanthera/BrightnessKeys)|Provides support for ACPI brightness change notifications|
|[ECEnabler](https://github.com/1Revenger1/ECEnabler)|Allows macOS to read EC fields over 8 bits long, removing the need to split them manually. |
|[HoRNDIS.kext](https://github.com/jwise/HoRNDIS)|driver for Mac OS X that allows you to use your Android phone's native USB tethering mode to get Internet access.|
|[NootedRed.kext](https://github.com/ChefKissInc/NootedRed)|Lilu plugin for AMD Vega iGPUs.|
|[SMCRadeonSensors](https://github.com/ChefKissInc/SMCRadeonSensors)|AMD GPU temperature monitoring on macOS|
|[VoodooI2C.kext](https://chefkissinc.github.io/Extras/Kexts/VoodooI2C.zip)|Driver for I2C input devices.|
|[VoodooRMI.kext](https://github.com/VoodooSMBus/VoodooRMI)|Synaptic Trackpad driver over SMBus/I2C for macOS|

## Screenshots
![Screenshot 2024-05-19 at 10 18 01 PM](https://github.com/akhil838/HP-VICTUS-16_Hackintosh/assets/64255484/eb2d2328-b82d-439b-9509-43b2174c9617)
![Screenshot 2024-05-19 at 10 19 22 PM](https://github.com/akhil838/HP-VICTUS-16_Hackintosh/assets/64255484/dea6dd8a-4a08-4e1a-a8a6-22039ae1d33e)


