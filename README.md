# android_platform_manifest
Init the CM11.0 repo, use --depth=1 to don't fetch all the unnecessary files.

`repo init --depth=1 -u git://github.com/CyanogenMod/android.git -b cm-11.0`

Replace local_manifest.xml to cm11.0/.repo/local_manifests/local_manifest.xml then:

`repo sync  -f --force-sync --no-clone-bundle --no-tags -j$(nproc --all)`

Guides:

https://forum.xda-developers.com/t/guide-cm11-how-to-build-your-own-cyanogenmod-11-0-rom-from-sources-for-the-nexus-4.2515305/

https://forum.xda-developers.com/t/guide-how-to-build-your-own-cm11-from-local-sources-for-the-galaxy-fame.2875919/
