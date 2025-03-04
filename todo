
# Arch Linux Setup Guide

## Partitioning & Initial Setup
```bash
sudo pacman -Suy
lsblk
gdisk /dev/nvme0n1
# Use commands: x, z, y, y

pacman -Sy archlinux-keyring
pacman -S archinstall
```

## Chroot Configuration
```bash
nano /etc/pacman.conf
# Uncomment multilib repository

sudo pacman -S firefox flatpak flatpak-kcm zip rar kvantum fastfetch
```

## Post-Reboot Setup
```bash
# Install YAY + Change DNS to Cloudflare
sudo pacman -S --needed git base-devel && git clone https://aur.archlinux.org/yay.git && cd yay && makepkg -si
```

## Font Configuration
[Font Improvement Guide](https://github.com/davgar99/arch-linux-font-improvement-guide)

## NVIDIA Drivers
```bash
yay -S nvidia-open nvidia-utils lib32-nvidia-utils
```

## ASUS Control Utilities
[ASUS Linux Guide](https://asus-linux.org/guides/arch-guide/)

## Grub Configuration
```bash
sudo nano /etc/default/grub
# Set:
# GRUB_TIMEOUT=0
# GRUB_TIMEOUT_STYLE=hidden

sudo grub-mkconfig -o /boot/grub/grub.cfg
```

## Application Installation
### Core Applications
```bash
# System utilities
pacman -S waydroid,
https://github.com/casualsnek/waydroid_script

# Gtk apps cursor
xdg-desktop-portal-gtk

# Gaming
pacman -S steam 
pacman -S lutris
yay -S protonplus

# Media
yay -S stremio
pacman -S obs-studio
yay -S spotify
pacman -S easyeffects

# Utilities
pacman -S kcalc
pacman -S gwenview
```

### Flatpak Applications
```bash
flatpak install prismlauncher bedrocklauncher vesktop zenbrowser
```

## SDDM Cursor Fix
Create/edit `/etc/sddm.conf.d/10-wayland.conf`:
```ini
[General]
DisplayServer=wayland
GreeterEnvironment=QT_WAYLAND_SHELL_INTEGRATION=layer-shell

[Wayland]
CompositorCommand=kwin_wayland --drm --no-lockscreen --no-global-shortcuts --locale1
```

## Btrfs Snapshots
```bash
sudo pacman -S grub-btrfs
yay -S timeshift-autosnap

sudo systemctl enable --now grub-btrfsd.service
sudo systemctl edit --full grub-btrfsd
# Modify ExecStart to:
# ExecStart=/usr/bin/grub-btrfsd --syslog --timeshift-auto

sudo grub-mkconfig -o /boot/grub/grub.cfg
```
