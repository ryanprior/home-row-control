# Home Row Control

If you use a shortcut keys with <kbd>Ctrl</kbd> often, you can create a more ergonomic layout by using <kbd>Caps Lock</kbd> and <kbd>Enter</kbd>, two big keys in the home row, as <kbd>Ctrl</kbd> modifiers.

You need not give up on the key behavior you are used to: <kbd>Enter</kbd> and <kbd>Caps Lock</kbd> will act as usual when you strike them a single time, or like <kbd>Ctrl</kbd> when held down as a modifier for other keys.

## Supported platforms

Home Row Control uses `kmonad`, which is supported on Linux (X11 & Wayland),
macOS and Windows. So you're likely covered.

### Dependencies

* [KMonad](https://github.com/kmonad/kmonad)
* posix sh (eg. `dash`)
* optionally systemd, to run automatically when you start your X session

_(help wanted to support auto-start for other init systems! see bug #8)_

### Installing

You can find binary packages (`deb`, `rpm`, and `tar`) plus a self-executing
`.sh` installer in
[releases](https://github.com/ryanprior/home-row-control/releases/latest).

After installing, run `systemctl --user start home-row-control`.

## Usage

Run `_home_row_control` to activate for the current session. Optionally, set up
your system to run that command automatically on login.

## Troubleshooting

Sometimes the system seems to lose the keymap. If you're using systemd you can
reset like so:

```sh-session
$ systemctl --user restart home-row-control
```

Otherwise you can serach for the home-row-control `kmonad` process and kill it,
then run `_home_row_control` again.

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
