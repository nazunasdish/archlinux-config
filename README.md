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
package:sway,swaybg,waybar,xorg-xwayland,swaylock,swayidle,nano





























-package:

--------------------------------------------------------------------

+:man


+blutooth:bluez, bluez-utils, blueman

+:fastfetch

+:firefox

+:greetd, greete-regreet

+:kitty

+:nemo,nemo-media-columns

+:networkmanager, network-manager-applet, nm-connection-editor

+:pipewire, pavucontrol, pipewire-audio

+:wofi

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



 
	
