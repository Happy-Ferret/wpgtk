
# wpgtk

A universal theming software for all themes 
defined in text files, compatible with all terminals, 
with default themes for GTK2, GTK+, openbox and Tint2, that uses 
[pywal](https://github.com/dylanaraps/pywal) as it's core, in which 
you can choose to interact with in two possible ways, so you can
manage your themes from either a cli applications or using a GUI.

#### [GUI](http://i.imgur.com/oJ0yakG.gif)

#### [Powerful command line interface](http://i.imgur.com/MM5yVZq.gif)

#### [Combine wallpapers and colors](http://i.imgur.com/qo5Hsoh.gif)


## Getting Started

### Dependencies

* python-gobject
* python-imaging
* Pillow (python)
* xsltproc
* pywal

**_Attention:_** If you're using another terminals, you can load colors upon opening terminals
by running `(wpg -t)` in your terminal, you can add this to your terminal's settings or anywhere
where it allows it to run on startup.

# Installing

**_Warning:_** If you have a previous version of wpgtk installed
please delete the contents of your current `~/.wallpapers` as 
they may conflict with the new folder structure.

You can install via pip:

```sh
$ pip install wpgtk
```

or install the `wpgtk-git` package via the AUR.  You can then install color-adaptable themes with
```
$ wpg-install.sh
```

And if everything went fine you can now execute `wpg` and it will take
you to the user interface (you will need to install python3-gobject if
you did not install from the AUR).


for more details on the cli interface do:
```
$ wpg-install.sh -h
$ wpg -h
```

# Theming

### General Usage

this is a list of useful wpg commands that you will be using if you want to use
the cli:
```
$ wpg -l #lists the currently added wallpapers
$ wpg -c #prints the current wallpaper
$ wpg -t #apply colorscheme to terminal (equivalent to wal -r)
$ wpg -z {wallpaper} #shuffles the given wallpaper's colorscheme
$ wpg --auto {wallpaper} #generates fg versions of the first 8 colors of the given wallpaper
$ wpg -d {wallpaper} #remove an existing wallpaper
$ wpg -h #display usage
$ wpg -s {wallpaper1} [{wallpaper2}] #sets the current wallpaper and colorscheme, wallpaper2 is optional
```

Files exported when creating a theme are all under the same directory `$HOME/.wallpapers`
this directory contains all exported formats that `pywal` and `wpgtk` have to offer, such
as:

* css variables under `$HOME/.wallpapers/current.css`
* json under `$HOME/.wallpapers/schemes/{image_name}.json`
* xres files under `$HOME/.wallpapers/xres/{image_name}.Xres`
* environment variables under `$HOME/.wallpapers/current.sh` 

### Optional files

Using the GUI you can add optional files for which `wpgtk` will create a copy and
add a modifiable file to the `~/.themes/color_other` under the file extension `.base`
in which some keywords will be replaced with the respective colors matching 
those keywords, these keywords are:

```assembly
from color 0 to color 9
#COLORY
where Y is the number of color

from color 10 to 15
#COLORXYY 
where Y is the number of color desired

also
#COLORIN (active color)
#COLORACT (inactive color)
```

after doing this `wpgtk` will replace this new file with the original.

# Loading at Startup
to load your new wallpaper at startup along with the colors add the following to your 
startup script or simply add it into your startup apps in your DE of choice.

```sh
bash ~/.wallpapers/wp_init.sh
```

# License

This project is licensed under the GPUv2 License - see the [LICENSE](LICENSE) file for details
