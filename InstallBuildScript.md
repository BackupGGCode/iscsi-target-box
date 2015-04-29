# Introduction #

Manual for [mkinitcpio](http://wiki.archlinux.org/index.php/Mkinitcpio) on Arch Wiki


# Details #

Installing for dependencies:
  * `pacman -S mkinitcpio-nfs-utils`
  * install [iscsitarget-kernel](http://aur.archlinux.org/packages.php?ID=24067) and [iscsitarget-usr](http://aur.archlinux.org/packages.php?ID=24069) from AUR or compile by yourself fresh version from iSCSI Enterprise Target [homepage](http://iscsitarget.sourceforge.net/)
  * unpack iscsi-target-box-X.X-src.tgz in /usr/lib/initcpio/
  * create link for install script: `ln base-iscsi /usr/lib/initcpio/install/base-iscsi`

Generate initramfs:
> `mkinitcpio -c /usr/lib/initcpio/iscsi-target-box/mkinitcpio.conf -g /boot/initrd-iscsi.img`

Quick test with QEMU:
> `qemu -snapshot -kernel /boot/vmlinuz-linux -initrd /boot/initrd-iscsi.img -hda /dev/sda -append "root=/dev/sda1 ro"`