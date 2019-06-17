Manifest project for building AOSP-7.1.x for Nexus 7 (2012) Grouper and Tilapia

Instructions for building:

repo init -u https://github.com/AndDiSa/platform_manifest-Grouper-AOSP.git -b ads-7.1.0

repo sync

. build/envsetup.sh

lunch 7 # for making grouper

make -j<x> otapackage


