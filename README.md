If you get this error: "yad: cannot create shared memory for key 12345: File exists", run this: "ipcrm -M 12345" (to remove shared memory segment by key).
When it is open if you launch it again this may happen. You can also lose the settings.

Settings are saved in your home with in the .multi-timer file. (You can make a copy).

The yad package is required, this install it on debian:
apt install yad

In this repo there is also a launcher, an icon and an alarm.
You can specify the paths in the launcher and with alacarte (tested on gnome) you can add it to the applications menu.

If you copy the script to /usr/bin you can also launch it from the cli using:
multi-timer
Works for all the users.

Always launch the same file if you copy it somewhere else.
