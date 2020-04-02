# batterymon-clone

Note: After 8 years without making changes to this code, _denilsonsa_ decided to archive this repository. If you are interested, please look at [other forks](https://github.com/sayamindu/batterymon-clone/network). At the time of archival, [_ixxra_'s fork](https://github.com/ixxra/batterymon-clone) seems to be the one with most activity.

## Summary

**batterymon-clone** is a simple battery monitor tray icon for Linux.

* Written in `Python`
* Should work on any desktop environment
* Very little dependencies: just `Python` and `PyGTK`
* Optional support for `notify-python`, for notifications using `libnotify`

The current implementation reads battery information from `/sys/class/power_supply/`, and updates the state by polling every few seconds.

### Changelog summary:

* Version 1.4.0 reads information from `/sys/class/power_supply/`, which has been added in Linux kernel 2.6.23. However, it uses `power_now` instead of `current_now`, and thus only works on 2.6.30 and newer.

* Version 1.3.0 reads information from `/proc/acpi/` interface (which has been removed from Linux kernel 2.6.39). The old DBus+HAL code was replaced by polling the battery state every few seconds.

* Older versions used DBus and HAL instead of polling the state every few seconds. However, support for HAL has been deprecated and removed from most distros.

## History

**batterymon-clone** is a fork of **batterymon**

[**batterymon**][1] was originally written in mid-2009 by _Matthew Horsell_ and _Tomas Kramar_, and was available at Google Code.

It was later forked in 2010 as [**batterymon-clone**][2] by _sayamindu_ on GitHub.

After a long time without commits, _denilsonsa_ [forked][3] and updated it in mid-2011.

Each one of the authors contributed a little in order to make _batterymon_ a better software for their own needs. You can also contribute! Feel free to fork this code and improve it!

[1]: http://code.google.com/p/batterymon/
[2]: https://github.com/sayamindu/batterymon-clone
[3]: https://github.com/denilsonsa/batterymon-clone

## Future improvements

Here is a list of things you can do to help moving _batterymon_ forward:

* Some code cleanup/refactor.
* Add a COPYING or LICENSE file (see [issue 15 at Google Code][oldissue15]).
* Add native GTK/freedesktop theme support (see [issue 16 at Google Code][oldissue15]).
  * But built-in theme support should still be kept.
* Add back support to DBus, but using newer interfaces. See [battery-status][battery-status] or [batti-gtk][batti] projects for inspiration.
  * But polling support should still be kept as fall-back.
* Take a look at [issue list at Google Code][oldissues] and try fixing them.
* Port to Python 3
* Update i18n

You do not need to ask for permission to fix them. Just fork this repository and start coding!

[battery-status]: https://github.com/ia/battery-status/blob/master/battery-status
[batti]: http://code.google.com/p/batti-gtk/
[oldissue15]: http://code.google.com/p/batterymon/issues/detail?id=15
[oldissue16]: http://code.google.com/p/batterymon/issues/detail?id=16
[oldissues]: http://code.google.com/p/batterymon/issues/list
