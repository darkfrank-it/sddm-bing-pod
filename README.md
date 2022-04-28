# sddm-bing-pod
Set Microsoft Bing picture of the day as background of sddm of lubuntu theme.

## Installation
Root or sudo permission is needed to install this package.

~~~bash
sudo dpkg -i sddm-bing-pod-1.0.2-Linux.deb
~~~

## Configuration
Copy the settings file into this directory: `/etc/sddm-bing-pod/` and personalize the 
setting by uncomment the desidered parameter.

Available configuration with example:
> The mkt parameter determines which Bing market you would like to
> obtain your images from.
> Valid values are: en-US, zh-CN, ja-JP, en-AU, en-UK, de-DE, en-NZ, en-CA, it-IT.
`mktValue=en-US`
**Default value is determinated based on $LANG, if something not work try to set this setting.**

> $saveDir is used to set the location where Bing pics of the day
> are stored. $HOME holds the path of the current user's home directory
> The images will be saved in  $saveDir/www.bing.com/
`saveDir='/usr/local/share/sddm-bing-pod'`

> The desired Bing picture resolution to download
> Valid options: "_1024x768" "_1280x720" "_1366x768" "_1920x1080"
`picRes="_1920x1080"`

> The desired size of overlay text
> Recommend options: "24" "26" "28" "30"
`pointSize="30"`

> Print to image the copyright information that describe the image
> Valid options: "true", "false"
`picCopyright=true`

> Remove picture older than $picRemoveOld located into $saveDir
> Valid options: "-1": never remove, "1" remove 1 day old picture, "2" remove 2 day old picture and so on 
`picRemoveOld=7`

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

## TODO
