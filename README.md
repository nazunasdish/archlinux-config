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

+:sway,swaybg,waybar,xorg-xwayland,swaylock,swayidle

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

+:mako

+:base-devel (--needed)

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
+Application Compatibility:them cai nay vao ~/.bashrc de mot so ung dung tuong thich (

	export MOZ_ENABLE_WAYLAND=1
	
	export QT_QPA_PLATFORM=wayland
	
	export GDK_BACKEND=wayland,x11
	
)

----------------------------------------------------------------
-network

+enable networkmanager:sudo systemctl enable NetworkManager --now

+nmtui de ket noi mang (nho tat iwd:sudo systemctl disable --now iwd)

 ----------------------------------------------------------------
 
(reboot)
 
	
