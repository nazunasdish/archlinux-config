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

+:sway,waybar

+:man-db, man-pages, texinfo

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

+:yay (https://aur.archlinux.org/yay.git)

+:code (vscode)

+:eww (yay)


-cai dat greetd,regreet,sway

+enable greetd service:systemctl enable greetd 

+cau hinh /etc/greetd/config.toml

+cau hinh /etc/greetd/sway-config

+cau hinh /etc/greetd/regreet.toml

+cau hinh ~/.config/sway/config
 
(reboot)
 
	
