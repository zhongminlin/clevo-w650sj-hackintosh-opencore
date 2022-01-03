# Clevo W650SJ OpenCore
This repository contains the necessary files to install macOS *Big Sur* on the Clevo W650SJ/Sager NP6658 laptop.
Based on [OpenCore 0.7.6](https://github.com/acidanthera/OpenCorePkg), followed [Dortania's guide](https://dortania.github.io/OpenCore-Install-Guide/), first time user. 

## Hardware Specs
- Processor: Intel(R) Core(TM) i7-4710MQ CPU @ 2.50GHz
- RAM: 8 GB Wintec DDR3L 1600MHz
- Motherboard: Intel HM86 Chipset
- iGPU: Intel(R) HD Graphics 4600
- dGPU: NVIDIA GeForce GTX 850M (disabled)
- Wireless: Realtek RTL8723BE Wireless LAN 802.11n PCI-E NIC (unsupported)
- Ethernet: Realtek PCIe GbE Family Controller

## Requirements
- [Clevo W650SJ laptop](https://web.archive.org/web/20140401085034/http://www.xoticpc.com/sager-np6658-clevo-w650sj-p-6994.html)
- Working PC with macOS/Linux/Windows installed
- Ethernet cable for online installer
- 4GB USB drive for online installer, 16GB for offline installer 
- Patience

## What doesn't work
- GTX 850M
- Brightness keys
- WiFi
- Bluetooth
- VGA (didn't test but most likely doesn't work)
- Realtek Card Reader

## Issues
- When booting into Recovery or the actual macOS, I encounter display artifacts similar to [this](https://www.tonymacx86.com/threads/glitchy-display-opencore-i7-4700mq-hd4600.298455/), but was able to circumvent it by closing the lid to put the machine to sleep and then wake up
- Windows/Linux made OpenCore USB installers won't boot with existing EFI operating systems, I had to disconnect or wipe the drives in order to boot the installer. Upon finishing the installation with EFI files copied to the EFI paritition, the machine cannot boot to Recovery natively without removing the drive(s) with EFI OS installed. Likely an UEFI problem, but multiboot with Windows and macOS on 2 seperate drives works fine. 

## Notes
- Brightness keys and card reader may be fixable but I am too lazy to investigate
- Compatible Intel WiFi chips may be purchased to be paired with [AirportItwlm and others](https://openintelwireless.github.io/) for usage
- SMBIOS MacBookPro11,4 was chosen to be compatible with Monterey in the future
- The RtWlanU kexts are installed as part of [chris111's drivers for USB WiFi dongles](https://github.com/chris1111/Wireless-USB-OC-Big-Sur-Adapter), feel free to remove and update config.plist if not needed
- OpenCore GUI and boot chime were added post-installation for fun
