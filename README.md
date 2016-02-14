# mbl-linux-4.0
WD My Book Live Kernel 4.0 (now applies on 4.1.y) patches

This patch set support WD My Book Live (not Duo), mostly are sata dirve and configuration ported from stock firmware 2.6.32 kernel.
A little bit more information can be found on: http://kl-yang.blogspot.sg 
This patch and config example allow to run Debian Jessie on MyBook Live as headless server.

Debian Jessie rootfs with kernel 4.1.17 (sshd enabled) can be found here (kernel compiled natively on MBL, and rootfs use debootstrap):

https://drive.google.com/file/d/0B-PZDFHXqH6pcFowcVJESGtsVGs/view?usp=sharing
MD5sum:38fdb6931da035d0b9b0b8024d9a9a87

The package must be unpaced to the first partition (ext2) of MBL, and is tested on the single drive nas.
Find the DHCP after boot, then ssh login as root and password is password.

Some disccussion can be found on WD's forum:
https://community.wd.com/t/any-interests-in-kernel-4-0-on-my-book-live/60483

Note (BACKUP EVERYTHING BEFORE DOING ANY OF THIS and TAKE YOUR OWN RISK USING IT):

The rootfs will NOT work on stock filesystem! The stock kernel use 64K page size (filesystem is also 64K page), 
My kernel use 16K page size (4K performance is bad), and only tested with filesystem of 4K page size (default on x86/64).
If none of them make any sense to you, just disassemble MBL to get the harddrive and connect to your PC's sata port (important, not USB!),
repartition the drive, and unpack rootfs to the first partition (must be formated as ext2).
Then put harddrive back into MBL, it should boot up as a Debian Jessie headless server.
There is risk that it DOES NOT boot at all!
