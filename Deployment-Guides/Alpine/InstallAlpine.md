# Minimal Alpine Linux Setup with a Graphical Interface

1. Download the “Virtual” realease for your processor architecture at https://alpinelinux.org/downloads.

2. Spin up a VM or install on hardware with enough RAM and disk space, the mount the downloaded ISO.

3. Log in with the user `root` and no password, then run setup-alpine to install Alpine Linux to the disk.

4. Choose `sda` as the disk, `sys` as the use case and confirm you want the disk to be erased. Accepting everything else on default is fine.

5. After the installation succeeds, unmount the ISO and reboot the VM/PC.

6. After logging in as `root`, install some basic tools by running `apk add sudo nano bash`.

7. Create a non-root user by running adduser [username], set its password as prompted and add it to the sudoers by running nano /etc/sudoers and adding `[username] ALL=(ALL) ALL` after the line `root ALL=(ALL) ALL `.

## For a Graphical Interface follow these steps

1. Run `setup-xorg-base xfce4 lightdm-gtk-greeter xfce4-terminal chromium mousepad` to setup the graphical environment and install other needed programs.

2. Run rc-update add lightdm and rc-update add dbus so the graphical interface starts when the system boots up.

3. Finally run `rc-service lightdm` start to start the graphical environment.

# Enable Community Repositories in APK

1. Open the repositories file by running `sudo nano /etc/apk/repositories` and uncomment any line that contains `community` or `main` in it.

2. Exit nano by pressing `Ctrl+X` and then `Y` and then `Enter`.