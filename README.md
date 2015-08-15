# mbl-linux-4.0
WD My Book Live Kernel 4.0 (can apply on 4.1.y) patches

This is patch set to support My Book Live. Mostly are sata dirve and configuration ported from stock 2.6.32 kernel.
More information can be found on: http://kl-yang.blogspot.sg

This patch and config example allow you run Debian Jessie on MyBook Live as a headless mini server.

A debian Jessie rootfs with kernel 4.1.5 (sshd enabled) can be found:
https://drive.google.com/file/d/0B-PZDFHXqH6pM19XVWFoT3VlWk0/view?usp=sharing
The package must be unpaced to the first partition (ext2) of MBL, and is tested on the single drive nas.
Find the DHCP after boot, then ssh login as root and password is password.
