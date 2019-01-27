# bandera-layout-linux

This is inspired by https://github.com/muromec/bandera-layout

Installation

```
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
