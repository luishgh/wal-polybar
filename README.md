# wal-polybar
A handy python script to customize your polybar with pywal colors.

## Requirements
### Dependencies

- linux or bsd
- python 3
- polybar
- pywal

## Installation

### Setup

-  Clone this repository with `git clone https://github.com/LuisHGH/molar-installation-scripts.git` or download only the script with `wget https://raw.githubusercontent.com/LuisHGH/wal-polybar/master/wal-polybar.py` 

- Make a backup of your current polybar config file just to be safe (it is usually located at `~/.config/polybar/config` )
- Copy your backup to a config.template file under the same directory (you can also use a custom directory, see: ...)
- Paste the following to the colors section of your config.template (you can also define the colors from the wal cache manually, see ...)
```
background = ${wal.color0}
background-alt = ${wal.color8}
foreground = ${wal.color7}
foreground-alt = ${wal.color7}
primary = ${wal.color1}
secondary = ${wal.color2}
alert = ${wal.color3}
```  
- Now just run these commands below in a terminal (assuming you're in the same folder as `wal-polybar.py`'):
```shell script
sudo ln -s "$(pwd)/wal-polybar.py"  /usr/bin/wal-polybar
wal-polybar
```
- Now just reload your polybar and it should be themed following your background colors!


## How to use `wal-polybar`
Run `wal-polybar` to update your polybar with any edits made at config.template or to a new background image. Remember that `wal-polybar` uses the cache of wal, so you need to generate the new color scheme with  `wal` before `wal-polybar` can acess it.
```sh
usage: wal-polybar [-v version] [-t 'path/to/template']

optional arguments:
    -v displays the version of wal-polybar
    -t runs the script with a custom template path 
 
```
You can also add `wal-polybar` to your startup aplications file assuming you also have wal on it to always update your polybar theme on startup

## Customization

### Color scheme
You can manually acess the wal cache colors individually at specific points of your config.template file using the sintax:
```
${wal.colorx}
```
Where x is a number between 0 and 15 that corresponds to it's position at the wal cache file. It's generally located at `~/.cache/wal/colors`.
The number of the colors follow a pattern established by `wal`: they are the 16 most present colors on the image in a decreasing order.
