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
