# NUC6i5SYH-Hackintosh
Install macOS Catalina on Intel NUC6i5SYH using OpenCore 0.5.9.

Reference: [OpenCore Desktop Guide](https://dortania.github.io/OpenCore-Desktop-Guide/)

## Specs
- CPU: *Intel Core i5-6260U*
- RAM: *12 GB (8GB + 4GB)*
- HDD: *Crucial MX500 250GB SATA SSD*
- GPU: *Intel Iris Graphics 540*
- Audio Codec: *Realtek ALC 283*
- Ethernet: *Intel Ethernet Connection I219-V*
- WIFI/BT: ~~*Intel Wireless-AC 8260 + Bluetooth 4.2*~~ Replaced with *BCM94360CS2* + *[M.2 B+M Key adapter](https://imgur.com/LKzHL8V)*
- BIOS Version: *SYSKLi35.86A.0072.2019.1001.1636*

**Working**
- Audio Jack
- HDMI Output
- Ethernet
- WIFI + BT
- HDMI Audio**
- iMessage, FaceTime & Continuity

**Not Working**
- Intel WIFI & ~~BT~~***
- Memory Card Reader

**Did Not Test**
- mDP Output

** HDMI Audio is fixed by using [FakePCIID + FakePCIID_Intel_HDMI_Audio (RehabMan-FakePCIID-2018-1027)](https://github.com/RehabMan/OS-X-Fake-PCI-ID)

*** Intel BT can be fixed by using [IntelBluetoothFirmware + IntelBluetoothInjector (1.0.3)](https://github.com/zxystd/IntelBluetoothFirmware/releases)

## Installation
1. Follow [OpenCore Desktop Guide - Creating the USB](https://dortania.github.io/OpenCore-Desktop-Guide/installer-guide/) to create USB installer.
2. Replace `EFI` with [EFI](EFI)
3. Generate SMBIOS using [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
   - Model: `iMac17,1`
   - Edit `EFI/OC/config.plist`
     - `Type` goes to PlatformInfo > Generic > SystemProductName
     - `Serial` goes to PlatformInfo > Generic > SystemSerialNumber
     - `Board Serial` goes to PlatformInfo > Generic > MLB
     - `SmUUID` goes to PlatformInfo > Generic > SystemUUID
     - MAC address go to PlatformInfo > Generic > ROM
4. Press **F2** during boot to enter **BIOS** Setup. Choose **Load Defaults**.
   - **Disable**
     - Security > Security Features > Intel VT for Directed I/O (VT-d)
     - Security > Security Features > Intel Platform Trust Technology
     - Security > Security Features > Intel Software Guard Extension (SGX)
     - Power -> Secondary Power Settings -> Wake on LAN from S4/S5
     - Boot > Boot Configuration > UEFI Boot > Fast Boot
     - Boot > Boot Configuration > Boot Devices > Network Boot
     - Boot > Secure Boot > Secure Boot
   - **Enable**
     - Devices > Video > IGD Minimum Memory: 64MB
     - Performace > Processor > Intel Hyper-Threading Technology
     - Performace > Processor > Intel Turbo Boost Technology
     - Security > Security Features > Execute Disable Bit
     - Security > Security Features > Intel virtualization Technology (VT-x)
5. Plug USB installer and restart. Press **F10** and boot from USB installer

## Post-installation
1. [Fix USB map](https://dortania.github.io/USB-Map-Guide/intel-mapping/intel.html) and remove USBInjectAll

## Source
- `EFI/OC/Drivers`
  - [HfsPlus.efi](https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi)
- `EFI/OC/Kexts`
  - [Lilu (1.4.5)](https://github.com/acidanthera/Lilu/releases)
  - [VirtualSMC + SMCProcessor + SMCSuperIO (1.1.4)](https://github.com/acidanthera/VirtualSMC/releases)
  - [WhateverGreen (1.4.0)](https://github.com/acidanthera/WhateverGreen/releases)
  - [AppleALC (1.5.0)](https://github.com/acidanthera/AppleALC/releases)
  - [IntelMausi (1.0.3)](https://github.com/acidanthera/IntelMausi/releases)
  - [USBInjectAll (0.7.5)](https://github.com/Sniki/OS-X-USB-Inject-All/releases)
  - [FakePCIID + FakePCIID_Intel_HDMI_Audio (RehabMan-FakePCIID-2018-1027)](https://github.com/RehabMan/OS-X-Fake-PCI-ID)
  - [IntelBluetoothFirmware + IntelBluetoothInjector (1.0.3)](https://github.com/zxystd/IntelBluetoothFirmware/releases)

## Additional Hardware
- BCM94360CS2
- [12+6 pin to M.2 adapter](https://www.aliexpress.com/item/4000494260199.html)

## Credits
- https://www.reddit.com/r/hackintosh/
- https://dortania.github.io/OpenCore-Desktop-Guide/
- https://github.com/acidanthera/
- https://github.com/Sniki/
- https://github.com/RehabMan/
- https://github.com/zxystd/






