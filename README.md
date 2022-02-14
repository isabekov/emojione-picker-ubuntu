# emojione-picker for Ubuntu

This fork of [Emojione Picker for Ubuntu](https://github.com/gentakojima/emojione-picker-ubuntu) has been revived using Python 3.9. It works on Ubuntu 21.10.

It uses the [Emoji One](http://emojione.com/) project.

## Installation

Installation will cause the program to be run at session startup.

### Recommended method: Standalone installer

This method does not require root access. If you run it as root, the picker will be installed for all users.

1. Clone the repository and cd into it:

    ```sh
    git clone https://github.com/victoriadrake/emojione-picker-ubuntu
    cd emojione-picker-ubuntu
    ```

2. For a stable release, list the available releases: `git tag -l` and checkout the one you want, for example: `git checkout v0.1`. Ignore this to install the latest development version.
3. Run `./install.sh`.
4. To uninstall, run `./install.sh` again.

#### I get "ValueError: Namespace AppIndicator3 not available" at startup

You're missing a required Python library. Please install the required package:

- Ubuntu: `gir1.2-appindicator3-0.1`
- OpenSuse Leap: `typelib-1_0-AppIndicator3-0_1`

### Method 2: Build a Debian Package from source

This method requires root access and was only tested on Ubuntu 14.04, 15.10 and 16.04, but should work on any Debian-based distribution.

1. Install dependencies: `sudo apt-get install python-2.7 python-all-dev build-essential python-notify gir1.2-notify-0.7 gir1.2-appindicator3-0.1 gir1.2-rsvg-2.0`
2. Clone the repository and cd into it:

    ```sh
    git clone https://github.com/victoriadrake/emojione-picker-ubuntu
    cd emojione-picker-ubuntu
    ```

3. For a stable release, list the available releases: `git tag -l` and checkout the one you want, for example: `git checkout v0.1`. Ignore this to install the latest development version.
4. Build the package: `debuild` (*Signing the package might fail at this point, but it's not a big deal*)
5. Install it: `sudo dpkg -i ../emojione-picker*.deb`

## How to run it

If you installed it, the picker should be started on a fresh session start. Just close your current session, and start it again.

If you want to manually run it, use the command `emojione-picker`. If you used the standalone installer and installed it just for the current user, you might need to specify the path to the program, for example, `~/.local/bin/emojione-picker`.

## How to use it

To use the picker:

  1. Choose your emoji from the dropdown menu.
  2. Paste it (usually `Ctrl+V`) wherever you want!

You can also enable the **experimental** option to type the emoji instead of using the clipboard in the Settings.

The **emoji search window** let you search emojis with keywords.

You can also assign a global hotkey to the command `emojione-picker`.

## Troubleshooting issues

The indicator usually takes 3 to 5 seconds to load, but it can take up to 30 seconds in older computers. In *Settings*, enable the option *Low end computer mode* to reduce the number of menu items (and emojis). That should speed up loading time. Currently, this mode shows about 1000 emojis out of 1800.

The **emoji search window** might be incorrectly placed under the current active window due to Unity/Compiz focus stealing prevention feature. This is not intended behaviour. The only known workaround is to disable this feature by running this command:

```sh
dconf write /org/compiz/profiles/unity/plugins/core/focus-prevention-level 0
```

If you want to enable the focus stealing prevention feature again, just run this command instead:

```sh
dconf write /org/compiz/profiles/unity/plugins/core/focus-prevention-level 1
```

## License

The code is probably poisoned by the GPL somehow, and I'm too lazy to check it. So be it, this will be licensed as GNU GPL v3. You know, *that* license. Check your smart TV or your toaster manual for a printed copy.

Emojis are licensed by the great people of [Emoji One](http://emojione.com/) under a free culture Creative Commons License (CC-BY 4.0).
