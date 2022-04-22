# sddm-bing-pod
Set Microsoft Bing picture of the day as background of sddm of lubuntu theme.

# Installation
~~~bash
sudo dpkg -i sddm-bing-pod-1.0.0-Linux.deb
~~~

## Manual run:
~~~bash
sudo sddm-bing-pod
~~~

## To run automaticcally at boot (maybe the picture change after sddm init, so you see the new picture at next login):
~~~bash
sudo systemctl --now enable sddm-bing-pod.service
~~~

