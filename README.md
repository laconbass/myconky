# My Conky Desktop Theme

A theme originally developed by [burzumishi](https://github.com/burzumishi/myconky)

## Diffs from the original theme

This theme version was - and it's being - adapted for:

- Dual-core CPU (original was developed for a quad-core `proc/cpuinfo`)
- Wide screen - 23" (1980x1080)
- Audio workstation based on a FP10 firewire card

## TODO

- [ ] better "install":
  - [ ] clone to .conky
  - [x] use `ln -s`
- [ ] Adjust and arrange indicator' size
- [ ] DPS load graph
- [ ] jackd info displays


## Installation:

```
cd
git clone https://github.com/burzumishi/myconky.git
ln -s myconky/conky .conky
ln -s myconky/conkyrc .conkyrc
mkdir -p .lua/scripts
ln -s ../../myconky/lua/scripts/rings.lua .lua/scripts/rings.lua
##
# do not forget installing the fonts!
#
cd .conky/fonts
su -c "cp * /usr/share/fonts/truetype/"
conky
```

## Extra tip by original theme author

```
su
apt-get install gdm3 plymouth
plymouth-set-default-theme spinner
update-initramfs -u
update-grub2
```

Yup, he's a gnome warrior ^^U and it's a nice boot splash animation


## Autostart and .desktop file

This example uses `orca.desktop`, but we striped it down a lot.
It's just a base `*.desktop` file, any other could suffice.

```
cd ~/.config/autostart
cp /usr/share/applications/orca.desktop conky.desktop
su -c "ln -s /home/${USER}/.config/autostart/conky.desktop /usr/share/applications/conky.desktop"
vim conky.desktop 
```

- This `autostart` _thing_ is a _gnome-thing_
- It could be also set to autostart at `/usr/share/gnome/autostart/`
- This is how we created the file, ofc it's now cv-sourced at this repo:

```
cd && mkdir -p .config/autostart
ln -s ../../myconky/config/gnome/conky.desktop .config/autostart/conky.desktop
```
