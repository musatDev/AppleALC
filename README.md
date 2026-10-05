> **Note: layout-id=81 is specific to my own motherboard: MSI MAG B460 TORPEDO (MS-7C81).**

## Custom AppleALC — Realtek ALCS1200A — Layout 81

**[Download AppleALC.kext R3 ZIP — Layout 81, +30 dB front microphone boost](https://github.com/musatDev/MSI-MAG-B460-TORPEDO-ALCS1200A-Layout81/raw/refs/heads/main/Downloads/AppleALC-Layout81-R3.zip)**

[Installation and changes](https://github.com/musatDev/MSI-MAG-B460-TORPEDO-ALCS1200A-Layout81#readme) · [SHA-256 checksum](https://github.com/musatDev/MSI-MAG-B460-TORPEDO-ALCS1200A-Layout81/blob/main/Downloads/SHA256SUMS.txt) · [Custom source branch](https://github.com/musatDev/AppleALC/tree/msi-b460-layout81)

The custom layout source is on the **msi-b460-layout81** branch. The ZIP above contains the prebuilt custom kext; GitHub's **Code > Download ZIP** downloads source code.

## Custom changes

- Added layout **81**, based on layout31, for the **Realtek ALCS1200A** codec on **MSI MAG B460 TORPEDO (MS-7C81)**.
- Added `layout81.xml` and `Platforms81.xml`, and registered the layout in the codec and PinConfigs files.
- Changed the front microphone path from `9 → 34 → 25` to `8 → 35 → 25`.
- Changed the rear line-in path from `8 → 35 → 26` to `9 → 34 → 26`.
- Kept the rear microphone path (`9 → 34 → 24`), layout31 output paths, and layout DSP settings.
- Adjusted pin defaults, microphone bias, and output EAPD settings for this board.
- Set front microphone boost to **+30 dB** (`01937003`) during both initialization and wake.

Paths use decimal AppleHDA NodeIDs. These source changes are on the **msi-b460-layout81** branch and are included in the downloadable R3 kext.

---

AppleALC
========

[![Build Status](https://github.com/acidanthera/AppleALC/actions/workflows/main.yml/badge.svg?branch=master)](https://github.com/acidanthera/AppleALC/actions) [![Scan Status](https://scan.coverity.com/projects/16166/badge.svg?flat=1)](https://scan.coverity.com/projects/16166)

An open source kernel extension enabling native macOS HD audio for not officially supported codecs without any filesystem modifications. AppleALCU can be used for systems with digital-only audio.

English (Current)  
[简体中文](https://github.com/acidanthera/AppleALC/blob/master/README_CN.md)  

#### Features
- Digital and analog audio support starting from the OS installation
- Recovery HD/macOS Installer audio support
- Automated codec detection
- Unsupported audio controller enabling (internal and external)
- Arbitrary kext patching
- Custom platform/layout injection
- Works with SIP / El Capitan+
- Currently compatible with 10.4-26*

\* _NOTE_: macOS 26 dropped AppleHDA.kext in DP2. AppleALC functioning on macOS 26 may require additional actions if AppleHDA.kext is necessary.

#### Credits
- [Apple](https://www.apple.com) for macOS  
- [Onyx The Black Cat](https://github.com/gdbinit/onyx-the-black-cat) by [fG!](https://reverse.put.as) for the base of the kernel patcher
- [capstone](https://github.com/aquynh/capstone) by [Nguyen Anh Quynh](https://github.com/aquynh) for the disassembler module
- [toleda](https://github.com/toleda), [Mirone](https://github.com/Mirone) and certain others for audio patches and layouts
- [Pike R. Alpha](https://github.com/Piker-Alpha) for [lzvn](https://github.com/Piker-Alpha/LZVN) decompression and certain HDMI patches
- [07151129](https://github.com/07151129) for some code parts and suggestions
- [roddy20](https://github.com/roddy20) for training and research dumps to a patching of codecs
- [vit9696](https://github.com/vit9696) for writing the software and maintaining it
- [Andrey1970AppleLife](https://github.com/Andrey1970AppleLife), [vandroiy2013](https://github.com/vandroiy2013) for maintaining the codec database

#### Installation
The minimal instruction is available on the [wiki](https://github.com/acidanthera/AppleALC/wiki).  
The prebuilt binaries are available on [releases](https://github.com/acidanthera/AppleALC/releases) page.

#### Contribution
To support more audio codecs in the binary packages you are asked to submit your configurations. Please read the [wiki](https://github.com/acidanthera/AppleALC/wiki) for more details. For the contributors with programming skills the headers are filled with AppleDOC comments.

#### Support and discussion
[InsanelyMac topic](http://www.insanelymac.com/forum/topic/311293-applealc-—-dynamic-applehda-patching/) in English  
[AppleLife topic](https://applelife.ru/threads/applealc-dinamicheskij-patching-applehda.1171672/) in Russian

#### Donations
Writing and supporting code is fun but it takes time. If you want to thank the author for his work consider contributing, bugreporting, or providing the support to other users.
