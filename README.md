<h1 align="center">Opencore EFI For the Asus Z8NA-D6</h1>
<p align="center">
<img src="https://img.shields.io/badge/macOS-High_Sierra_10.13-yellow.svg"/>
<img src="https://img.shields.io/badge/OpenCore-1.0.6-blue.svg"/>
<img src="https://img.shields.io/badge/Board-Asus_Z8NA--D6-red.svg"/>
<img src="https://img.shields.io/badge/CPU-2x_Xeon_X5670-lightgrey.svg"/>
<img src="https://img.shields.io/badge/SMBIOS-MacPro5%2C1-blueviolet.svg"/>
<img src="https://img.shields.io/badge/Status-Maintained-brightgreen.svg"/>
</p>

#### Use This code at your own risk!, I am not responsible for any issues that arise w/ this EFI. not all features are working as this is a personal repo.

- This Repo can be used as a reference for a hackintosh based on the same board, but please do not rely on this repo. Please use the <a href="https://dortania.github.io/OpenCore-Install-Guide/">Opencore Install Guide</a> As there are hardware differences and not all things will work the same if you choose to go down the route of using this as a base for your machine.
- This EFI is configured for OSX 10.13 High Sierra.
- I am using a ASPEED AST 2050 Baseboard Management Controller for the Video, It lacks video acceleration and proper resolution support and is not compatible with Macos in any means, It will spit out video
- I had to use a tool called BOOTICE to modify / add the Boot sectors into the usb drive to make opencore bootable, without it the installer would not boot (legacy bios quirk.)
  
This repository may or may not be updated depending on if I keep macOS on the machine and get a proper GPU. If I do, I will update this repository accordingly — if not, it will remain here as-is. For any machine like this, I recommend moving to AMD for a GPU instead of NVIDIA. You will be stuck on 10.13 and only Pascal/Maxwell cards can work. Modern MacOS Support will not work.

<details>
<summary><strong>Functional / Not Tested / Unfunctional</strong></summary>
<br>

### Non-Functional / Not Tested

| Feature                    | Status | Notes                                       |
| :------------------------- | :----: | :------------------------------------------ |
| WiFi                       | ⚠️     | Not tested — no WiFi card installed         |
| Bluetooth                  | ❌     | No Bluetooth card installed                 |
| Audio                      | ⚠️     | Not tested — no soundcard installed         |
| PS2 Keyboard / Mouse       | ⚠️     | Not tested                                  |
| Serial Port                | ⚠️     | Not tested                                  |
| iMessage / FaceTime        | ❌     | Not working — Most likely a 10.13 Issue |
| AirDrop                    | ⚠️     | Not tested — requires WiFi + Bluetooth      |
| S3 Sleep / Wake            | ❌     |Not Functional - Server Board Stuff |
| Video Acceleration (QE/CI) | ❌     | ASPEED BMC VGA only — no GPU acceleration   |

### Working

| Feature                   | Status | Notes                            |
| :------------------------ | :----: | :------------------------------- |
| Ethernet (both ports)     | ✅     | `AppleIntelE1000E.kext`         |
| USB 2.0 (all ports)           | ✅     | All ports functional (Proper USB Mapping) |
| Apple ID / Apple Services | ✅     | Sign in works, iMessage does not |
| Time Machine              | ✅     | Native support                   |

</details>

<details>
<summary><strong>Tools Used.</strong></summary>
<br>

These are the Resources and tools used in my journey of getting this to work.:

- [Dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [Dortania's OpenCore Post Install Guide](https://dortania.github.io/OpenCore-Post-Install/)
- [Dortania/ Getting Started with ACPI](https://dortania.github.io/Getting-Started-With-ACPI/)
- [ProperTree](https://github.com/corpnewt/propertree) For Config Plist Editing
- [UnPlugged](https://github.com/corpnewt/UnPlugged) Getting the 10.13 Installer in an offline Format
- [OpenCore PKG](https://github.com/acidanthera/opencorepkg) The Opencore Repo Itself

</details>

<details>
<summary><strong>Kexts Used</strong></summary>
<br>

These are links to the kexts used in the EFI Folder

- [AppleALC](https://github.com/acidanthera/applealc/releases)
- [AppleIntelE1000e](https://github.com/chris1111/AppleIntelE1000e)
- [CpuTscSync](https://github.com/acidanthera/CpuTscSync)
- [Lilu](https://github.com/acidanthera/lilu/releases)
- [VirtualSMC](https://github.com/acidanthera/virtualsmc/releases) Note, SMCProcessor is in this Repo
- [WhateverGreen](https://github.com/acidanthera/Whatevergreen)

  </details>

    <details>
<summary><strong>Hardware Specifications</strong></summary>
<br>

| Category    | Specification                                      |
| :---------- | :------------------------------------------------- |
| CPU         | 2x Intel Xeon X5670 (6C/12T each, 12C/24T total)  |
| Chipset     | Intel 5520 (Tylersburg)                            |
| Motherboard | Asus Z8NA-D6                                       |
| RAM         | 32GB DDR3 ECC 1333MHz (4x8GB HP/Nanya)             |
| Storage     | 500GB WD Black HDD (SATA)                          |
| GPU         | ASPEED AST2050 BMC (VGA only, no acceleration)     |
| Ethernet    | 2x Intel 82574L 1Gbps                              |
| Audio       | Realtek ALC (onboard, no soundcard)                |

  </details>
