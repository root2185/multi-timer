This is an application to set multiple timers sequentially. 

It is tested on Debian 9, 10, 11, Ubuntu 14.04, 16.04, 18.04, Windows 10 with Ubuntu 16.04 Desktop installed.<br>
Probably works on the others GNU/Linux ditros too.

All credits are to https://askubuntu.com/users/307523/wineunuuchs2unix, the script is taken from here https://askubuntu.com/questions/1039357/a-timer-to-set-up-different-alarms-simultaneosly.<br>

Settings are saved in your home with in the .multi-timer file. (You can make a copy).

The yad and libnotify-bin package are required, this install them on Debian:

`apt install yad libnotify-bin`

This package doesn't work on gnome wayland, because of yad.
The alarms won't sound if you aren't running pulseaudio or pipewire as replacement.

You may need to set the number of timers:
At line number 140, 141 and 142 you will see this:
```
# No. of timers default is 17 for 768 line screen and TMR_DURATION_NDX is 30
TMR_DURATION_NDX=30 # Set to 28 for 800x600 screen, 32 for 1920x1080 screen
MAX_TIMERS=17       # Set to 15 for 800x600 screen, 19 for 1920x1080 screen
```
Although 19 timers are supported, they might only fit on a 1920x1080 screen. About 17 (the default setting) will fit on the average 1024x768 screen. If you have Super VGA with 800x600 resolution you might only get 13 to 15 timers.

You must change the values on the others lines at the same time:
```
Bash field name    ----------- Values to assign ---------
TMR_DURATION_NDX   23  24  25  26  27  28  29  30  31  32
MAX_TIMERS         10  11  12  13  14  15  16  17  18  19
```
eg If you want a maximum of 12 timers, set TMR_DURATION_NDX=25 and MAX_TIMERS=12.

After changing the Index and Maximum save the multi-timer file. If you have already run the program once a configuration file may have been created and it will have to be deleted. Use this command to remove the old configuration file:

`rm ~/.multi-timer`

In this repo there are also a launcher, an icon and an alarm.
You can specify the paths in the launcher and with alacarte (tested on gnome) you can add it to the applications menu.

If you copy the script to /usr/bin you can also launch it from the cli using:

`multi-timer`

Works for all the users.

Icon credit: https://icon-library.com/icon/timer-icon-24.html.
