# android_platform_manifest

## Requirements To Build
- A decent CPU
- 8GB of RAM
- 100GB of storage
- JDK 6
- [Android Build Dependencies](https://source.android.com/setup/build/initializing#setting-up-a-linux-build-environment)

## How To Set Up Sources

```
repo init --depth=1 -u git://github.com/CyanogenMod/android.git -b cm-11.0
git clone git://github.com/T110-android/android_platform_manifest.git .repo/local_manifests && rm -rf .repo/local_manifests/.git/
repo sync -c --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune -j$(nproc --all)
```

## How To Build

```
. build/envsetup.sh
lunch cm_goyawifi-[buildtype = eng|user|userdebug]
mka [target = bacon, otapackage, bootimage etc.]
```

**e.g.**

```
. build/envsetup.sh
lunch cm_goyawifi-eng
mka bacon
```

## Building Guides
[\[GUIDE CM11\] How to build your own CyanogenMod 11.0 ROM from sources for the Nexus 4](https://forum.xda-developers.com/t/guide-cm11-how-to-build-your-own-cyanogenmod-11-0-rom-from-sources-for-the-nexus-4.2515305/)

[\[GUIDE\]How to Build your own CM11 from Local sources for the Galaxy Fame](https://forum.xda-developers.com/t/guide-how-to-build-your-own-cm11-from-local-sources-for-the-galaxy-fame.2875919/)

## Errors
- `fatal error: CSSGrammar.hpp: No such file or directory`
  - `cd out/target/product/goyawifi/obj/GYP/shared_intermediates/blink`
  - `ln -s CSSGrammar.h CSSGrammar.hpp`
  - `ln -s XPathGrammar.h XPathGrammar.hpp`
- `Assertion 'cnt < (sizeof (_nl_value_type_LC_TIME) / sizeof (_nl_value_type_LC_TIME[0]))' failed.`
  - `export LC_ALL=C`

### Good luck and have fun building CyanogenMod!
