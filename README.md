# My Conky Desktop Theme

A theme originally developed by [burzumishi](https://github.com/burzumishi/myconky)

## Installation:

```
cd
git clone https://github.com/burzumishi/myconky.git
cd myconky/
cp -a conky ../.conky
cp -a lua ../.lua
cp -a conkyrc ../.conkyrc 
# do not forget installing the fonts!
cd ../.conky/fonts
su -c "cp * /usr/share/fonts/truetype/"
conky
```

## Autostart and .desktop file

This example uses `orca.desktop`, but we striped it down a lot.
It's just a base `*.desktop` file, any other could suffice.

```
cd ~/.config/autostart
cp /usr/share/applications/orca.desktop conky.desktop
su -c "ln -s /home/${USER}/.config/autostart/conky.desktop /usr/share/applications/conky.desktop"
vim conky.desktop 
orca.desktop
```

- This is how we created the file, ofc it's now cv-sourced at this repo.
- The `autostart` _thing_ is a _gnome-thing_
- It could be also set to autostart at `/usr/share/gnome/autostart/`

## Diffs from the original theme

This theme version was - and it's being - adapted for:

- Dual-core CPU (original was developed for a quad-core `proc/cpuinfo`)
- Wide screen - 23" (1980x1080)
- Audio workstation based on a FP10 firewire card

## Extra tip by original theme author

```
su
apt-get install gdm3 plymouth
plymouth-set-default-theme spinner
update-initramfs -u
update-grub2
```

Yup, he's a gnome warrior ^^U and it's a nice boot splash animation

## TODO

- [ ] better "install":
  - [ ] clone to .conky
  - [ ] use `ln -s` for .conkyrc and .lua

