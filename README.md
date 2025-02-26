Connection

ip addr show
systemctl status sshd
passwd

connect via putty


Partiton / Initial setup
sudo pacman -Suy
lsblk
gdisk /dev/nvme0n1
x,z,y,y 

pacman -Sy archlinux-keyring
pacman -S archinstall




mirrors
profiles-desktop-kde
amd drivers
pipewire
networkmanager
user



nano /etc/pacman.conf
uncomment multilib

sudo pacman -S firefox 
sudo pacman -S flatpak
sudo pacman -S flatpak-kcm
sudo pacman -S zip,rar
sudo pacman -S kvantum
sudo pacman -S fastfetch


Yay

sudo pacman -S --needed git base-devel
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si

Nvidia + asusctl + grub (timeout)
yay -S nvidia-dkms nvidia-utils lib32-nvidia-utils

https://asus-linux.org/guides/arch-guide/
sudo nano /etc/default/grub
timeout 0
picker hidden
grub-mkconfig -o /boot/grub/grub.cfg



Apps
EasyEffects (settings start as a service) + Presets

yay -S waydroid 
https://github.com/casualsnek/waydroid_script
libndk

Spotify
ProtonPlus
Steam
Lutris
flatpak - PrismLauncher
flatpak - Vesktop
PCS2X
OBS
Stremio
Kcalc
Gwenview



SDDM CursorFix

/etc/sddm.conf.d/10-wayland.conf

[General]
DisplayServer=wayland
GreeterEnvironment=QT_WAYLAND_SHELL_INTEGRATION=layer-shell

[Wayland]
CompositorCommand=kwin_wayland --drm --no-lockscreen --no-global-shortcuts --locale1



Btrfs snapshots

sudo pacman -S grub-btrfs
yay -S timeshift-autosnap

sudo systemctl enable --now grub.btrfsd.service
sudo systemctl edit --full grub-btrfsd 
ExecStart=/usr/bin/grub-btrfsd --syslog --timeshift-auto
grub-mkconfig -o /boot/grub/grub.cfg










