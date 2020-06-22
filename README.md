# NUC6i5SYH-Hackintosh
Install macOS Catalina on Intel NUC6i5SYH using OpenCore.

## Specs
- CPU: *Intel Core i5-6260U Processor*
- RAM: *12 GB (8GB + 4GB)*
- HDD: *Crucial MX500 250GB SATA SSD*
- GPU: *Intel Iris Graphics 540*
- Audio Codec: *Realtek ALC 283*
- Ethernet: *Intel Ethernet Connection I219-V*
- WIFI/BT: *Intel Wireless-AC 8260 + Bluetooth 4.2*
- BIOS Version: *SYSKLi35.86A.0072.2019.1001.1636*

## Functionality
### Working
- Audio Jack
- HDMI Output
- Ethernet
- BT
- HDMI Audio*
### Not Working
- WIFI
- Memory Card Reader
### Did Not Test
- mDP Output

## Preparation
### BIOS
Press **F2** during boot to enter BIOS Setup

**Disable**
- Boot > Boot Configuration > Fast Boot
- Boot > Secure Boot > Secure Boot
- Security > Intel VT for Directed I/O (VT-d)
- Security > Intel Software Guard Extension (SGX)
- Security > Intel Platform Trust Technology

**Enable**
- Security > Intel virtualization Technology (VT-x)
- Security > Execute Disable Bit
- Performace > Processor > Intel Hyper-Threading Technology
- EHCI/XHCI Hand-off
- OS type: Windows 8.1/10 UEFI Mode
- Performance > Graphics > DVMT Pre-Allocated(iGPU Memory): 64MB

### OpenCore
This [OpenCore Desktop Guide](https://dortania.github.io/OpenCore-Desktop-Guide/) is a great resource for setting up files.
Current OpenCore Version: 0.5.9
