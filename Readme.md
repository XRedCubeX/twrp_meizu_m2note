Device Tree based on Twrp-8.1 for Meizu M2 Note [MT6753]

Normal specs:
================================
Basic   | Spec Sheet
-------:|:--------------------------------------------------
CPU     | Mediatek MT6753 octa-core 1.3GHZ
GPU     | Mali-T720 MP3
Memory  | 2GB RAM
Screen  | 1080x1920
Storage | 16 GB
Android | Flyme OS 4.5 based on Android 5.1
Kernel  | 3.10.65

![M2Note](https://www.schermata.it/img/meizu-m1-note2.jpg "M2Note")


How to compile TWRP for this device:

```mkdir twrp
cd twrp

repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-8.1

repo sync

git clone https://github.com/XRedCubeX/twrp_meizu_m2note.git -b twrp-8.1 device/meizu/m2note

git clone https://github.com/XRedCubeX/android_kernel_m2note -b o-8.1 kernel/meizu/m2note

export ALLOW_MISSING_DEPENDENCIES=true; . build/envsetup.sh; lunch omni_m2note-eng; mka recoveryimage
```

You will now find the file recovery in: out/target/product/m2note/recovery.img
