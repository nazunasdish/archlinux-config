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

++: set $menu wmenu-run -> set $menu wofi --grun






















-package:

--------------------------------------------------------------------

+:man


+blutooth:bluez, bluez-utils, blueman

+:fastfetch


+:nemo,nemo-media-columns

+:networkmanager, network-manager-applet, nm-connection-editor

+:pipewire, pavucontrol, pipewire-audio


+:mako

+:base-devel (--needed)

+:git

+:yay (https://aur.archlinux.org/yay.git ,makepkg -si)

+:code (vscode)

+:eww (yay)

+:cliphist

+:wl-clipboard

+:fcitx5-im fcitx5-bamboo fcitx5-configtool

+:gvfs-mtp

+:noto-fonts noto-fonts-cjk noto-fonts-emoji noto-fonts-extra (fc-cache -fv, de update font)

+strawberry (yay)

+apparmor

+:spotify-launcher

+:libreoffice-still

+:maple-mono-nf-cn-unhinted (yay)

+:guvcview

-----------------------------------------------------------------

-cai dat greetd,regreet,sway

+enable greetd service:systemctl enable greetd 

+cau hinh /etc/greetd/config.toml

+cau hinh /etc/greetd/sway-config

+cau hinh /etc/greetd/regreet.toml

+cau hinh ~/.config/sway/config(

	copy default truoc de dung 
	
	:mkdir -p ~/.config/sway
	
	:cp /etc/sway/config ~/.config/sway/config


)

+them bien moi truong (#wayland,sway trong file /etc/environment)

----------------------------------------------------------------

-network

+enable networkmanager:sudo systemctl enable NetworkManager --now

+nmtui de ket noi mang (nho tat iwd:sudo systemctl disable --now iwd)

 ----------------------------------------------------------------

 -audio
 
	enable:systemctl --user enable --now pipewire pipewire-pulse wireplumber

 ------------------------------------------------------------------

-bluetooth

	enable:systemctl enable --now bluetooth

 -----------------------------------------------------------------

 -clipboard 
 
	+khoi dong cliphist trong sway (co trong file ~/.config/sway/config. ###cliphist)
	+gan keybind:trong sway config (#clipboard)

-Fcitx5 (xoa ibus neu co)
	
	+them bien moi truong (#fcitx trong /etc/environment)

	+tu khoi dong cung sway:(#fcitx trong ~/.config/sway/config)

	+reboot , set up:fcitx5-configtool

-Nemo
	+kitty lam terminal:gsettings set org.cinnamon.desktop.default-applications.terminal exec 'kitty'
	
 --------------------------------------------------------------

 -firefox
 

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



 
	
