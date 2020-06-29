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
  * [Default Command Line Editor](#default-command-line-editor)
  * [Show git branch name in the command line](#show-git-branch-name-in-the-command-line)
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
* Appearance > Use built-in theme: enable
* Behavior > Click action > Minimize
* Behavior > Click action > Settings > Shift+Click action: Launch new instance
* Behavior > Click action > Settings > Middle-Click action: Show window previews
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
### Default Command Line Editor
Switch default command line editor:
```bash
sudo update-alternatives --config editor
```
### Show git branch name in the command line
1. Open a terminal
    ```bash
    gedit ~/.bashrc
    ```
2. Find the following snippet
    ```bashrc
    if [ "$color_prompt" = yes ]; then
        PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
    else
        PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
    fi
    ```
3. Replace the snippet above
    ```bashrc
    # git branch info if present
    parse_git_branch() {
        git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)  /(\1)/'
    }
    
    if [ "$color_prompt" = yes ]; then
        PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]  \u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[33m\]$  (parse_git_branch)\[\033[00m\]\$ '
    else
        PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w$  (parse_git_branch)\$ '
    fi
    ```
### Solaar
Install this one to interact with Logitech Unify Receiver.
```bash
sudo apt-get install solaar
```
Logout and login again. Probably you need to re-plug in the receiver.