# Installation #

Unpack iscsi-target-box-X.X-bin.tgz on disk in root.
Install GRUB on this disk and edit menu.lst:
```
 title  Linux iSCSI Target Box
 root   (hd0,0)
 kernel /vmlinuz-linux root=/dev/sdb1 ro ip=<this-box-ip>::<gw-ip>:<netmask>::eth0:none
 initrd /initrd-iscsi.img
```

Where /dev/sdb1 - partition with `iscsi-target-etc` config directory in root.

# Configuration #

`iscsi-target-etc` - Local copy of configuration files copied in /etc at loading box.

In `iet` directory stored configuration for [iSCSI Enterprise Target](http://iscsitarget.sourceforge.net/) daemon.

File `rc.local` executed on startup system.

Put the changed `shadow` file in `iscsi-target-etc` for change root password (default: 666666)