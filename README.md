# Post-install settings
#### Configure mkinitcpio.conf
Remove the hook: consolefont. Additionally, for Nvidia-users, for early loading add the Nvidia modules to MODULES=, like this MODULES=(nvidia nvidia_modeset nvidia_uvm nvidia_drm). I also like to remove the fallback options for linux kernels. These can be found under /etc/mkinitcpio.d/linux.preset.

#### Hooks
Some useful hooks to automate pacman actions. I have them uploaded in this repository, and just needs to be placed in /etc/pacman.d/hooks.

#### Configure paru
Configuration for paru can be found in /etc/paru.conf. I uncomment usually, BottomUp, RemoveMake, CleanAfter and NewsOnUpgrade. Also uncomment bin and define your preferred file manager.

#### SDDM-Wayland
https://wiki.archlinux.org/title/SDDM#Wayland, and apply Wayland-settings on SDDM in System-settings. This requires the package `sddm-kcm`. If you want a clean looking theme, check out [Silent SDDM](https://github.com/uiriansan/SilentSDDM)!

#### Fcitx5
Add in /etc/environment
```
GTK_IM_MODULE=fcitx
QT_IM_MODULE=fcitx
XMODIFIERS=@im=fcitx
```

#### KDE Connect
In order to use, follow this wiki: https://wiki.archlinux.org/title/KDE#KDE_Connect. If using ufw, you need to open the port these specific ports, which can be done like this: `sudo ufw allow 1714:1764/tcp` and `sudo ufw allow 1714:1764/udp`. The package `sshfs` is needed to access the filesystem of your phone. 

#### Configure Wi-Fi Regulatory Domain
Have wireless-regdb installed and edit the file /etc/conf.d/wireless-regdom to uncomment your country. Effects are taken on next reboot.
