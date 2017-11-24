# how to install your mom
make one full-disk partition in fdisk and
```shell
mkfs.ext4 /dev/sda1
mount /dev/sda1 /mnt
pacstrap -i /mnt base base-devel
genfstab -U -p /mnt >> /mnt/etc/fstab
arch-chroot /mnt /bin/bash
ln -sf /usr/share/zoneinfo/America/Chicago
hwclock --systohc --utc
rm -f /etc/locale.gen && echo en_US.UTF-8 UTF-8 | tee /etc/locale.gen && locale-gen
echo LANG=en_US.UTF-8 > /etc/locale.conf
echo cyberia > /etc/hostname
echo "127.0.1.1 cyberia.localdomain  cyberia" | tee -a /etc/hosts
passwd # and enter a password
exit
reboot
```
##### and now you're a cool kid
