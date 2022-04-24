# sddm-bing-pod
Set Microsoft Bing picture of the day as background of sddm of lubuntu theme.

## Installation
Root or sudo permission is needed to install this package.

~~~bash
sudo dpkg -i sddm-bing-pod-1.0.1-Linux.deb
~~~

## Manual run:
~~~bash
sudo sddm-bing-pod
~~~

## To run automaticcally at boot (maybe the picture change after sddm init, so you see the new picture at next login):
~~~bash
sudo systemctl --now enable sddm-bing-pod.service
~~~

## Uninstall
~~~bash
sudo apt-get remove sddm-bing-pod
~~~

Then you need to download original wall.png and copy to /usr/share/sddm/themes/lubuntu/wall.png with root permission.
The file must be owned by root to.
