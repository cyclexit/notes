# Ubuntu Note (Ubuntu 20.04 LTS)

## Software List
* Visual Studio Code(with the `Settings Sync` plug-in)
* Android Studio
* Firefox
* Opera

***

## Index
* [Setup](#setup)
  * [Chinese Pinyin Input](#chinese-pinyin-input)
  * [Dash to Dock](#dash-to-dock)
  * [Tweaks](#tweaks)
  * [Lid Close](#lid-close)
  * [Screen Lock](#screen-lock)
* [Functionality]
  * [Files Bookmark](#files-bookmark)
  * [Screenshots and Screencasts](#screenshots-and-screencasts)
  * [Clipboard](#clipboard)
***

## Setup
### Chinese Pinyin Input
[https://leimao.github.io/blog/Ubuntu-Gaming-Chinese-Input/](https://leimao.github.io/blog/Ubuntu-Gaming-Chinese-Input/)
### Dash to Dock
[https://github.com/micheleg/dash-to-dock](https://github.com/micheleg/dash-to-dock) </br>
This extension should be enabled in `Tweaks`. </br>
The settings of this extension can also be accessed in `Tweaks`.
* Position and size > Position on screen: bottom
* Position and size > Intelligent autohide
* Position and size > Icon size limit: 32
* Behavior > Click action > Minimize
* Appearance > Opacity > Fixed: 50%
### Tweaks
* Extensions > Dash to dock: enable
* Extensions > Desktop icons: disable
* Extensions > Desktop icons > Settings > Show the personal folder in the desktop: disable
  Extensions > Desktop icons > Settings > Show the trash icon in the desktop: disable
* Top Bar > Battery percentage: enable
* Top Bar > Clock > Weekday: enable
### Lid Close
[How to Change Lid Close Action in Ubuntu 18.04 LTS](https://tipsonubuntu.com/2018/04/28/change-lid-close-action-ubuntu-18-04-lts/) </br>
This also apply to Ubuntu 20.04 LTS.
### Screen Lock
* Settings > Blank Screen: Never
* Settings > Privacy > Screen Lock > Blank Screen Delay: Never
* Settings > Privacy > Screen Lock > Automatic Screen Lock: disable
* Settings > Privacy > Screen Lock > Lock Screen on Suspend: disable
* Settings > Privacy > Screen Lock > Show Notifications on Lock Screen: disable

## Functionality
### Files Bookmark
Open `Files`. Toggle the folder icon, and then you can see the the `New bookmark` section on the side bar.
### Screenshots and Screencasts
[https://help.ubuntu.com/stable/ubuntu-help/screen-shot-record.html](https://help.ubuntu.com/stable/ubuntu-help/screen-shot-record.html)
### Clipboard
```
sudo apt install CopyQ
```
In `Startup Application`, add `CopyQ`.