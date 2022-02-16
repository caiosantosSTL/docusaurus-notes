# How to install arch linux

## Intro

In this article, we gonna see how to install arch linux easily. Using a arch linux live CD we will be able to install the system, and is important make a test installation on a virtual machine like VirtualBox, to avoid complications.

---

## Disk partition

We use the cfdisk, beacuse is more easy to make partition. We gonna create just tree partition in that
example, the root, swap and bios partition.

## Formatting

Using the command `mkfs` we are able to format each partition

```
 mkfs.ext4 /dev/sda2
```
> to format the root partition

```
mkfs.fat -F32 /dev/sda1
```
> to format the bios boot partition

```
mkswap /dev/sda3
```
> to create the swap area

## Mount file system

```
mount /dev/sda2 /mnt
```
> mount on /mnt , the dir where we will install the root directory of linux

```
swapon /dev/sda3
```
> to activate the swap area

## Install the basic system

```
pacstrap /mnt base linux linux-firmware
```
> the command pacstrap is used to install the linux root directory

When the pacstrap installation is ended, we will create a fstab file using this command:
```
genfstab -U /mnt >> /mnt/etc/fstab
```

If you wish, we can see informations about the partition tree using this command:

```
lsblk
```

## Chroot

Now we will out from the live CD directoy using the command `arch-chroot`

```
arch-chroot /mnt 
```
> using this command, we will enter at the hard disk directory root

## Hostname

Hostname is the name of our PC

```
nano etc/hostname
```
or
```
echo "hostnamepc" >> /etc/hostname
```

## Config network

```
nano /etc/hosts
```
Inside the hosts file we will write:

```
127.0.0.1 localhost.localdomain localhost
::1       localhost.localdomain localhost
127.0.1.1 hostnamepc.localdomain hostnamepc
```
> note that, hostnamepc will be your hostname pc name

## Root password

It is very important create a root password, because if you not create a password, you will not be able to
enter on your system easily again.

```
passwd [password here]
```

## Create a user and user password

```
useradd -M -G users -S /bin/bash [name user]
```

and now the password for user

```
passwd [user password]
```

## Install the GUI

### Install display manager

The display manager is the login screen, place where the user will put your user name and password to be able
to enter to the system.

There is a lot display manager to install, but in that example, we will install `lxdm`, but before to install it, we will first install the display server xorg:

```
pacman -Sy xorg-server xorg-xinit
```
> the pacman is our package manager for Archlinux

And install video driver 

```
pacman -Sy xf86-video-vesa
```

And now we will install the display manager

```
pacman -Sy lxdm
```

### Install the desktop environment

Now we will install all visual ambient to our system, and we have a list of desktop environment:

* gnome
* lxde
* lxqt
* xfce4
* cinnamon
* etc ...

In this example, we will install gnome, beacuse is cool and very complete environment. It is important emphasize that, if we will install gnome, for example, gnome already has your own display manager, and while the gnome is installed, will appear a message if you want to replace your current display manager installed (in our example is lxdm), if apear that message, we will select to replace it, because the gnome display manager is really good.

## Bonus to install

It is important install the networkmanager, and a terminal, well, gnome already has your own terminal, but it is important install another:

```
pacman -Sy networkmanager, xfce4-terminal
```
> note that, exist a lot others terminal

```
pacman -Sy ntfs-3g dosfstools
```
> to be able arch linux understand ntfs and fat file system

## Install GRUB

In that example, we are using the BIOS boot, so:

```
pacman -Sy grub os-prober
```

and we install the grub

```
grub-install /dev/sda
```
> install it in all device

```
grub-mkconfig -o /boot/grub/grub.cfg
```

Doing this we will check if the display manager and network manager are active or not

```
systemctl status gdm
```
> if you are using other display manager, put the name instead gdm

If the status is not connected, we will conect using this command

```
systemctl enable gdm
```

And possibly we need activate the newtwork manager
```
systemctl enable NetworkManager
```

Then, we exit from /mnt and umount

```
exit 0
```

and

```
umount -R /mnt
```

then we restart the system

```
shutdown now
```

Disconnect the live cd and enter to the system installed on your HDD