---
title: "Enabling BitLocker and BitLocker Screen Startup"
date: 2021-04-05T01:24:37+01:00
draft: false
toc: false
images:
tags: [BitLocker, Windows, Encryption]
---
![BitLocker-Header](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/bitlocker-header.jpg "BitLocker-Header")

This is a step by step guide for those who want to enable bitlocker on their main Windows c drive and also want to enable the BitLocker screen when booting up their machine. 

**Prerequisites:** </br>
For this you'll need to have a [TPM](https://docs.microsoft.com/en-us/windows/security/information-protection/tpm/trusted-platform-module-overview "docs.microsoft.com - Trusted Platform Module Technology Overview") version of 1.2 or later.

Applies to:
* Windows 10
* Windows Server 2016
* Windows Server 2019

### Implementation

1. Open mmc.exe
2. File > Add/Remove snap in
3. Add into the selected  snap-ins the "Local Computer Policy"
4. Expand > Computer Configuration
5. Administrative Templates
6. Windows Components
7. BitLocker Drive Encryption
8. Operating System Drives

Double click on "Require additional authentication at startup" and enable it </br>
Untick the "Allow BitLocker without a compatible TPM (requires a password or a startup key on a USB flash drive)

Double click on "Allow enhanced PINs for startup" and enable it.

![mmc](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/mmc.jpg "mmc")

You can now close the mmc console without having to save it. </br>
Type in bitlocker on the Windows magnifier icon (bottom left hand side on tasbar). </br>
Click on Manage BitLocker. </br>
Tun BitLocker on. </br>

![turn-bitlocker-on](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/turn-bitlocker-on.jpg "Turn Bitlocker on")

Enter a PIN (recommended)

![enter-pin](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/enter-pin.jpg "Enter a PIN")

Type in your BitLocker Password and select "Set PIN"

![type-pin](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/type-pin.jpg "Type a PIN")

Choose how you want to back up your recover key

![backup](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/backup.jpg "How do you want to back up your recovery key?")

I would select the first option and one of the other two options or all.
You can do all of them.
</br>

The recovery will come in handy in case you do a BIOS/UEFI update as it will detect a change and only once after the update, it will prompt for the recovery key.

![how-much-to-encrypt](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/how-much-to-encrypt.jpg "Choose how much of your drive to encrypt")

If this a fixed main drive that you use to load your Windows then select the first option.
New encryption mode (best for fixed drives on this device)

![encryption-mode](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/encryption-mode.jpg "Select which encryption mode to use")

![ready-to-encrypt](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/ready-to-encrypt.jpg "Are you ready to encrypt this drive?")

Restart your machine

![restart](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/restart.jpg "The computer must be restarted")

Now you will see the initial BitLocker screen prompting for the BitLocker password.

![bitlocker-screen](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/bitlocker-screen.jpg "BitLocker Screen")

After logging back in, BitLocker will still be in progress but won't take long if you're on an SSD drive.

Click on your hidden icons at the bottom left hand side of your taskbar.
Double click on the BitLocker icon.

![hidden-icons](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/hidden-icons.jpg "Hidden Icons")

![encrypting1](/posts/Enabling-BitLocker-and-BitLocker-Screen-Startup/encrypting.png "Encrypting...")

**References:** </br>
+ https://docs.microsoft.com/en-us/windows/security/information-protection/bitlocker/bitlocker-overview
+ https://docs.microsoft.com/en-us/windows/security/information-protection/tpm/trusted-platform-module-overview

