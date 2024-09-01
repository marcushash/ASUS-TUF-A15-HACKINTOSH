# Hackintosh Installation Guide for ASUS TUF A15 🖥️🍏

This detailed guide offers step-by-step instructions for installing macOS Sonoma on the ASUS TUF A15 using a customized EFI folder. 📘✨ It includes comprehensive hardware specifications, pre-installation and installation steps, as well as post-installation procedures to ensure a smooth setup. 🛠️💻

## Disclaimer ⚠️

**Important:** The EFI provided in this guide is a proof of concept. It has several issues that may not be fixed, and many components have not been fully tested. **Do not use this EFI as your daily driver.** For a stable Hackintosh setup, create your own EFI tailored to your specific hardware configuration. The author is not responsible for any damage caused by the contents of this guide. Proceed at your own risk.

## Hardware Specifications 🛠️

### CPU
- **Model:** AMD Ryzen 5 4600H with Radeon Graphics
  - **Cores:** 6
  - **Threads:** 12
  - **SSE:** SSE4.2
  - **SSSE3:** Supported
  - **Codename:** Renoir

### GPU
- **Integrated GPU:** AMD Radeon(TM) Graphics
  - **Device ID:** 0x1636
  - **Vendor ID:** 0x1002
  - **PCI Path:** PciRoot(0x0)/Pci(0x8,0x1)/Pci(0x0,0x0)
  - **ACPI Path:** \_SB.PCI0.GP17.VGA_
  - **Codename:** Renoir
- **Discrete GPU:** NVIDIA GeForce GTX 1650 (Disabled)
  - **Device ID:** 0x1F99
  - **Vendor ID:** 0x10DE
  - **PCI Path:** PciRoot(0x0)/Pci(0x1,0x1)/Pci(0x0,0x0)
  - **ACPI Path:** \_SB.PCI0.GPP0.PEGP

### Memory
- **Model:** Crucial 8ATF1G64HZ-3G2J1
  - **Type:** DDR4
  - **Slot:** DIMM 0 (P0 CHANNEL A)
  - **Frequency:** 3200 MHz
  - **Manufacturer:** Crucial
  - **Capacity:** 16 GB (Dual Channel, 8192MB x 2)

### Network
- **Wi-Fi:** Intel Wi-Fi 6 AX200
  - **Device ID:** 0x2723
  - **Vendor ID:** 0x8086
  - **PCI Path:** PciRoot(0x0)/Pci(0x2,0x2)/Pci(0x0,0x0)
  - **ACPI Path:** \_SB.PCI0.GPP4.PXSX

### Audio
- **Codec:** Realtek ALC295
  - **Device ID:** 0x0295
  - **Vendor ID:** 0x10EC

### Input
- **Keyboard:** 
  - **Product ID:** 0xC08B
  - **Vendor ID:** 0x046D

### Storage
- **SSD:** WDC PC SN530 SDBPNPZ-256G-1014
  - **Type:** NVMe
  - **Connector:** PCI Express
  - **Location:** Internal

## Pre-Installation Steps 🛠️

1. **Flash the Olarilla Image Using TransMac** 🗂️:
   - Format a USB drive as `Mac OS Extended (Journaled)` using TransMac, and restore the Olarilla image to the USB drive.

2. **Prepare the EFI Folder** 📂:
   - Download the EFI folder from the GitHub repository: [ASUS-TUF-A15-HACKINTOSH](https://github.com/marcushash/ASUS-TUF-A15-HACKINTOSH).
   - Use [MiniTool Partition Wizard](https://www.partitionwizard.com/) to rename the EFI partition so that it can be detected by Windows.
   - Use [Explorer++](https://explorerplusplus.com/) to copy the EFI folder from the USB drive to the EFI partition of the USB drive.

3. **Configure BIOS/UEFI Settings** 🗂️:
   - Insert the USB drive with the EFI folder into your ASUS TUF A15.
   - Restart the laptop and enter BIOS/UEFI settings (usually by pressing `F2` or `Del` during startup).
   - Adjust the following settings:
     - Set `SATA Mode` to `AHCI`.
     - Disable `Secure Boot`.
     - Enable `VT-d` (Virtualization Technology for Directed I/O).
     - Disable `Fast Boot`.
     - Set `CSM` (Compatibility Support Module) to `Disabled` if available.
   - Save and exit BIOS.

4. **Boot from USB** 🖥️:
   - Restart the laptop and boot from the USB drive containing the EFI folder (usually by pressing `F8`, `F11`, or `Esc` during startup and selecting the USB drive).

## Installation Steps 🚀

1. **Install macOS** 🍏:
   - Boot from the USB drive and select `Install macOS Sonoma` from the boot menu.
   - Follow the on-screen instructions to install macOS.
   - During installation, you may need to re-select the USB drive as the boot disk if the laptop restarts.

2. **Post-Installation** 🔧:
   - After the macOS installation, the system may reboot. Boot again from the USB drive and select the newly installed macOS volume.
   - Install the OpenCore or Clover bootloader to your internal drive:
     - Mount the EFI partition of the internal drive.
     - Copy the `EFI` folder from the USB drive to the EFI partition of the internal drive.

3. **Finalize Installation** ✔️:
   - Once macOS boots from the internal drive, configure the system.
   - Install any additional kexts or drivers required for full hardware compatibility (network, audio, etc.).

## Notes 📋

- **What Works:**
  - Wi-Fi 🌐
  - USB 🔌
  - NVMe Drive 💾

- **What Does Not Work:**
  - Keyboard ⌨️ (only one in-built keyboard is used)
  - Trackpad 🖱️
  - Discrete GPU (NVIDIA GeForce GTX 1650) 🎮
  - Other functionalities may be untested 🕵️

- **Compatibility:** Not all hardware components may be fully compatible with macOS. Check community forums for similar hardware reports.
- **Updates:** Be cautious with system updates as they may affect compatibility. Research before applying updates.

## Support 🙏

If you find this guide helpful and wish to support my work, consider buying me a coffee:

<h3 align="left">Support:</h3>
<p><a href="https://ko-fi.com/marcushash"> <img align="left" src="https://cdn.ko-fi.com/cdn/kofi3.png?v=3" height="50" width="210" alt="Support me on Ko-fi" /></a></p><br><br>

## Resources 📚

- [Olarilla Forums](https://www.olarilla.com)
- [Hackintosh Community](https://www.tonymacx86.com)
- [OpenCore Documentation](https://dortania.github.io/OpenCore-Install-Guide/)
- [TransMac](https://www.acutesystems.com/scrtm.htm)
- [MiniTool Partition Wizard](https://www.partitionwizard.com/)
- [Explorer++](https://explorerplusplus.com/)
