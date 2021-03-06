dbdump
======

A python utility to pull android database files of a particular app from an emulator without having to go through all the regular adb shenanigans every time, features:
- pulls the .db files from the databases folder to a local directory on your dev computer (you can then analyze this using sqlitebrowser: http://sourceforge.net/projects/sqlitebrowser/)
- supports multiple devices
- supports selective db file pulls
- tested on a Genymotion emulator

###Prerequisites
- python
- access to adb on the system path
- assuming adb has native root access to the emulator/device

###Usage

```bash
python dbdump.py app_packagename [destination_dir] [--device devicename] [--db my_dbfile.db]
```

###Example

To pull all the database files from my app (package: com.myorg.myapp) to the current folder

```bash
python dbdump.py com.myorg.myapp
```

To pull a particular db file (my_db_name.db) from my app (package: com.myorg.myapp) on a particular emulator(192.168.56.101:5555) to the desktop on a mac

```bash
python dbdump.py com.myorg.myapp ~/Desktop --device 192.168.56.101:5555 --db my_db_name.db
```

The device id that needs to be passed in --device can be obtained from adb devices

###Sample output

```bash
Copying my_db_name.db --> ~/Desktop
Done!
```

As seen on:
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-dbdump-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/930)
