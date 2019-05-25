![Moon Open Stars Project](https://raw.githubusercontent.com/MoonOSX/MoonOSXStuff/master/img/moonosx-banner-XDA.png)

Syncing the source
===================

Please read the following before proceeding:

* [Requirements](https://source.android.com/setup/build/requirements)
* [Installing dependencies](https://source.android.com/setup/build/initializing)
* [Installing repo](https://source.android.com/setup/build/downloading)

Initialize the repository:
```bash
repo init -u https://github.com/MoonOSX/moon.git -b pie
```

Then to sync up:
```bash
repo sync -c -f -j$(nproc --all) --force-sync
```

Building
========

After you have finished syncing, please read the [AOSP building instructions](https://source.android.com/setup/build/building) on how to build.

You can also build for specific devices like this:
```bash
. build/envsetup.sh
lunch aosp_$devicecodename-userdebug
mka bacon -j4
```

In which `$devicecodename` would be your device's codename (e.g. `bacon` for the OnePlus One).

Remember to `make clobber && make clean` every now and then!
