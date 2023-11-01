Device configuration for Sony Xperia XZ1 (poplar)
========================================================

Description
-----------

This repository is for LineageOS 20.0 on Sony Xperia XZ1 (poplar).

How to build LineageOS
----------------------

* Make a workspace:

        mkdir -p ~/lineageos
        cd ~/lineageos

* Initialize the repo:

        repo init -u git://github.com/LineageOS/android.git -b lineage-21.0 --git-lfs

* Create a local manifest:

        mkdir .repo/local_manifests && nano .repo/local_manifests/roomservice.xml

        <?xml version="1.0" encoding="UTF-8"?>
        <manifest>
            <!-- SONY -->
            <project name="whatawurst/android_kernel_sony_msm8998" path="kernel/sony/msm8998" revision="lineage-21" />
            <project name="whatawurst/android_device_sony_yoshino-common" path="device/sony/yoshino-common" revision="lineage-21" />
            <project name="whatawurst/android_device_sony_poplar" path="device/sony/poplar" revision="lineage-21" />

            <!-- blobs for poplar -->
            <project name="whatawurst/android_vendor_sony_yoshino-common" path="vendor/sony/yoshino-common" revision="lineage-21" />
            <project name="whatawurst/android_vendor_sony_poplar" path="vendor/sony/poplar" revision="lineage-21" />
        </manifest>

* Sync the repo:

        repo sync

* Setup the environment

        source build/envsetup.sh
        breakfast poplar

* Build LineageOS

        m bacon
