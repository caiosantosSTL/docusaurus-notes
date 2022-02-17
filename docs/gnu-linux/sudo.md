# Add sudo

To add sudo in your system we will install it as a root

```
apt install sudo
```

and

```txt
usermod -aG sudo username
```

And using nano text editor we will edit the file sudoers from /etc directory

```txt
nano /etc/sudoers
```

And under the comentary #User privilege specification we will write

```txt
username ALL=(ALL:ALL) ALL
```

finished

