Manifest project for building AOSP-7.1.x for Nexus 7 (2012) Grouper and Tilapia

Instructions for building:

repo init -u https://github.com/AndDiSa/platform_manifest-Grouper-AOSP.git -b ads-7.1.0

repo sync

...

cd build

patch -p 1 < ../.repo/manifests/build.patch

cd ..

cd frameworks/av

patch -p 1 < ../../.repo/manifests/frameworks_av.patch

cd ../..

cd frameworks/base

patch -p 1 < ../../.repo/manifests/frameworks_base.patch

cd ../..

cd frameworks/native

patch -p 1 < ../../.repo/manifests/frameworks_native.patch

cd ../..

cd hardware/ril

patch -p 1 < ../../.repo/manifests/hardware_ril.patch

cd ../..

cd packages/aps/Music

patch -p 1 < ../../../.repo/manifests/packages_apps_music.patch

cd ../../..

cd system/core

patch -p 1 < ../../.repo/manifests/system_core.patch

cd ../..

cd system/sepolicy

patch -p 1 < ../../.repo/manifests/system_sepolicy.patch

cd ../..

. build/envsetup.sh

lunch 7 # for making grouper

make -j<x> otapackage


