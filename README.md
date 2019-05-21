# mbl-linux-4.0

WD My Book Live Kernel 4.0 (now applies on 4.19.y) patches

This patch and example kernel configuration support WD My Book Live (not Duo), the old drivers have been droped.
Now all the patches are from OpenWRT, so all the thanks to their great work.
Debian has stopped powerpc release after Jessie, but the powerpc port is still maintained.

Debian popwerpc port rootfs with kernel 4.9.44 (sshd enabled) can be found here (kernel compiled natively on MBL, 
and rootfs use debootstrap):

https://drive.google.com/open?id=1pJNQd6xacCGBOfPgc9ye-SehU7ekgmfU

MD5sum: 630420a54724a0b30bb566b4b24755fb

# If you want debootstrap a clean Debian

Be careful to check this bug report:
https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=927255

# Installation notes

The package must be unpaced to the first partition (sda1, and ext2 format) of MBL, and is tested on the single drive nas.
Find the DHCP after boot, then ssh login as root and password is password.

Some disccussion can be found on WD's forum:

https://community.wd.com/t/any-interests-in-kernel-4-0-on-my-book-live/60483

BACKUP EVERYTHING BEFORE DOING ANY OF THIS and TAKE YOUR OWN RISK USING IT:

The rootfs will NOT work on stock filesystem! The stock kernel use 64K page size 
(filesystem is also 64K page size, which performs better but makes data recovery harder).
The compiled kernel here use 4K page (compatible with x86 PC if you swap the HDD and insert on PC).
If none of them make any sense to you, just disassemble MBL to get the harddrive and connect to your PC's sata port (important, not USB!),
repartition the drive, and unpack rootfs to the first partition (sda1, must be formated as ext2).
Then put harddrive back into MBL, it should boot up as a Debian headless server.
Regenerate your SSH keys after installation! There is risk that it DOES NOT boot at all!
