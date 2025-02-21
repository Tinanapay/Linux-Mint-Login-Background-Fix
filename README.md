To change login backgroun in linux mnt xcfe!(using LightDM GTK+ Greeter Settings)

move ur choosen pic to /usr/share/backgrounds/ use-
--------------------------------------------
sudo mv /path/to/your/image.png /usr/share/backgrounds/
--------------------------------------------

give read access (LightDM needs)-
--------------------------------------------
sudo chmod 644 /usr/share/backgrounds/image.png
--------------------------------------------

to be sure LightDM can access-
--------------------------------------------
sudo chown root:root /usr/share/backgrounds/image.png
--------------------------------------------

now go back to LightDM GTK+ Greeter Settings, select the image u want from /usr/share/backgrounds/image.png, and then save.

=================================================================================
ADDITIONAL:

❗ If Background Still Doesn't Change After Restart

Linux Mint uses Slick-Greeter by default, so maybe LightDM GTK+ Greeter isn't even active. 🤡

to confirm run-
--------------------------------------------
grep -i greeter /etc/lightdm/*.conf /etc/lightdm/*.conf.d/*
--------------------------------------------

if it say 
--------------------------------------------
"greeter-session=slick-greeter"
--------------------------------------------

then yah its slick-greeter lmao, so now do
--------------------------------------------
sudo nano /etc/lightdm/slick-greeter.conf
--------------------------------------------

and then find this, its usually the first one
--------------------------------------------
[Greeter]
background=/usr/share/backgrounds/reli.png
--------------------------------------------


Save (CTRL + X, then Y, then ENTER`), and restart LightDM:
--------------------------------------------
sudo systemctl restart lightdm
--------------------------------------------
and ur done yayyy
