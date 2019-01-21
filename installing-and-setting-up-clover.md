# Installing and setting up Clover

We will need some bootloader capable of booting macOS. The only correct choice at the moment is Clover ~~sadly.~~

1. Download the latest [Clover LZMA](https://github.com/Dids/clover-builder/releases/latest) from Dids' Clover repo.
2. Use 7zip to extract the LZMA and TAR until you get a .iso file
3. Mount the ISO by double clicking
4. Copy the EFI folder from "CloverCD" to CLOVER
5. Go `CLOVER > EFI > CLOVER`
6. Delete: 
   1. doc
   2. OEM
   3. drivers64
   4. drivers32
   5. drivers32UEFI
7. Open `drivers64UEFI` and delete everything inside of it.
8. Go to `drivers-off > drivers64UEFI` and copy the following:
   1. ApfsDriverLoader
   2. AppleImageLoader
   3. AptioMemoryFix
   4. HFSPlus
      1. _Now paste all of this in to `drivers64UEFI`_
9. Go to [Goldfish's Kext Repo](https://1drv.ms/f/s!AiP7m5LaOED-m-J8-MLJGnOgAqnjGw)
10. Download the following kexts:
    1. _**FakeSMC**_ OR _**VirtualSMC**_ - These kexts both emulate an SMC, but VSMC does this cleaner.
    2. _**Lilu**_ - This kext patches other kexts.
    3. _**WhateverGreen**_ - A kext which is a plugin for Lilu that patches a lot of GPU related issues.
    4. _**NullCPUPowerManagement**_ - This kills CPU PM, since that doesn't work anyways.
    5. For your LAN card:
       * **AppleIntele1000** for some old cards
       * **IntelMausiEthernet** for most Intel NICs
       * **AtherosE2200Ethernet** for some Atheros/QualcommAtheros/Killer\(some\) NICs
       * **BCM5722D** for Broadcom BCM5722 NetXtreme and NetLink family
       * **RealtekRTL8100** for 10/100 Realtek Cards \(Realtek FE\)
       * **RealtekRTL8111** for Gigabit Realtek Cards \(Realtek GbE\)
         * _Note: if you're not sure, LOOK FOR YOUR LAN CHIPSET AND CHECK THIS AGAIN._
11. Place these kexts, extracted from their .zip, in to `CLOVER > EFI > CLOVER > kexts > Other`. You can skip the sensor kexts.

Only a config needed and we're ready to go!



