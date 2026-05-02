-wifi:iwd (for archiso)

+: systemctl start iwd

+interactive promt: iwctl

+:station list

+:station name scan
  
+:station name get-networks

+:station name connect SSID

+:ping google.com (check)

-arinstall(archiso)

+: archinstall (bat dau install)


-package:

--------------------------------------------------------------------

+:sway,swaybg,waybar,xorg-xwayland

+:man

+:nano

+blutooth:bluez, bluez-utils, blueman

+:fastfetch

+:firefox

+:greetd, greete-regreet

+:kitty

+:nemo

+:networkmanager, network-manager-applet, nm-connection-editor

+:pipewire, pavucontrol, pipewire-audio

+:wofi
+:base-devel (--needed)

-----------------------------------------------------------------

+:git

+:yay (https://aur.archlinux.org/yay.git ,makepkg -si)

+:code (vscode)

+:eww (yay)

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

----------------------------------------------------------------
-network

+enable networkmanager:sudo systemctl enable NetworkManager --now

+nmtui de ket noi mang (nho tat iwd:sudo systemctl disable --now iwd)

 ----------------------------------------------------------------
 
(reboot)
 
	
