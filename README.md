# Home Row Control

If you use a shortcut keys with <kbd>Ctrl</kbd> often, you can create a more ergonomic layout by using <kbd>Caps Lock</kbd> and <kbd>Enter</kbd>, two big keys in the home row, as <kbd>Ctrl</kbd> modifiers.

You need not give up on the key behavior you are used to: <kbd>Enter</kbd> and <kbd>Caps Lock</kbd> will act as usual when you strike them a single time, or like <kbd>Ctrl</kbd> when held down as a modifier for other keys.

## Supported platforms

Home Row Control uses X11, which means no native Windows or Mac support. (help wanted! see bugs #1 and #2)

## Dependencies

* [Xcape](https://github.com/alols/xcape)
* xmodmap
* bash

## Usage

Run `_home_row_control` to activate for the current session. Optionally, set up your system to run that command automatically on login.
