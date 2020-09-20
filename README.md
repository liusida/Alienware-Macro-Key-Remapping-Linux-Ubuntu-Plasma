# Alienware-Macro-Key-Remapping-Linux-Ubuntu-Plasma

These macro keys slept for too long in Linux system, until they were finally woke up!

# Scancode for Macro Keys From X,1,2,...,9

XF86LaunchX = e011
XF86Launch1 = e012
XF86Launch2 = e013
XF86Launch3 = e014
XF86Launch4 = e015
XF86Launch5 = e016
XF86Launch6 = e017
XF86Launch7 = e018
XF86Launch8 = e01a
XF86Launch9 = e01b

Infomation obtained using:

```bash
dmesg | grep key
```

# Default keycode for Macro Keys

This map is meaningful, but some of the keycode cannot be seen by KDE or `xev`.

keycode 128 = XF86LaunchA NoSymbol XF86LaunchA
keycode 156 = XF86Launch1 NoSymbol XF86Launch1
keycode 157 = XF86Launch2 NoSymbol XF86Launch2
keycode 192 = XF86Launch5 NoSymbol XF86Launch5
keycode 193 = XF86Launch6 NoSymbol XF86Launch6
keycode 194 = XF86Launch7 NoSymbol XF86Launch7
keycode 195 = XF86Launch8 NoSymbol XF86Launch8
keycode 196 = XF86Launch9 NoSymbol XF86Launch9
keycode 210 = XF86Launch3 NoSymbol XF86Launch3
keycode 211 = XF86Launch4 NoSymbol XF86Launch4
keycode 212 = XF86LaunchB NoSymbol XF86LaunchB

Infomation obtained using:

```bash
xmodmap -pke | grep Lau
```

# Map Scancode to Keycode

Finally, I decided to set up the left 6 macro keys and one right macro keys. Cannot find available key slot for the rest three.

create a file in `/etc/init.d/` with arbitrary name (I used `macrokey_remap`), and put these commands in.

```bash
# XF86WakeUp
setkeycodes e011 143
# XF86Launch1
setkeycodes e012 148
# XF86Launch2
setkeycodes e013 149
# XF86Launch5
setkeycodes e014 184
# XF86Launch6
setkeycodes e015 185
# XF86Calculator
setkeycodes e016 140
# TouchpadToggle
setkeycodes e017 191
# Unknown
# setkeycodes e018 188
# setkeycodes e01a 202
# setkeycodes e01b 203
```

If `xev` can see the key press, KDE Global Shortcut Setting can use the key.

# According to Global Shortcut Settings ?

yet another different values

148 = Launch(3)
149 = Launch(4)
184 = Launch(7)
185 = Launch(8)

Infomation obtained while I was setting them in Global Shortcut:

# Show key code

Another advanced tool which can see any key pressed (at least we know the keyboard has no problem):

```bash
sudo showkey
```
