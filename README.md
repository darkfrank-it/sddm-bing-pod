# sddm-bing-pod
Set Microsoft Bing picture of the day as background of sddm of lubuntu theme.

## Installation
Root or sudo permission is needed to install this package.

~~~bash
sudo dpkg -i sddm-bing-pod_<version>-<revision>_all.deb
~~~

## Configuration
Copy the settings file into this directory: `/etc/sddm-bing-pod/` and personalize the 
setting by uncomment the desidered parameter.

Available configuration with example:
> The mkt parameter determines which Bing market you would like to
> obtain your images from.
> Valid values are: en-US, zh-CN, ja-JP, en-AU, en-UK, de-DE, en-NZ, en-CA, it-IT.

**Default value is determinated based on $LANG, if something not work try to set this setting.**

`mktValue=en-US`


> $saveDir is used to set the location where Bing pics of the day
> are stored. $HOME holds the path of the current user's home directory
> The images will be saved in  $saveDir

`saveDir='/usr/local/share/sddm-bing-pod'`

> The desired Bing picture resolution to download
> Valid options: "_1024x768" "_1280x720" "_1366x768" "_1920x1080"

`picRes="_1920x1080"`


> Remove picture older than $picRemoveOld located into $saveDir
> Valid options: "-1": never remove, "1" remove 1 day old picture, "2" remove 2 day old picture and so on 

`picRemoveOld=7`

## Manual run:
~~~bash
sudo sddm-bing-pod
~~~

## Run automaticcally at boot

The new installation script automatically enable sddm-bing-pod.service
**Note:** Maybe the picture change after sddm init, so you see the new picture at next login


## Uninstall
~~~bash
sudo apt-get remove sddm-bing-pod
~~~

**Note:** Maybe you have to adjust setting in `/etc/sddm.conf`

## CHANGELOG

### v2.0.0-1 
- Redesigned the process. Now .deb package install a copy of sddm theme "lubuntu" that will be used to show downloaded Bing's picture-of-the-day with it's description (copyright) readed from a file and compose in qml (qt) inside a rectangle with text wrap. It's no more possible to disable the copyright feature, unless you manually copy the Main.qml file from lubuntu theme folder to the lubuntu-bing-pod theme folder inside `/usr/share/sddm/themes/`
