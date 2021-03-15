# ramdisksetup

A small utility / shell script to make a ramdisk (tmpfs).

## usage

WARNING: this script needs root access. Please run with sudo.

```
ramdisk [-h] SIZE [PATH]
```

* `-h`: display help
* `SIZE`: size, for example `1m` ( = 1MB) or `1G` ( = 1GB)
* `PATH` (optional argument, default=`/tmp/ramdisk`): mountpoint for ramdisk

**Make sure the directory you pass as `PATH` does not exist!**

## installation

Simply copy the `ramdisk` file into your $PATH, for example `.local/bin/`:

```
$ cp ramdisk ~/.local/bin/
```

You can also create a symlink:

```
$ ln -s full/path/to/ramdisk ~/.local/bin/ramdisk
```

> Note: if that doesn't work, try `chmod +x`

## examples

### creating a ramdisk at the default mountpoint:

```
$ sudo ramdisk 1m
1m @ /tmp/ramdisk
* Mountpoint created
* tmpfs mounted!
Unmount with:
 sudo umount /tmp/ramdisk; sudo rm -rf /tmp/ramdisk
```

### creating a ramdisk at a custom mountpoint:

```
$ sudo ramdisk 1m /mnt/tmp
1m @ /mnt/tmp
* Mountpoint created
* tmpfs mounted!
Unmount with:
 sudo umount /mnt/tmp; sudo rm -rf /mnt/tmp
```
