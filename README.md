# Clevo W650SJ OpenCore
This repository contains the necessary files to install macOS *Big Sur* on the Clevo W650SJ laptop.
Based on [OpenCore 0.7.6](https://github.com/acidanthera/OpenCorePkg), followed [Dortania's guide](https://dortania.github.io/OpenCore-Install-Guide/), first time user. 

## Specs
Processor: Intel(R) Core(TM) i7-4710MQ CPU @ 2.50GHz
iGPU: Intel(R) HD Graphics 4600
dGPU: NVIDIA GeForce GTX 850M (disabled)
Wireless Adapter: Realtek RTL8723BE Wireless LAN 802.11n PCI-E NIC (unsupported)

## What doesn't work
- GTX 850M
- Brightness keys
- WiFi
- Bluetooth
- VGA (didn't test but most likely doesn't work)

## Issues
- When booting into Recovery or the actual macOS, I encounter display artifacts similar to [this](https://www.tonymacx86.com/threads/glitchy-display-opencore-i7-4700mq-hd4600.298455/), but was able to circumvent it by closing the lid to put the machine to sleep and then wake up
- Windows/Linux made OpenCore USB installers won't boot with existing EFI operating systems, I had to disconnect or wipe the drives in order to boot the installer. Upon finishing the installation with EFI files copied to the EFI paritition, the machine cannot boot to Recovery natively without removing the drive(s) with EFI OS installed. Likely a UEFI problem, but multiboot with Windows and macOS on 2 seperate drives works fine. 

## SMBIOS
I used MacBookPro11,4 to have some compatibility with Monterey in the future
