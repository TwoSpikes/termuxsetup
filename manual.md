# Installing F-Droid

- go to `f-droid.org`
- download f-droid apk
- install f-droid
- remove f-droid apk

# Installing Hacker's Keyboard

- open f-droid
- download Hacker's Keyboard (I have version v.1.41.1 (version in app is not always matches version in apk))
- open Hacker's Keyboard
- press `enable keyboard`
- enable keyboard
- press `set input method`
- set input method
- press `input languages`
- setup input languages (select `English [en]` and `Russian [ru]`)
- press `Keyboard mode, portrait`
- select `Full 5-row layout`
- uncheck `Autosubstitution of uppercase`
- uncheck `Douple-tap Shift mode`
- press `Key feedback settings`
- check `Haptic feedback`
- press `Vibrate duration`
- select `20 ms`
- uncheck `increase pressed`
- go back
- press `Gesture and key actions`
- press `Swipe up`
- select `Increase height`
- press `Swipe down`
- select `Decrease height`
- press `Swipe left`
- select `Toggle extension row`
- go back
- press `Ctrl-A (select all) override`
- select `Use Ctrl-A (no override)`
- press `Ctrl key code`
- select `Left Ctrl`
- press `Alt key code`
- select `Left Alt`
- press `Meta key code`
- select `Left Meta`
- press `Popup mini-keyboard contents`
- select `No popups, use auto-repeat`
- uncheck `Suggest variants`

# Installing Termux

- open f-droid
- download Termux
- install Termux
- open Termux

# Setup Termux

- $ rm $PREFIX/etc/motd
- press `<Volume Up + k>` to remove toolbar
- $ termux-change-repo
- select your favorite mirror
- $ pkg update
- $ pkg upgrade
- $ termux-setup-storage
- $ pkg uninstall nano ed command-not-found

# Installing proot-distro

- $ pkg install proot-distro

# Setup Alpine

- $ proot-distro install alpine

# Login Alpine

- $ proot-distro login alpine

Note: Section named as `<some_program>::<something>` mean that you must do operations in `<some_program>`. \
For example, `Alpine::Setup` means that you must be logged into Alpine.

# Alpine::Setup

- $ apk update
- $ apk upgrade
- $ apk add shadow coreutils util-linux busybox-extras-openrc findutils usbutils pciutils iproute2

# Alpine::Timezone setup

- $ apk add tzdata tzdata-doc
- $ cp /usr/share/zoneinfo/Europe/Moscow /etc/localtime

Check your date with:

- $ date

Now you can uninstall tzdata

- $ apk del tzdata-doc tzdata

# Alpine::Doas setup

- $ apk add doas doas-doc
- $ nvim /etc/doas.conf

Todo: doas in now working for me (`doas: timestamp uid, gid or mode wrong`)

# Alpine::Man setup

- $ apk add man-pages mandoc docs

Note: notation like `<variable>` means that you enter this command replacing `<variable>` with variable (without triangle brackets)

# Alpine::Git setup

- $ apk add git
- $ git config --global user.name "<Your_name>"
- $ git config --global user.email "<Your_email>"
- $ git config --global init.defaultBranch master

# Alpine::Zsh setup

- $ apk add zsh

# Alpine::Nvim setup

- $ apk add neovim neovim-doc

# Alpine::Emacs setup

- $ apk add emacs

Todo: It is not executing from shell, I do not know why

# Alpine::Tmux setup

- $ apk add tmux

# Alpine::Byobu setup

- $ apk add byobu

# Alpine::Dotfiles setup

- $ git clone --depth=1 https://github.com/TwoSpikes/dotfiles
- $ cp ~/dotfiles/.bashrc ~/
- $ cp ~/dotfiles/timer.sh ~/dotfiles/checkhealth.sh ~/dotfiles/xterm-color-table.vim ~/dotfiles/tsch.sh ~/
- $ mkdir ~/.config
- $ cp -r ~/dotfiles/.config/nvim/ ~/.config/
- $ cp ~/dotfiles/blueorange.vim /usr/share/nvim/runtime/colors/
- $ cp -r ~/dotfiles/.emacs.d/ ~/
- $ cp ~/dotfiles/.tmux.conf ~/

# Uninstall Alpine

- $ proot-distro uninstall alpine

# Reset Alpine

- $ proot-distro reset alpine

# Uninstall proot-distro

- $ pkg uninstall proot-distro
- $ apt autoremove

# Troubleshooting

- check how you entered command
- repeat your command
- check your Internet connection
- check if Termux have access to Internet
- check if Termux have access to Storage
- check if Termux/device/keyboard responding
- if in Alpine: run command with doas
- relogin to Alpine
- restart Termux
- reset Alpine
- reinstall Alpine
- reinstall proot-distro
- Do in Termux: $ pkg update && pkg upgrade
- Do in Alpine: $ apk update && apk upgrade
- reboot device
- clear cache/files of Termux
- reinstall Termux
- root your device
