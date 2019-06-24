Manifest project for building AOSP-7.1.x for Nexus 7 (2012) Grouper and Tilapia

Instructions for building:

repo init --depth=1 --no-clone-bundle -u https://github.com/AndDiSa/platform_manifest-Grouper-AOSP.git -b ads-7.1.0

repo sync --jobs="\<x>" --quiet --force-sync --no-tags --no-clone-bundle #where \<x> is equal to number of available CPU threads

. build/envsetup.sh

lunch 7 # for making grouper (9 for Tilapia)

export LC_ALL=C # optional, mitigates issues with prebuilts/misc/linux-x86/flex/flex-2.5.39 when compiling on modern OS like ubuntu 18.04 and higer 

make -j\<x> otapackage #where \<x> is equal to number of available CPU threads
