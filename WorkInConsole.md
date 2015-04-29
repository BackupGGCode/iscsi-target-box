## Introduction ##

You can operate box by means of the console or telnet connections.


## iSCSI Enterprise Target Daemon ##

Config stored in `/etc/iet/`.

Stop daemon:
> `ietadm --op delete`

> `killall ietd`

Start daemon:
> `/sbin/ietd`

Viewing of sessions:
> `cat /proc/net/iet/session`

Viewing of shared volumes:
> `cat /proc/net/iet/volume`

## iSCSI Enterprise Target Administration Utility ##

Add a Target:
> `ietadm --op new --tid=[id] --params Name=iqn.foo.bar:test1`

id must be unused and not zero.

Add a LUN to a pre-existing target:

> `ietadm --op new --tid=[id] --lun=[lun] --params Path=/path/to/exported/file,Type=fileio`

> or

> `ietadm --op new --tid=[id] --lun=[lun] --params Path=/path/to/exported/dev,Type=blockio`

id must be an already existing Target ID.

Display status of Target:
> `ietadm --op show --tid=[id]`

Change Target parameters:
> `ietadm --op update --tid=[id] --params=key1=value1,key2=value2,...`

Delete existing LUN:

> `ietadm --op delete --tid=[id] --lun=[lun]`