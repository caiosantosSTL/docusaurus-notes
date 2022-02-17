# How to install QEMU

QEMU is a linux solution to create virtual machines

Using Debian family system, we will use that command to install:

* sudo apt install
* * qemu-kvm
* * libvirt-daemon-system
* * libvirt-clients
* * bridge-utils
* * virtinst
* * virt-manager

After install all programs, we will check if libvirt is activated

```
sudo systemctl is-active libvirtd
```

If it is not activated, we will activate it using this command:

```
sudo systemctl enable libvirtd
```

and

```
sudo systemctl start libvirtd
```

Now, we will check if my user is inside the group libvirt. We will check it using this command:

```
groups $USER
```

> it will show a list of groups that the current user is in. If it is not inside the group, we can add it using
`sudo usermod -aG libvirt $USER`

Now we will add the current user inside the `kvm` group

```
sudo usermod -aG kvm $USER
```
And we restart the system