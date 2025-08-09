# grub-default-title-kernel
A Patch of `grub.d/10_linux` to make it possible to set REAL DEFAULT kernel version for grub2. I call it `title version` because it is the first options in the grub2 menu.

## Usage:
1. Replacing `/etc/grub.d/10_linux` by the file here.

2. Editing `/etc/default/grub` ( or `/etc/default/grub` according to your distro ), adding like
```
GRUB_TITLE_KERNEL_VERSION=6.1.
```
This means the default option in grub2 will use the lastest patch version of linux 6.1

Noting the point (`.`) in `6.1.`, it is used to distinguish 6.1 and (for example) 6.12

You can also use version string like `6.` or `6.1.6`, but it is seldom useful.

3. `sudo grub2-mkconfig -o /boot/grub2/grub.cfg `
