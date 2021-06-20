# How-To-Actually-Dual-Boot

### Example Windows Dual Boot, the retard/safe way

*This makes it to where you can't fuck up your windows install. And by 'you' I mean you specifically, but also Linux Installers doing dumb shit and self-destructing your efi*

1) Format and install windows. Use like 70% of your drive for it.

2) You'll have 3-4 partitions post-install. [  fat32(EFI)  ]/[  NTFS(Big)  ]/[  idk(Recovery  ]/[ msr/randomjunk ]

3) Don't fucking touch those partitions, and don't let Linux touch those. I mean it, don't.

4) Boot Linux and open Gparted. If you don't have Gparted, you should consider 'is it us that has forgotten god, or god that has forgotten us?'

5) On that 30% extra create [Fat32-512MB]/[linuxswap-2GB(Optional)]/[EXT4-24GB/remainder of drive)

6) Click Apply. After it is done right click the EFI YOU JUST MADE and add the 'boot/ESP flag'.
*(Protip: Name your fucking partitions or you're gonna have a bad time one day. Promise.)*

7) Install Linux onto those and bootloader onto that fat32 partition you made. Don't combine the Linux/Windows EFI if you try out other distros a lot, don't know what you're doing, aren't wanting to restart from Step 1 because you didn't listen to Step 3. 

8) Select which device @boot instead of having some gay-ass grub menu, thus saving hours of your life. It's not graceful, but you've saved some of your short, pathetic, nerdy, selfish, yet beautiful, life. 

*You can also install grub after you're done (On the LINUX EFI DONT TOUCH WINDOWS), change the main boot partition in your bios to partition 4/5 or whatever, and it works just like a dual boot should; but rarely does. 

*Refind works but is pretty rude, will pimp-smack your not-to-be-touched windows EFI, and also completely hideous out-of-the-box.

*And you know the rule the first rule of systemd-boot don't you? 
**The first rule of systemd-boot is that we don't use systemd-boot.**
