-wifi:

+:systemctl start iwd

+:iwctl

+:station list

+:station *name* scan
  
+:station *name* get-networks

+:station *name* connect *SSID*

+:quit

---------------------------------------

-arinstall

+:archinstall

bootloader:systemd-boot

profile:minimal

audio:pipewire

power management:power-profiles-daemon

firewall:ufw

bluetooth, printservice,... on

--------------------------------------

-package:sway,swaybg,waybar,xorg-xwayland,swaylock,swayidle,nano,firefox,greetd,greetd-regreet,kitty,wofi

-:systemctl enable greetd

-cau hinh tam thoi /etc/greetd/config.toml:

```
 [terminal]
# The VT to run the greeter on. Can be "next", "current" or a number
# designating the VT.
vt = 1

# The default session, also known as the greeter.
[default_session]

# `agreety` is the bundled agetty/login-lookalike. You can replace `/bin/sh`
# with whatever you want started, such as `sway`.
command = "sway --config /etc/greetd/sway-config" #sua dong nay

# The user to run the command as. The privileges this user must have depends
# on the greeter. A graphical greeter may for example require the user to be
# in the `video` group.
user = "greeter"

```

-cau hinh tam thoi /etc/greetd/sway-config:

```

exec "regreet; swaymsg exit"

```

-cau hinh tam thoi cho sway:

+:mkdir -p ~/.config/sway

+:cp /etc/sway/config ~/.config/sway/config

+nano ~/.config/sway/config roi sua nhu sau:

++: set $term foot -> set $term kitty

++: set $menu wmenu-run -> set $menu wofi --show drun

++:bar{........} -> exec waybar
-reboot

---------------------------------------

sudo pacman -S --needed git base-devel

git clone https://aur.archlinux.org/yay.git

cd yay

makepkg -si

---------------------------------------

package:polkit-gnome, blueman,pavucontrol,fastfetch,nemo

them vao swayconfig "exec /usr/lib/polkit-gnome/polkit-gnome-authentication-agent-1"

-dat kitty lam terminal cho nemo:gsettings set org.cinnamon.desktop.default-applications.terminal exec 'kitty'

---------------------------------------------

package:networkmanager, network-manager-applet

sudo systemctl disable --now iwd.service

sudo systemctl enable --now NetworkManager.service

them vao swayconfig "exec nm-applet --indicator"

reboot

------------------------------------------------

sudo pacman -S noto-fonts noto-fonts-cjk noto-fonts-emoji noto-fonts-extra ttf-jetbrains-mono-nerd

fc-cache -fv

-----------------------------------------------

-package: fcitx5 fcitx5-unikey fcitx5-configtool fcitx5-gtk fcitx5-qt

-them vao /etc/environment:

```
GTK_IM_MODULE=fcitx
QT_IM_MODULE=fcitx
XMODIFIERS=@im=fcitx
SDL_IM_MODULE=fcitx
GLFW_IM_MODULE=fcitx
```
-sway config: exec fcitx5 -d

reboot 

-config:fcitx5-configtool

--------------------------------------------------------------------

package:cliphist

-swayconfig:

```
exec wl-paste --type text --watch cliphist store
exec wl-paste --type image --watch cliphist store
bindsym $mod+v exec cliphist list | wofi --dmenu | cliphist decode | wl-copy
```







+:mako

+:code (vscode)

+:eww (yay)

+:gvfs-mtp

+strawberry (yay)

+apparmor

+:spotify-launcher

+:libreoffice-still

+:guvcview

 --------------------------------------------------------------

-apparmor

	+enable:systemctl enable apparmor

			systemctl enable auditd

	+chinh lai boot(doi voi truong hop bat uki(unified kernel image))(

		sudo nano /etc/kernel/cmdline

		them vao dong root:lsm=landlock,lockdown,yama,integrity,apparmor,bpf

		capnhat:sudo bootctl update
				sudo mkinitcpio -P

		reboot
	)
	+enforce tat ca:sudo aa-enforce /etc/apparmor.d/* (chi enforce ung dung can bao mat)








----------------------------------------------------------------------------------------------------------------

**sua loi "Mount point '/boot' which backs the random seed file is world accessible, which is a security hole!"

sudo nano /etc/fstab roi sua dmask, fmask thanh o phan /boot thanh dmask=0077, fmask=0077



 
	
