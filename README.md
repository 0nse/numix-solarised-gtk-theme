Numix is a modern flat theme with a combination of light and dark elements. It supports Gnome, Unity, XFCE and Openbox.
Numix is a part of the [Numix Project](http://numixproject.org).

This fork tries to adapt its look using [solarised colours](http://ethanschoonover.com/solarized) and thus is a successor to [mkrnr/Numix-Solarized-Dark](https://github.com/mkrnr/Numix-Solarized-Dark).
Creating it anew was necessary due to problems introduced by GTK+ 3.20.
Moreover, the theme tries to use less visual space.
This is done in order to maximise the amount of visible content on the screen while remaining Numix' pleasant look.

Currently, only the dark scheme was solarised as this is the only one I personally need.
If you want to solarise the light version as well, feel free to send me a pull request.


### Manual installation

First, you need to compile the theme using the [Sass](http://sass-lang.com/) compiler.

To install Sass, install ruby and the gem command using your distro's package manager. Then install `sass` with the `gem` command,

`gem install sass`

You'll also need the following commands in your path to generate the gresource binary. Install them using your distro's package manager.

* `glib-compile-schemas`
* `gdk-pixbuf-pixdata`

After installing all the dependencies, switch to the cloned directory and, run the following in Terminal,

```sh
make
sudo make install
```

To set the theme, modify your `$HOME/.gtkrc-2.0`:

```
gtk-theme-name="Numix Solarised"
```

Furthermore, edit `$HOME/.config/gtk-3.0/settings.ini` so that it contains the following lines:

```
gtk-theme-name=Numix Solarised
gtk-application-prefer-dark-theme=true
```

### For developers

If you want to hack on the theme, make sure you have the `inotifywait` command available, which is used for watching and automatically building the files.

To start watching for changes, run the following,

```sh
make watch
```

If you change any assets, you'll need to regenerate the `gtk.gresource.xml` and `gtk.gresource` files. You can use [grrr](https://github.com/satya164/grrr) to do it easily.

### Requirements

GTK+ 3.16 or above

Murrine theme engine

### Code and license

Report bugs or contribute at [GitHub](https://github.com/numixproject/numix-gtk-theme)

License: GPL-3.0+
