# Home Row Control

If you use a shortcut keys with <kbd>Ctrl</kbd> often, you can create a more ergonomic layout by using <kbd>Caps Lock</kbd> and <kbd>Enter</kbd>, two big keys in the home row, as <kbd>Ctrl</kbd> modifiers.

You need not give up on the key behavior you are used to: <kbd>Enter</kbd> and <kbd>Caps Lock</kbd> will act as usual when you strike them a single time, or like <kbd>Ctrl</kbd> when held down as a modifier for other keys.

## Supported platforms

Home Row Control uses X11, which means no native Windows or Mac support.

_(help wanted to support other platforms! see bugs #1 and #2)_

### Dependencies

* [Xcape](https://github.com/alols/xcape)
* xmodmap (from `x11-server-utils`)
* posix sh (eg. `dash`)
* optionally systemd, to run automatically when you start your X session

_(help wanted to support auto-start for other init systems! see bug #8)_

### Installing

You can find binary packages (`deb`, `rpm`, and `tar`) plus a self-executing `.sh` installer in [releases](https://github.com/ryanprior/home-row-control/releases/latest).

## Usage

Run `_home_row_control` to activate for the current session. Optionally, set up your system to run that command automatically on login.

### Detailed explanation of effects

1. <kbd>Enter</kbd> is reassigned to <kbd>Hyper</kbd> which should
   have no effect in most contexts. When you press <kbd>Enter</kbd>,
   the system sees a key up and key down event corresponding to
   <kbd>Hyper</kbd> and also applies the same modifier as if a
   <kbd>Control</kbd> were held down.
   
   If you tap it briefly (<1 second) without pressing other keys
   between press and release, it will trigger the normal
   <kbd>Enter</kbd> behavior. This means the key press will not
   register immediately when you press, but will instead come a
   fraction of a second later upon release.

2. <kbd>Caps Lock</kbd> is reassigned to <kbd>Right Control</kbd>.
   When you press <kbd>Caps Lock</kbd> the system sees a key up and
   key down event corresponding to <kbd>Right Control</kbd> and
   applies its modifier.
   
   If you tap either <kbd>Caps Lock</kbd> or <kbd>Right Control</kbd>
   briefly (<1 second) without pressing any other keys between press
   and release, it will trigger the normal <kbd>Caps Lock</kbd>
   behavior.
   
   I chose to use <kbd>Right Control</kbd> this way because X11
   apparently doesn't recognize separate left- and right-
   <kbd>Hyper</kbd> keys. If you know of a better option that does not
   change the behavior of the normal control keys at all, please let
   me know.

## Building packages

You can use the included `package` script to build your own packages.
The packaging dependencies are:

* `ruby`
* `fpm` (installed as a ruby gem)
* `bash`
* `debuild` and `rpmbuild`

### Running the packaging script

1. in the project directory, run `bundle install`
2. run `bundle exec ./package`
