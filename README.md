# bandera-layout-linux

This is inspired by https://github.com/muromec/bandera-layout

Installation

```
wget https://raw.githubusercontent.com/samael33/bandera-layout-linux/master/ua
sudo cp ua /usr/share/X11/xkb/symbols/ua
```

Edit file `/usr/share/X11/xkb/rules/evdev.xml`
Add lines
```
...
        <variant>
          <configItem>
            <name>bandera</name>
            <description>Ukrainian (Bandera)</description>
          </configItem>
        </variant>
...
```
Small addition on ThinkPad make Fn-F11/F12 working under Linux

```
cat > /etc/udev/hwdb.d/99-local-keyboard.hwdb <<EOF
# "Keyboard" (Fn+F11) and "Favorites" (Fn+F12) by default generate
# KEY_KEYBOARD and KEY_FAVORITES, which is good. But those keycodes
# can't be handled by X, so remap them. Sigh.
evdev:name:ThinkPad Extra Buttons:dmi:bvn*:bvr*:bd*:svnLENOVO*:pn*
 KEYBOARD_KEY_45=prog1
 KEYBOARD_KEY_49=prog2
EOF
>>
systemd-hwdb update
udevadm trigger
```
Getting scancodes
```
showkey  --scancodes
```