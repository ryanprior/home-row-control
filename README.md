# Home Row Control

If you use a shortcut keys with <kbd>Ctrl</kbd> often, you can create a more ergonomic layout by using <kbd>Caps Lock</kbd> and <kbd>Enter</kbd>, two big keys in the home row, as <kbd>Ctrl</kbd> modifiers.

You need not give up on the key behavior you are used to: <kbd>Enter</kbd> and <kbd>Caps Lock</kbd> will act as usual when you strike them a single time, or like <kbd>Ctrl</kbd> when held down as a modifier for other keys.

## Supported platforms

Home Row Control uses X11, which means no native Windows or Mac support. (help wanted! see bugs #1 and #2)

### Dependencies

* [Xcape](https://github.com/alols/xcape)
* xmodmap
* bash

## Usage

Run `_home_row_control` to activate for the current session. Optionally, set up your system to run that command automatically on login.

### Detailed explanation of effects

1. <key>Enter</key> is reassigned to <key>Hyper</key> which should
   have no effect in most contexts. When you press <key>Enter</key>,
   the system sees a key up and key down event corresponding to
   <key>Hyper</key> and also applies the same modifier as if a
   <key>Control</key> were held down.
   
   If you tap it briefly (<1 second) without pressing other keys
   between press and release, it will trigger the normal
   <key>Enter</key> behavior. This means the key press will not
   register immediately when you press, but will instead come a
   fraction of a second later upon release.

2. <key>Caps Lock</key> is reassigned to <key>Right Control</key>.
   When you press <key>Caps Lock</key> the system sees a key up and
   key down event corresponding to <key>Right Control</key> and
   applies its modifier.
   
   If you tap either <key>Caps Lock</key> or <key>Right Control</key>
   briefly (<1 second) without pressing any other keys between press
   and release, it will trigger the normal <key>Caps Lock</key>
   behavior.
   
   I chose to use <key>Right Control</key> this way because X11
   apparently doesn't recognize separate left- and right-
   <key>Hyper</key> keys. If you know of a better option that does not
   change the behavior of the normal control keys at all, please let
   me know.
