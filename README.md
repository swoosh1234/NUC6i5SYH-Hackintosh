# NUC6i5SYH-Hackintosh
Install macOS Catalina on Intel NUC6i5SYH using OpenCore.

Reference: [OpenCore Desktop Guide](https://dortania.github.io/OpenCore-Desktop-Guide/)

## Specs
- CPU: *Intel Core i5-6260U*
- RAM: *12 GB (8GB + 4GB)*
- HDD: *Crucial MX500 250GB SATA SSD*
- GPU: *Intel Iris Graphics 540*
- Audio Codec: *Realtek ALC 283*
- Ethernet: *Intel Ethernet Connection I219-V*
- WIFI/BT: *Intel Wireless-AC 8260 + Bluetooth 4.2*
- BIOS Version: *SYSKLi35.86A.0072.2019.1001.1636*

### Working
- Audio Jack
- HDMI Output
- Ethernet
- BT
- HDMI Audio

### Not Working
- WIFI
- Memory Card Reader

### Did Not Test
- mDP Output
- Internal USB headers

## Preparation
### BIOS
Press **F2** during boot to enter BIOS Setup. Choose **Load Defaults**.

**Disable**
- Boot > Boot Configuration > Fast Boot
- Boot > Boot Configuration > Network Boot
- Boot > Secure Boot > Secure Boot
- Security > Intel VT for Directed I/O (VT-d)
- Security > Intel Software Guard Extension (SGX)
- Security > Intel Platform Trust Technology
- Power -> Secondary Power Settings -> Wake on LAN from S4/S5
 
**Enable**
- Security > Intel virtualization Technology (VT-x)
- Security > Execute Disable Bit
- Performace > Processor > Intel Hyper-Threading Technology
- Performance > Graphics > DVMT Pre-Allocated(iGPU Memory): 64MB
- EHCI/XHCI Hand-off
- OS type: Windows 8.1/10 UEFI Mode

### OpenCore
Current OpenCore Version: 0.5.9

Follow [OpenCore Desktop Guide - Creating the USB](https://dortania.github.io/OpenCore-Desktop-Guide/installer-guide/) to create USB installer.

**Drivers**
- HfsPlus.efi
- OpenCanopy.efi
- OpenRuntime.efi

**Kexts**
- [Lilu (1.4.5)](https://github.com/acidanthera/Lilu/releases)
- [VirtualSMC + SMCProcessor + SMCSuperIO (1.1.4)](https://github.com/acidanthera/VirtualSMC/releases)
- [WhateverGreen (1.4.0)](https://github.com/acidanthera/WhateverGreen/releases)
- [AppleALC (1.5.0)](https://github.com/acidanthera/AppleALC/releases)
- [IntelMausi (1.0.3)](https://github.com/acidanthera/IntelMausi/releases)
- [USBInjectAll (0.7.5)](https://github.com/Sniki/OS-X-USB-Inject-All/releases)


