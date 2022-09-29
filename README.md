# AutoRaise & Launcher    ![](Launcher/Images.xcassets/AppIcon.appiconset/AutoRaise_32.png)                  


This project consists of two components: AutoRaise and Launcher. 

The **AutoRaise** binary is written and maintained by Stefan Post at https://github.com/sbmpost/AutoRaise. From the readme:

> When you hover a window it will be raised to the front (with a delay of your choosing) and gets the focus. There is also an option to warp the mouse to the center of the activated window when using the cmd-tab key combination.
> 
> See also: https://stackoverflow.com/questions/98310/focus-follows-mouse-plus-auto-raise-on-mac-os-x

While AutoRaise is concerned with GUI window and mouse behaviour, as a command line application it lacks a GUI itself.

Here's where the **Launcher** app bundle comes into play: a menubar application that allows to control and configure the AutoRaise binary. A mouse click on it's menubar icon will start/stop AutoRaise, preferences can be configured from it's context menu and will be saved between sessions.
 
 
<p align="center">
<img src="/Launcher/Menu.png" alt="alt text" width="60%" height="60%">

<img src="/Launcher/Prefs.png" alt="alt text" width="75%" height="75%">
</p>

Please note that this project does not alter the upstream AutoRaise code, it merely wraps an app bundle around it for convenience.

## Installing

There is no installer or pre-built binary being distributed via Github but AutoRaise & Launcher binaries can be installed via [MacPorts](https://www.macports.org):

`sudo port install AutoRaise`

This installs the menubar app bundle (which includes a copy of the upstream AutoRaise cli binary) into your Applications folder and symlinks the cli into the Path, usually into `/opt/local/bin`

## Building from source

Simply clone, open and build this project in XCode. 

Like upstream XCode will first build the AutoRaise binary by running

`g++ -O2 -Wall -fobjc-arc -o AutoRaise AutoRaise.mm -framework AppKit`

and include it when finally building the Launcher app bundle (AutoRaise.app).

To install copy AutoRaise.app into the `/Applications` folder and/or the AutoRaise binary to e.g. `/usr/local/bin`

## Running & Configuring

Open AutoRaise.app and click on the menubar icon to enable/disable AutoRaise with default settings. Preferences are saved between sessions in the default `~/Library/Preferences` folder.
On first launch you should be prompted to grant access for AutoRaise in _System Preferences > Security & Privacy > Privacy > Accessibility_.

More options to run and configure AutoRaise are explained in the upstream project's Readme.


If you want to suppport this project [buy me a coffee](https://www.buymeacoffee.com/lhaeger)!
