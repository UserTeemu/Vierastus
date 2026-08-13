# Vierastus
A Finnish-friendly (and Swedish-friendly) XKB keymap for ANSI keyboards. Places ÅÄÖ in the same locations as the normal Finnish keyboard layout, but requires using right alt to access them. Compared to existing international keyboard layours, this is more intuitive coming from a Finnish keyboard and allows typing these letters with just one hand because the letters are close to right alt (compared to RALT+A for typing Ä in most existing layouts).

Additionally, this layout allows for easy typing of the euro symbol, section and ½ which are found in a normal Finnish keyboard, as well as en dash and em dash which are useful for typing dashes correctly ("ajatusviiva").

## Keys
- RALT + ' = Ä
- RALT + ; = Ö
- RALT + [ = Å
- RALT + E = €
- RALT + - = – (en dash)
- RALT + - + SHIFT = — (em dash)
- RALT + ` = §
- RALT + ` + SHIFT = ½

## Installation
The keymap can be installed in two ways:
1. as a standalone layout not under any country (country flags etc. will probably not be displayed in your UI of choice)
2. as a variant of the US layout

### X11-compatible installation
If you need X11 compatibility, you need to modify system layout files to install this keymap. Even if you use Wayland, you might come across some situations where this is needed. For example, KDE Plasma's layout preview only supports the X11 file paths [for now](https://bugs.kde.org/show_bug.cgi?id=509455).

#### Standalone layout installation
1. Copy `standalone/symbols/vierastus` to `/usr/share/X11/xkb/symbols`.
2. Add the `layout` element from `standalone/rules/evdev.xml` to `/usr/share/X11/xkb/rules/evdev.xml` (or `evdev.extras.xml`).
3. Done. Logging out or restarting is recommended.

#### Variant installation
1. Append the contents of `variant/symbols/us` (except the explicit default section) to the end of `/usr/share/X11/xkb/symbols/us`.
2. Add the `variant` element from `variant/rules/evdev.xml` to the existing US layout's `variantList` in `/usr/share/X11/xkb/rules/evdev.xml` (or `evdev.extras.xml`).
3. Done. Logging out or restarting is recommended.

### Easier user-specific installation (not X11-compatible)
1. Find or create directory `xkb` in `$XDG_CONFIG_HOME` (typically `~/.config`).
2. Copy the contents of this repository's `variant` or `standalone` directory to the `xkb` directory.
3. Done. Logging out or restarting is recommended.

### Easier system-wide installation (not X11-compatible)
Same as "Easier user-specific installation" but use [a system-wide XKB data directory](https://xkbcommon.org/doc/current/custom-configuration.html#xkb-data-locations).


## See also
- https://xkbcommon.org/doc/current/pages.html
- The de_se_fi keymap by Stephan Lachnit
- The basic Finnish keymap, Kotoistus, by Troy Korjuslommi (also acted as an inspiration for this project's name)
