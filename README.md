# mbl-linux-4.0
WD My Book Live Kernel 4.0 (now applies on 4.1.y) patches

This is patch set to support WD My Book Live. Mostly are sata dirve and configuration ported from stock 2.6.32 kernel.
More information can be found on: http://kl-yang.blogspot.sg

This patch and config example allow you run Debian Jessie on MyBook Live as a headless mini server.

A debian Jessie rootfs with kernel 4.1.5 (sshd enabled) can be found here:

https://drive.google.com/file/d/0B-PZDFHXqH6pM19XVWFoT3VlWk0/view?usp=sharing

Some disccussion can be found on WD's forum:
https://community.wd.com/t/any-interests-in-kernel-4-0-on-my-book-live/60483

A newer kernel (only) 4.1.15 (with openvpn and strongswan related module enabled):

https://drive.google.com/file/d/0B-PZDFHXqH6pcndaQlI2U09ieGc/view?usp=sharing

MD5:46d325e772922de042e381a183a9e9c6

The package must be unpaced to the first partition (ext2) of MBL, and is tested on the single drive nas.
Find the DHCP after boot, then ssh login as root and password is password.

Note (BACKUP EVERYTHING BEFORE DOING ANY OF THIS):

The rootfs will NOT work on stock filesystem! The stock kernel use 64K page size (filesystem is also 64K page), 
My kernel use 16K page size (4K performance is bad), and only tested with filesystem of 4K page size (default on x86/64).
If none of them make any sense to you, just disassemble MBL to get the harddrive and connect to your PC's sata port (important, not USB!),
repartition the drive, and unpack rootfs to the first partition (must be formated as ext2).
Then put harddrive back into MBL, it should boot up as a Debian Jessie headless server.
There is risk that it DOES NOT boot at all!
