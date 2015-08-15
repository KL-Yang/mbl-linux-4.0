# mbl-linux-4.0
WD My Book Live Kernel 4.0 (can apply on 4.1.y) patches

This is patch set to support My Book Live. Mostly are sata dirve and configuration ported from stock 2.6.32 kernel.
More information can be found on: http://kl-yang.blogspot.sg

This patch and config example allow you run Debian Jessie on MyBook Live as a headless mini server.

A debian Jessie rootfs with kernel 4.1.5 (sshd enabled) can be found:

https://drive.google.com/file/d/0B-PZDFHXqH6pM19XVWFoT3VlWk0/view?usp=sharing

The package must be unpaced to the first partition (ext2) of MBL, and is tested on the single drive nas.
Find the DHCP after boot, then ssh login as root and password is password.

Note:

The rootfs will NOT work on stock filesystem! The stock kernel use 64K page size (filesystem is also 64K page), 
My kernel use 16K page size (4K performance is bad), and only tested with filesystem of 4K page size (default on x86/64).
If none of them make any sense to you, just disassemble MBL to get the harddrive and connect to your PC's sata port (important),
repartition the drive, and unpack rootfs to the first partition (must format as ext2).
Then put harddrive back into MBL, it should boot up as a Debian Jessie headless server.
